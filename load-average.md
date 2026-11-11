# 01 – Load average

## What it is
Load average = number of processes not done yet (running, waiting in line
for a CPU, or stuck on disk). It's a count, not a percentage.
Shown as 3 numbers: average over the last 1, 5 and 15 minutes.

## How to read it
- CPU problem: `running` stays higher than the number of cores
- Disk problem: `stuck` stays above 0 (and disk_wait goes up)
- busy + disk_wait + idle ≈ 100

## Analogy
The machine is a shop. Cores = cashiers, processes = customers,
disk = stockroom.

## Mistake I made
Ran the disk test in /mnt/c (the Windows filesystem). Linux didn't see it as
disk I/O, so stuck and disk_wait stayed at 0. Lesson: a tool only shows what
it can see.
