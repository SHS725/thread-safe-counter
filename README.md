# thread-safe-counter

20173408-신현승

#### Compiled in WSL2


<img width="869" alt="Mutex vs Semaphore" src="https://user-images.githubusercontent.com/68070637/121775192-15cfd200-cbc1-11eb-9d3b-30cde6e88ddc.PNG">

At first I used semaphore header file to implement semaphore variable. It works very well but I recognized Professor gave us semaphore example code so I made another code with that example code. It is tscounter3.c.
So the picture I post is comparing between original Mutex(tscounter.c) and semaphore(tscounter3.c)
As you can see Mutex one is much faster than semapohore one.
