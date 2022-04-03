# An-Improved-Scheduling-Algorithm-for-Real-Time-Systems



Our Proposed Algorithm:
We calculate an intelligent time slice (ITS) is calculated based on the priority, shortest CPU burst time and context switch. We have a pre- defined time slice which is the Original time slice
(OTS), if the process needs special consideration, the priority component (PC) is assigned to 0 or 1 according to the pre-defined priority by the user. We define a Shortness component (SC) which is the difference between the burst time of the current process and its previous process. If the difference is negative, we make SC as 1 else
0. To calculate CSC i.e. Context switch component we add PC, SC
 
and OTS and the resulting sum is subtracted from the burst time of the process. If the result obtained is less than the OTS, we consider it as CSC. Adding all the calculated components we get our ITS.
Our time quantum varies from TQi to TQn, where i is the round number

III.	Algorithm:



Step 1- Sort the processes according to priority as well as shortness and assign a new priority to each process which is the sum of the original priority and shortness rank.
Step 2- Calculate priority component. If there are n processes, for a process i in n
PCi=0 if its new priority is > 2n/3 (Not Important)
PCi=1 if its new priority is > n/3 (Moderately Important) PCi=2 if its new priority is >= 1 (Important)
Step 3- Calculate shortness component. If there are n processes, for a process i in n
SCi=0 if the (Burst Time)i>(Burst Time)i-1 (Longer) SCi=1 if the (Burst Time)i<=(Burst Time)i-1 (Shorter)
Step 4- Calculate the intelligent time slice (ITS) for each process as the sum of the initial time slice, burst time, priority component and shortness component.
Step 5- Repeat Step 6 until all processes are completed.
Step 6- If the Round number(j) is 1, calculate time quantum as TQj,i=ITSi if SCi=1
 
TQj,i=ITSi/2 if SCi=0
If the Round number(j) is not 1, calculate time quantum as TQj,i=TQj-1,i * 2 if SCi=1
TQj,i=TQj-1,i * 1.5 if SCi=0
Step 7-Calculate average waiting time and average turnaround time.
