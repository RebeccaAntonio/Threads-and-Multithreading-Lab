<div align="center">
<h1>BCA151 – Threads and Multithreading Laboratory</h1>
  
</div>

<hr>

<div align="center">

<h3>Laboratory Activity 4</h3>

<p><strong>Implementing Threads and Multithreading Using Python and GitHub</strong></p>

<p><strong>Submitted by:</strong><br>
Rebecca Lyn Antonio</p>

<p><strong>Section:</strong> B186</p>

<p><strong>Date:</strong> November 21, 2026</p>

</div>

---

## Laboratory Description

This laboratory demonstrates thread creation, multithreading, thread coordination, and shared-resource management using Python.

## Introduction
Threads allow a program to perform multiple tasks concurrently within a single process. Through Python's threading module, students can create, execute, and manage multiple threads. In this laboratory activity, students will use GitHub to create and manage a Python project that demonstrates thread creation, concurrent execution, thread synchronization, and shared-resource management.

## Tools and Requirements
- GitHub account
- Python 3.x
- Visual Studio Code or another Python editor
- Web browser
- Internet connection

## Laboratory Task
  The activity consists of four tasks:

| Task | Description |
|---:|---|
| 1 | Creating and executing a single thread |
| 2 | Implementing multiple threads |
| 3 | Demonstrating thread synchronization using `join()` |
| 4 | Managing shared resources using thread locks |

## Learning Outcomes
- Create and execute threads.
- Demonstrate concurrent execution.
- Explain thread coordination.
- Apply locks to protect shared resources.
  
## Completed Tasks

## 1. Single Thread
   
   ### Task 1: Creating and Executing a Single Thread
   Output showing the single thread displaying numbers 1 through 5.
   <img width="1917" height="1020" alt="Screenshot 2026-11-21 234546" src="https://github.com/user-attachments/assets/eec8b42e-876c-44d8-ac01-53ac4c300e3c" />
<div align="center">
  Figure 1. Output of the single-thread program
  
</div>

### Output
<img width="197" height="133" alt="image" src="https://github.com/user-attachments/assets/a7a2f4d1-36fe-4e8a-ab81-a7af5d3be36e" />

</div>

### Questions:
1.	What is the purpose of threading.Thread()?
    -	It creates a thread and assigns the function that the thread will run.
2.	What happens when start() is executed?
    -	It starts the thread, so its assigned function runs separately from the main program.
3.	What is the purpose of join()?
    -	It makes the main program wait until the thread finishes.
4.	What happens if join() is removed?
    -	he main program can continue without waiting for the thread. In this example, Python usually keeps running until the non-daemon thread finishes, but the main program may print Program completed. before         the thread has displayed all its numbers.

</div>

## 2. Multiple Threads

   ### Task 2: Implementing Multiple Threads
   Output showing two threads running concurrently. The order of their output may vary.
   <img width="1917" height="1020" alt="Screenshot 2026-11-21 234653" src="https://github.com/user-attachments/assets/e3e41f67-0e1c-4fec-9807-b37c06b30377" />
<div align="center">
  Figure 2. Output of the multiple-threads program

  </div>

### Output
<img width="312" height="526" alt="image" src="https://github.com/user-attachments/assets/822cec83-02a6-425e-a659-e340a29fddc0" />

 </div>
 
### Questions:
1.	How many threads are created in the program?
    -	Two worker threads are created: t1 and t2. The program also has its main thread.
2.	Do the two threads execute independently?
    -	Yes. Each runs its own function, and both can make progress during the same period.
3.	Why might the output order change when the program is executed again?
    -  The operating system schedules the threads, so the timing of their print statements can vary between runs.
4.	What is the difference between sequential and concurrent execution?
    - In sequential execution, one task finishes before the next begins. In concurrent execution, multiple tasks make progress during overlapping periods, with the system switching between them as needed.

 </div>
 
## 3. Thread Synchronization using `join()`

