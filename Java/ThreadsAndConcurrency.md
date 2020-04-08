# Thread

- Every java program has a default thread.
- A thread is an independent path of code execution within a program.
- Many thread can run concurrently in java program , also known as multitasking.
- Threads can be used to run time intensive tasks and run them into background, this allow the application to remain responsive to it’s users

- Each thread executes a runnable object
- Runnables are objects encapsulate code sequence
- Thread can initiate an Asynchrnous task.
- Asnchronous indicates that  it can run concurrently.

- The JVM gives each thread its own private JVM stack. (Which is basically its own private area of memory)
- This prevents thread from interfering with each other.
- The stack holds local variables and partial results
- It also track next instruction to be executed and plays part in calling methods and handling return values.


- Threads are either daemon or non-daemon
- Daemon threads don’t stop the JVM  from ending.
- Threads by default are non-daemon threads.

- Java garbage collection runs on a daemon thread
- A daemon thread is created by calling setDaemon(true)
- Main-Thread is a non-daemon thread
- The program ends when all non-daemon threads have died

### Thread state
- NEW - created but not started
- RUNNABLE - a thread executing in JVM
- BLOCKED - blocked waiting for a monitor to be unlocked
- WATING - waiting to be notified to continue
- TIMED_WAITING - waiting with a Time limit
- TERMINATED - a thread that has completed execution

- name
- alive/dead
- priority
- execution state
- daemon/non-daemon status

### Static Methods 
- activeCount() - return estimated number of threads in current threads thread group and it's sub group
- currentThread() - return reference of current thread
- enumerate(Thread[] Starr) - list of active threads
- sleep(long millis) - sleep or stop execution

### Concreate Methods
- join() - waits for this thread to die.
- join(long milllis) - max wait time for this thread to die.
- interrupt() - use to stop the thread
- start() - start the thread to be run

### Multithreaded Application Problem
- Thread interaction can cause problems
- Race condition, data races, and cached variable problem
- These make an app thread-unsafe
- Increase complexity, debugging much more difficult
- Reliance on synchronization can impact scalability
- A race condition occurs when threads depend on relative timing by the scheduler
- A data race occurs when two or more threads access the same memory location.


### Synchronization
- Synchronization can be used to solve race condition, data races and cached variable problem.
- Prevent two threads from accessing a critical section 
- Ensures the thread can safely update the shared variable 
- can be applied on methods or code blocks
- Synchronization code known as critical sections.
- JVM supports synchronization via monitors
- Every Java object associated with a monitor
- Before a thread enters a critical section, It must get a lock on the monitor.
- If the monitor is already locked, the thread is blocked.
- Shared variables are copied into the thread's working memory
- this ensures access to most recent values
- when done, it writes values back to the main memory


### Wait and Notify
- wait()  // until another thread invoke notify() or notifyAll() for this object 
- wait(long millis) // until this time duration or notify() or notifyAll() 
- wait(long millis, long nano) // for fine precision
- notify() // wakes up a single thread that's waiting on this object's monitor
- notifyAll() // wakes up all threads that are waiting on this objects monitor
- The API uses the objects condition queue
- A condition queue stores the threads that are in a wait state
- The waiting threads known as wait set
- The current thread must own the object's monitor
- then it can invoke these methods
- Otherwise, an IlleagalMonitorStateException is thrown.


### DeadLock
- Two or more threads blocked forever waiting for each other.


# Concurrency

## Concurrency Utilities
- Offer a powerful and extensive framework for threads
- Includes a high-performance thread pool
- A framework for asynchronous task
- Collection classes optimized for concurrent access

### Advantage
- Reduced Programming effort
- Increased performance
- Increased reliability
### Utility includes
- Task scheduling framework such as executors
- Fork/join Framework
- Concurrent collection (newQueue, BlockingQueue, BlockingDequeue and concurrent implementation of map, list and queue)
- Atomic variables
- Synchronizers
- Locks
- Nanosecond granularity timing

## Executors
- Defines a high-level API to manage threads
- Provides thread pool management
- Separate thread creation and management from main thread
- Uses worker thread to minimize overhead

### Executor interfaces
- Executor - support launching new tasks
- ExecutorService - add features to manage lifecycle
- ScheduledExecutorService - supports future and periodic tasks

## Synchronizers
- Latches
- Barriers
- Semaphores
- Exchangers

### CountDownLatch
- It causes one or more threads to wait at a "gate"
- Another thread opens the gate
- It contains count value and the logic to decrement the count until it reaches zero.
- await() - This forces the calling thread to wait until the latch counted down to zero.
- boolean await(long timeout, TimeUnit) - This forces the calling thread to wait until the latch count down to zero or the specified timeout value in unit timeunit has expired.
- void countdown() - decrement the count and releasing all waiting threads when count reaches zero.
- long getCount() -  returns the current count

## Locking Framework
- Lock, ReentrantLock
- Condition
- ReadWriteLock, ReentrantReadWriteLock

### Lock Methods
- lock() - this acquire the locks
- lockinturraptibly()
- Condition newCondition()
- boolean tryLock() , boolean tryLock(long time, TimeUnit t)
- void unlock() releases the lock
