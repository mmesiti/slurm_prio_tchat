

# When will my job run?

`squeue --start`

* Default: FIFO
* With the Multifactor Priority Plugin, jobs are ordered by priority
* But if your job can be executed without delaying the start of any other jobs,
  the backfill 

## The slurm priority formula 

https://slurm.schedmd.com/priority_multifactor.html

### Values of the parameters

/etc/slurm/slurm.conf

OR

`sprio -w`

### `sacctmgr`

For the QOS part:
`sacctmgr list qos`


What is an association?
```quote
The association is a combination of cluster, account, user names and optional partition name.)
```
For the association part:
`sacctmgr list associations`

### `sprio -l`

To check all the terms in the formula!

### The fairshare

sshare -a

#### Fair Tree algorithm
Accounts are ordered, first get 1.0, last gets 0.0
https://slurm.schedmd.com/fair_tree.html

Old algorithm (classic fair share):
https://slurm.schedmd.com/classic_fair_share.html

the fairshare factor decreases as the ratio usage/assigned share of 
resources increases

The usage is corrected taking into account the usage of the "siblings",
e.g. users that share the same account.




## Backfill pass

https://slurm.schedmd.com/SUG14/sched_tutorial.pdf

```
Backfill scheduler will start lower priority jobs if doing
so does not delay the expected start time of any
higher priority job
```
