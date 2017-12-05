---
layout: post
title: "Karatsuba's Algorithm"
author: Perchema
---
When dealing with numbers, having hundreds of thousands of digits, we need to
implement ourselves even basic arithmetic (e.g. addition or division). In this 
post I'm going to explain Karatsuba's algorithm for multiplication.

### What are Long Numbers ?
For those of you who haven't heard of *long numbers* or *BigInts*, I suggest 
reading [this][stack_overflow_tutorial] tutorial on StackOverflow. A quick
primer: To work with large figures, we split them into smaller parts (a la digits)
and follow the rules we, humans, use to add, subtract, multiply, etc.

#### The Basic Algorithm for Multiplication
You apply the algorithm you are thought in grade school - you multiply the first
number with every digit of the second one and sum the results. The complexity of 
this algorithm is $$O(n^2)$$. [Read more][grade_school_wikipedia].

{% highlight c++ %}
//we assume that both numbers are of the same length (len) 
void grade_school(int64_t *a, int64_t *b, int64_t *ans, int32_t len) {
    for (int32_t i = 0;i < len;i++) {
        for (int32_t j = 0;j < len;j++) {
            ans[i + j] += a[i] * b[j]; 
            //carry
            ans[i + j + 1] += ans[i + j] / 10;
            ans[i + j] %= 10;
        }
    }
}
{% endhighlight %}

#### Optimizations
Use a bigger base -  $$10^8$$ reduces the number of digits 8 times and makes
the algorithm $$8^2 = 64$$ times faster.

  * Watch out for overflow - in the case of multiplying you need to fit the
    square of your base in the data type you're using.
  * Use powers of 10 to avoid problems with I/O

### Karatsuba
In 1960 Anatoly Karatsuba developed a *Divide and conquer* algorithm for 
multiplication of numbers. The basic idea is to replace part of the
multiplication with additions and subtractions. 

#### Math
We want to multiply the numbers $$x$$ and $$y$$. For simplicity they're going to
be both $$n$$ digits long in some base $$B$$. Let's pick some number of digits
$$m$$, such that $$0 < m < n$$. Then we can split our numbers as:

$$x = x_1B^m + x_0$$  
$$y = y_1B^m + y_0$$  

Let's express the product:  
$$xy = (x_1B^m + x_0)(y_1B^m + y_0)$$  
$$xy = x_1y_1B^{2m} + (x_1y_0 + x_0y_1)B^m + x_0y_0$$  
$$xy = z_2B^{2m} + z_1B^m + z_0$$  

After $$z_2$$ and $$z_0$$ are calculated, $$z_1$$ can be computed with a single
multiplication:  
$$z_1 = x_1y_0 + x_0y_1$$  
$$z_1 = (x_1y_1 + x_1y_0 + x_0y_1 + x_0y_0) - (x_1y_1 + x_0y_0)$$  
$$z_1 = (x_1 + x_0)(y_1 + y_0) - x_1y_1 - x_0y_0$$  
$$z_1 = (x_1 + x_0)(y_1 + y_0) - z_2 - z_0$$

#### The Algorithm
To achieve best performance the numbers are split into halves -
$$m = \lceil n / 2 \rceil$$. $$z_0, z_1, z_2$$ are calculated by using the 
same algorithm, applied recursively. When the numbers become small enough, 
they are multiplied directly.

{% highlight pseudocode %}
procedure karatsuba(x, y)
    if (x < 10) or (y < 10)
        return x * y

    maxLen = max(len(x), len(y))
    m = ceil(maxLen / 2)

    /* split the digit sequences about the middle */
    x1, x0 = split_at(x, m)
    y1, y0 = split_at(y, m)

    /* 3 calls made to numbers approximately half the size */
    z0 = karatsuba(x0, y0)
    z2 = karatsuba(x1, y1)
    z1 = karatsuba((x1 + x0),(y1 + y0)) - z0 - z1

    return z2 * BASE ^ (2 * m) + z1 * BASE ^ m + z0
{% endhighlight %}

#### Complexity
At each step there are $$O(n)$$ operations performed for addition and 
subtraction and the algorithm is called recursively 3 times, for numbers, half
the length of the original ones. The number of elementary operations is:

$$T(n) = 3T(\lceil n / 2\rceil) + an$$

Using the [master theorem][master_theorem] for complexity of recursive 
algorithms (I won't explain it here, it's a big topic in its own right), we can
calculate the complexity of Karatsuba's algorithm as 
$$O(n^{log_2{3}}) \approx O(n^{1.585})$$.

### Implementation
Karatsuba doesn't improve the simple grade school algorithm that much, due to 
the overhead, added for recursion. To have it run fast, one needs an efficient 
implementation. There were 2 main optimizations, that've sped up my code:

 *  Use the $$O(n^2)$$ algorithm, for small numbers to eliminate overhead - 
    for my code I've found 16 digits to be the threshold.

 *  Don't allocate memory dynamically - use ordinary arrays and pointers. I 
    couldn't find it explained anywhere, but the code of 
    [Carl Burch][carl_burch_karatsuba] has helped me. His idea is to 
    have a bigger array for the answer, used to store all intermediate 
    calculations and as a stack for the lower level recursion calls - since 
    their numbers are twice as small, they only need half the memory.

     *  $$2n$$ digits for the final answer
         *  $$2m$$ for $$z_0$$
         *  The other ($$n - 2m$$) for $$z_2$$
         *  $$z_0$$ and $$z_2$$ are calculated directly where they need to be 
            at the end.
    * $$2m$$ digits for the sums $$x_1 + x_0$$ and $$y_1 + y_0$$.
    * $$2m$$ digits for $$z_1$$
    * $$2n$$ digits for lower recursion

#### Testing
After you've implemented Karatsuba, I highly recommend uploading your code to an
online judge. SPOJ has 2 version of this problem with different constraints -
[MUL][SPOJ_mul] and [VFMUL][SPOJ_vfmul]. Having it tested makes sure you have
learned and implemented the algorithm correctly.

#### My code
You can find my source as a [gist][my_code]. It runs for 1.06 sec on
[VFMUL][SPOJ_vfmul], but it can probably be optimized further.

### Further reading
I should mention that Karatsuba's algorithm isn't the fastest way to multiply
long numbers. If you're interested you can read more about the more efficient 
[Schönhage–Strassen algorithm][wikipedia_mult_fft], which uses 
[Fast fourier transforms][wikipedia_fft]. Another interesting topic is the
[Strassen algorithm][wikipedia_matrix], which is \"Karatsuba for matrices\".

[stack_overflow_tutorial]: http://stackoverflow.com/questions/1218149/arbitrary-precision-arithmetic-explanation
[grade_school_wikipedia]: https://en.wikipedia.org/wiki/Multiplication_algorithm#Long_multiplication
[master_theorem]: https://en.wikipedia.org/wiki/Master_theorem
[carl_burch_karatsuba]: http://www.cburch.com/proj/karat/karat.txt

[SPOJ_mul]: http://www.spoj.com/problems/MUL/
[SPOJ_vfmul]: http://www.spoj.com/problems/VFMUL/
[my_code]: https://gist.github.com/Alaxe/23f6267ab86c793da280#file-karatsuba-cpp

[wikipedia_mult_fft]: https://en.wikipedia.org/wiki/Sch%C3%B6nhage%E2%80%93Strassen_algorithm
[wikipedia_fft]: https://en.wikipedia.org/wiki/Fast_Fourier_transform
[wikipedia_matrix]: https://en.wikipedia.org/wiki/Strassen_algorithm
