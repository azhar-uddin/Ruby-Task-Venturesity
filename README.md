# Ruby-Task-Venturesity

Write a program that helps in balancing load among a set of servers. The input will be an array of integers, indicating number of units of load on each server. For each second, a loaded server can share its load with the neighbors one unit at a time. The output of the program should be the minimum time taken to balance the load. There can be multiple loaded servers in the input array, and they can share load in the same second, if needed.

Example: 0,0,10,0,0,0,0,0,0,0
There are 10 servers having load as below. Each server is placed next to each other. For each second, the server can share the load with the neighbors one at a time.

Time 0: 0,0,10,0,0,0,0,0,0,0
Time 1: 0,1,8,1,0,0,0,0,0,0
Time 2: 1,1,6,1,1,0,0,0,0,0
...
Time 7: 1,1,1,1,1,1,1,1,1,1

Here, the expected answer is 7 seconds, i.e. it took 7s to balance the load among servers.

So, sample input: 0,0,10,0,0,0,0,0,0,0
Output: 7 

Judging Criteria:

Efficiency
Code Quality
Correctness
Input Validation

Note:You must use the Ruby programming language to complete this challenge!

Solution:
1) Asks the user to enter the input. 
2) If user enters the input other than comma( , ) separated positive integers, it asks the user to enter the valid input. 
3) If the user enters a valid input and if the total load of all servers cannot be balanced between the number of servers, 
it prints that 'The load cannot be balanced equally', else prints the minimum time taken to balance the load.
Note: 1)Please uncomment the 2 commented lines in the code to print the sever loads at each second. 
2) There are 2 files with the same code in the github path, one is the .rb file and the other is the .txt file.