### Task 3: Thread Synchronization Using `join()`
Output showing the main program waiting until the download thread finishes.
<img width="1917" height="1017" alt="Screenshot 2026-11-21 234810" src="https://github.com/user-attachments/assets/5c89c07c-cba0-4b0f-84a7-c4e4a02fd4ec" />
<div align="center">
  Figure 3. Output of the thread synchronization program

   </div>
   
 ### Output
 <img width="266" height="127" alt="image" src="https://github.com/user-attachments/assets/84bca9d7-d4a7-4207-a6b3-f7fc3cc4dcd2" />

 </div>
 
### Question:
1.	Why does the main program wait when join() is used?
    -	Calling t1.join() makes the main thread wait until the download thread finishes.
2.	What happens when join() is removed?
    -	The main thread no longer waits at that point, so it may print Main program continues. before the download finishes. Python usually keeps the process alive until a regular non-daemon thread exits.
3.	In what situations is thread synchronization necessary?
    -	Synchronization is needed when one thread must wait for another to finish or when threads share data or resources that must be accessed in a controlled order.

 </div>
 
## 4. Shared Resource Management using `Lock()`

  ### Task 4: Managing Shared Resources Using Thread Locks
   Output showing the final counter value of 200000 with the lock protecting the shared resource.
   <img width="1917" height="1020" alt="Screenshot 2026-11-21 234846" src="https://github.com/user-attachments/assets/e2217087-5c12-4433-8da1-6986f9db3271" />
<div align="center">
Figure 4. Output of the thread lock program

   </div>

### Output
<img width="220" height="22" alt="image" src="https://github.com/user-attachments/assets/a4b69e23-a9ed-4183-9a08-b03bbad51eb3" />

  </div>
  
### Questions:
1.	What is a shared resource?
    -	A shared resource is data or an object that multiple threads can access, such as the counter variable in this program.
2.	What is a race condition?
    -	A race condition happens when a result depends on the timing or order of multiple threads accessing shared data.
3.	What is the purpose of threading.Lock()?
    -	It creates a lock that lets only one thread at a time enter a protected section of code.
4.	What is a critical section?
    -	A critical section is code that accesses or changes shared data and should be protected from simultaneous access.
5.	Why is synchronization important when multiple threads access shared data?
    -	Synchronization coordinates access so threads don’t interfere with each other, helping prevent incorrect results such as lost counter updates.

 </div>

 ## General Questions:
 1.	What is the difference between a process and a thread?
    -	A process is a running program with its own memory space and resources. A thread is a path of execution within a process. Threads in the same process share memory and resources.
2.	What are the advantages of using multithreading?
    -	Multithreading can let a program make progress on several tasks at once, keep an application responsive during background work, and share data between tasks within the same process.
3.	How does multithreading improve application responsiveness?
    -	A program can handle user input in one thread while another performs a longer task, such as loading or processing data. This helps the interface remain usable while the work continues.
4.	What is the difference between concurrency and parallelism?
    -	Concurrency means multiple tasks make progress over overlapping periods. Parallelism means tasks are actually executing at the same time, typically on different processor cores.
5.	Why is a lock necessary when multiple threads access shared data?
    -	A lock controls access to shared data so only one thread at a time can modify it in a protected section. This helps prevent threads from interfering with each other’s updates.
6.	What might happen if a thread is not properly synchronized?
    -	Threads may use incomplete or outdated data, overwrite each other’s changes, produce inconsistent results, or run in an unintended order.
7.	Can multiple threads execute simultaneously on a single-core processor? Explain.
    -	They can make progress concurrently, but a single core can execute only one thread at a time. The operating system switches between threads quickly, creating the appearance that they run simultaneously.
8.	How does the operating system manage kernel-level threads?
    -	The operating system’s scheduler tracks kernel-level threads and assigns them processor time. It can pause and resume threads, switch between them, and run threads on different cores when available.

<div align="center">

<h3>End of Laboratory Activity 4</h3>

