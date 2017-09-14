---
layout: post
title: "Disabling CMS User Tests"
author: Perchema
---
Last month I was preparing a lecture on interactive informatics tasks and wanted
to set up some example problems in [CMS][cms].
One of the task types I wanted to showcase was [two steps][cms-two-steps][^1].

### The problem
At the time of writing CMS doesn't fully support this task type.
One feature of CMS is user tests - contestants can run their sollution on a
specific input under the constest environment.
This is really convinient for debugging more unusual tasks.
The problem is that user tests for two steps tasks are not implemented
(literally CMS throws a *NotImplementedError*).
Moreover sending a user test throws an exception which hangs the worker,
rendernig CMS useless.

So, I wanted to disable user tests for the two steps problem.
The only issue is that you can disable them for the whole contest but not for
specific tasks.

### The sollution
In CMS you can limit the number of user tests per task per user.
If I could set this limit to zero, then nobody could send user tests.
This stops them from hanging the worker and breaking the system for everyone.

CMS requires that the maximum allowed number of user tests is at
least one.
After some digging I found out that the contsrtaint is set on the database
level.
So, you can enter the database console and can change it with the following two
queries:

```sql
ALTER TABLE tasks DROP CONSTRAINT "tasks_max_user_test_number_check";
ALTER TABLE tasks ADD CONSTRAINT "tasks_max_user_test_number_check" CHECK (max_user_test_number >= 0);
```

The original constraint `CHECK (max_user_test_number > 0)`{: .language-sql} is
removed by the first line.
The second line creates a new one in its place, which allows for
`max_user_test_number` to be 0.
Of course, running `cmsInitDB` or `cmsDropDB` will reset the constraint to its
original value and you will have to run these queries again.

If you are lazy you can just paste the following code in your terminal and it
should do the trick.

```bash
sudo su - postgres
psql --username=postgres --dbname=cmsdb --command='ALTER TABLE tasks DROP CONSTRAINT "tasks_max_user_test_number_check"'
psql --username=postgres --dbname=cmsdbp --command='ALTER TABLE tasks ADD CONSTRAINT "tasks_max_user_test_number_check" CHECK (max_user_test_number >= 0)'
```

### Conclusion
As you may have noticed this is more of a hack than a legitimate solution.
As such it may break in a future version of CMS or it might even be breaking
something in the current one.
Basically, use at your own risk.

[^1]:
    If you are interested, [Parrots][ioi-parrots] and [Last Supper][ioi-last-supper]
    from the [IOI][ioi] are good (and hard) examples of two steps tasks.

[cms]: http://cms-dev.github.io/
[cms-two-steps]: https://cms.readthedocs.io/en/v1.3/Task%20types.html#twosteps
[ioi-parrots]: http://www.ioi2011.or.th/hsc/tasks/EN/parrots.pdf
[ioi-last-supper]: http://www.ioi2012.org/wp-content/uploads/2011/12/supper.pdf
[ioi]: www.ioinformatics.org
