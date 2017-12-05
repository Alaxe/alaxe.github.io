---
layout: post
title: "VPSs for Informatics Competitions"
author: Perchema
---
Recently a few informatics competitions I participated in had problems with 
their grading systems - it would take up to *an hour* for a submisson to be
tested.
Here I am going to explain why this happens and propose a solution - [virtual
private servers][vps].

### What is the Problem ? 
Hosting an informatics competition is very computationally intensive.
That's because each solution may require anywhere from 5 to 30 seconds to be
graded.
Suppose we had 100 participants, 5 tasks and on average 2 submission per user
per task.
(The rationale behind this last estimate is that most users won't even try
solving the harder problems.)
Assuming it took an average 10 seconds to test each solution, we get
100 × 5 × 2 × 10 = 10 000 seconds or about 3 hours of computing time.
If the competition was 2 hours long we would need 3 ÷ 2 = 1.5 computing cores.

But that's an optimistic estimate - it assumes that solutions are submitted
uniformly throughout the competition (they aren't).
Also, as usually participants are provided with feedback, we don't want any
solutions to have to wait for too long before being tested - that would defeat
the purpose of feedback.
To account for this we would have to bump up our previous number of 1.5 to 3 or
maybe even 6 computing cores just to be safe - this is a rough estimate after
all.

This second part is what got messed up during the aforementioned competitions.
Even though all submissions were graded eventually, the feedback was taking so
long it was practically useless. 

### Why VPS ?
It is expensive to buy a server with so much computing power, but if you
rent a virtual one, just for the few hours you actually need it, it becomes
much more affordable.
What is nice about virtual private servers (or [IaaS][IaaS]) is that they
run a full [linux][linux] distribution and therefore act very similarly to a
physical machine.
This means you could install anything you wanted, something especially important
if you want to use third party software (e.g. [CMS][cms]).

The biggest players in the VPS market are [DigitalOcean][digital-ocean] and 
[Linode][linode]. 
They are both reliable and competitively priced, so you can't really go wrong
with either one.
Still, for this workload I would recommend DigitalOcean as they've recently
introduced [High CPU VPSs][high-cpu] which are better suited for this task. 

Both VPS providers offer per hour billing - that's key as we don't
want to rent our servers for a whole month, but just for our 2 hour 
competition.
At the time of writing a DigitalOcean VPS with 8 cores costs $160/month which is
only $0.25/hour - less than a dollar for our hypothetical usecase.
Virtual servers can also be upgraded on the fly which is really nice
because you can start with a low-end VPS, configure it and then upgrade it
just before the competition - you wouldn't be paying for computing power you 
aren't using anyway.

### My Recommended Setup
What would I do if I had to organize a large scale competition myself ?

Let's start with the software: I would use CMS because it's very robust and has
been used for many prestigious competitions, including the [IOI][ioi].
Another cool feature of CMS is that it's designed in way that allows for
different parts of it (or *services*) to be run on different machines.

I would have a cheap VPS running the web server and database, as they are relatively
lightweight, and a (few) high performance VPSs for the *workers* or the services
which do the computationally intensive testing.
While it's simpler to setup only a single worker VPS, it's really easy to clone
VPSs so it is not a big deal to use more.
This would come with the benefit of allowing me to add workers quickly during the
competiton in case I needed more than I had anticipated.

These VPSs would still need to communicate with each other.
Fortunately, both DigitalOcean and Linode offer a local network for your virtual
servers, which doesn't count against your transfer quotas.
I would still need to use secure passwords though, as this network isn't
private - it's open to all VPSs in the datacenter.

To minimise cost I would create the worker servers just before the competition
from a previously configured image (snapshot) and delete them after the testing
has finished.
Still I would leave the web server VPS running so I could provide online
results.

### Conclusion
Running an informatics competition requires a lot of computing power.
Instead of buying an expensive hardware, you could rent VPSs for little to
nothing and achieve the same (if not better) results.
While you are free to use any software, I would choose CMS at it's reliable and
well suited for this multi-machine setup.


[vps]: https://en.wikipedia.org/wiki/Virtual_private_server
[IaaS]: https://en.wikipedia.org/wiki/Infrastructure_as_a_service
[digital-ocean]: https://www.digitalocean.com
[linode]: https://www.linode.com/
[linux]: https://en.wikipedia.org/wiki/Linux
[cms]: https://cms-dev.github.io/
[high-cpu]: https://www.digitalocean.com/products/compute/high-cpu/
[ioi]: http://www.ioinformatics.org/
