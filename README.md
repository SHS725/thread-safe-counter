# thread-safe-counter

20173408-신현승

#### Compiled in WSL2


<img width="869" alt="Mutex vs Semaphore" src="https://user-images.githubusercontent.com/68070637/121775192-15cfd200-cbc1-11eb-9d3b-30cde6e88ddc.PNG">

At first I used semaphore header file to implement semaphore variable. It works very well but I recognized Professor gave us semaphore example code so I made another code with that example code. It is tscounter3.c.
So the picture I post is comparing between original Mutex(tscounter.c) and semaphore(tscounter3.c)
As you can see Mutex one is much faster than semapohore one.

Let me explain about Mutex and Semaphore first.
First as I learned from class, we need those fuctions for preventing race condition when we use multi proceeses or multi threades. There is common resources that only limited process or thread should access. If not, there will be conflict between them and it cause wrong count in our code. So we should lock the common resource in critical section and for that we can use Mutex or semaphore.

Mutex is abbreviation of Mutual exclusion. As we can see in the word Mutex can lock the critical sectionn for only one process or thread(I will explain from a thread point).
With Mutex, thread could lock the door of critical section with a key. And the locked door only can be opened by entered thread with the key. And the key will be passed to the next thread which was in the waiting line.

Semaphore uses concept of counter so it declared as a integer. We can make keys as many as we want. And it exist as a form of counts. For example Mutex is a restroom only with one toilet and semaphore is a restroom with many toilets. So we can make many threads could access to critical section at the same time. It is used for syncronization. As I mentioned, we can make many counts and it means we can make only one key for critical section. We call it binary semaphore and it works like Mutex. But there is one difference between Mutex and semaphore. In Mutex the key could be held only by entreing thread so if entered thread is won't coming out there is no way to open it. However in semaphore the closed door could be opened by ohter thread by changing the value of semaphore.

I think the major cause of time difference is different form of them. Semaphore should change its count at evey time main thread is changed. But Mutex doesn't have to. It can work as just passing the key to next thread right away. 
