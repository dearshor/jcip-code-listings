# Java Concurrency in Practice - Code Listings

Created: Nov 9, 2020 11:13 PM
URL: https://jcip.net/listings.html

Written by Brian Goetz and Tim Peierls with assistance from members of JCP JSR-166 Expert Group and released to the public domain, as explained by the [Creative Commons public domain license](http://creativecommons.org/licenses/publicdomain).

Note that this license is no longer recommended by Creative Commons for any use, and has never been recommended for use with software. Nevertheless, this is the license that we picked in 2006.

## install annotations jar
```
cd jcip-code-listings

mvn install:install-file -Dfile="./annotations/jcip-annotations.jar" -DartifactId=jcip-annotations -DgroupId=jcip-annotations -Dversion=1.0 -Dpackaging=jar

mvn install:install-file -Dfile="./annotations/jcip-annotations-src.jar" -DartifactId=jcip-annotations -DgroupId=jcip-annotations -Dversion=1.0 -Dpackaging=jar -Dclassifier=sources
```

## Introduction

- 1.1 [Non-thread-safe sequence generator.](src/main/java/net/jcip/examples/UnsafeSequence.java)
- 1.2 [Thread-safe sequence generator.](src/main/java/net/jcip/examples/Sequence.java)

## Thread Safety

- 2.1 [A stateless servlet.](src/main/java/net/jcip/examples/StatelessFactorizer.java)
- 2.2 [Servlet that counts requests without the necessary synchronization.](src/main/java/net/jcip/examples/UnsafeCountingFactorizer.java)
- 2.3 [Race condition in lazy initialization.](src/main/java/net/jcip/examples/LazyInitRace.java)
- 2.4 [Servlet that counts requests using AtomicLong.](src/main/java/net/jcip/examples/CountingFactorizer.java)
- 2.6 [Servlet that caches last result, but with unnacceptably poor concurrency.](src/main/java/net/jcip/examples/SynchronizedFactorizer.java)
- 2.7 [Code that would deadlock if intrinsic locks were not reentrant.](src/main/java/net/jcip/examples/NonReentrantDeadlock.java)
- 2.8 [Servlet that caches its last request and result.](src/main/java/net/jcip/examples/CachedFactorizer.java)

## Sharing Objects

- 3.1 [Sharing variables without synchronization.](src/main/java/net/jcip/examples/NoVisibility.java)
- 3.2 [Non-thread-safe mutable integer holder.](src/main/java/net/jcip/examples/MutableInteger.java)
- 3.3 [Thread-safe mutable integer holder.](src/main/java/net/jcip/examples/SynchronizedInteger.java)
- 3.4 [Counting sheep.](src/main/java/net/jcip/examples/CountingSheep.java)
- 3.5 [Publishing an object.](src/main/java/net/jcip/examples/Secrets.java)
- 3.6 [Allowing internal mutable state to escape.](src/main/java/net/jcip/examples/UnsafeStates.java)
- 3.7 [Implicitly allowing the this reference to escape.](src/main/java/net/jcip/examples/ThisEscape.java)
- 3.8 [Using a factory method to prevent the this reference from escaping during construction.](src/main/java/net/jcip/examples/SafeListener.java)
- 3.9 [Thread confinement of local primitive and reference variables.](src/main/java/net/jcip/examples/Animals.java)
- 3.10 [Using ThreadLocal to ensure thread confinement.](src/main/java/net/jcip/examples/ConnectionDispenser.java)
- 3.11 [Immutable class built out of mutable underlying objects.](src/main/java/net/jcip/examples/ThreeStooges.java)
- 3.12 [Immutable holder for caching a number and its factors.](src/main/java/net/jcip/examples/OneValueCache.java)
- 3.13 [Caching the last result using a volatile reference to an immutable holder object.](src/main/java/net/jcip/examples/VolatileCachedFactorizer.java)
- 3.14 [Publishing an object without adequate synchronization.](src/main/java/net/jcip/examples/StuffIntoPublic.java)
- 3.15 [Class at risk of failure if not properly published.](src/main/java/net/jcip/examples/Holder.java)

## Composing Objects

- 4.1 [Simple thread-safe counter using the Java monitor pattern.](src/main/java/net/jcip/examples/Counter.java)
- 4.2 [Using confinement to ensure thread safety.](src/main/java/net/jcip/examples/PersonSet.java)
- 4.3 [Guarding state with a private lock.](src/main/java/net/jcip/examples/PrivateLock.java)
- 4.4 [Monitor-based vehicle tracker implementation.](src/main/java/net/jcip/examples/MonitorVehicleTracker.java)
- 4.5 [Mutable point class similar to java.awt.Point.](src/main/java/net/jcip/examples/MutablePoint.java)
- 4.6 [Immutable Point class used by DelegatingVehicleTracker.](src/main/java/net/jcip/examples/Point.java)
- 4.7 [Delegating thread safety to a ConcurrentHashMap.](src/main/java/net/jcip/examples/DelegatingVehicleTracker.java)
- 4.8 [Returning a static copy of the location set instead of a 'live' one.](src/main/java/net/jcip/examples/DelegatingVehicleTracker.java)
- 4.9 [Delegating thread safety to multiple underlying state variables.](src/main/java/net/jcip/examples/VisualComponent.java)
- 4.10 [Number range class that does not sufficiently protect its invariants.](src/main/java/net/jcip/examples/NumberRange.java)
- 4.11 [Thread-safe mutable point class.](src/main/java/net/jcip/examples/SafePoint.java)
- 4.12 [Vehicle tracker that safely publishes underlying state.](src/main/java/net/jcip/examples/PublishingVehicleTracker.java)
- 4.13 [Extending Vector to have a put-if-absent method.](src/main/java/net/jcip/examples/BetterVector.java)
- 4.14 [Non-thread-safe attempt to implement put-if-absent.](src/main/java/net/jcip/examples/ListHelpers.java)
- 4.15 [Implementing put-if-absent with client-side locking.](src/main/java/net/jcip/examples/ListHelpers.java)
- 4.16 [Implementing put-if-absent using composition.](src/main/java/net/jcip/examples/ImprovedList.java)

## Building Blocks

- 5.1 [Compound actions on a Vector that may produce confusing results.](src/main/java/net/jcip/examples/UnsafeVectorHelpers.java)
- 5.2 [Compound actions on Vector using client-side locking.](src/main/java/net/jcip/examples/SafeVectorHelpers.java)
- 5.3 Iteration that may throw ArrayIndexOutOfBoundsException. (fragment)
- 5.4 Iteration with client-side locking. (fragment)
- 5.5 Iterating a List with an Iterator. (fragment)
- 5.6 [Iteration hidden within string concatenation.](src/main/java/net/jcip/examples/HiddenIterator.java)
- 5.7  [ConcurrentMap interface.](http://java.sun.com/j2se/1.5.0/docs/api/java/util/concurrent/ConcurrentMap.html#method_summary) (external link to Javadoc)
- 5.8 [Producer and consumer tasks in a desktop search application.](src/main/java/net/jcip/examples/ProducerConsumer.java)
- 5.9 [Starting the desktop search.](src/main/java/net/jcip/examples/ProducerConsumer.java)
- 5.10 [Restoring the interrupted status so as not to swallow the interrupt.](src/main/java/net/jcip/examples/TaskRunnable.java)
- 5.11 [Using CountDownLatch for starting and stopping threads in timing tests.](src/main/java/net/jcip/examples/TestHarness.java)
- 5.12 [Using FutureTask to preload data that is needed later.](src/main/java/net/jcip/examples/Preloader.java)
- 5.13 [Coercing an unchecked Throwable to a RuntimeException.](src/main/java/net/jcip/examples/LaunderThrowable.java)
- 5.14 [Using Semaphore to bound a collection.](src/main/java/net/jcip/examples/BoundedHashSet.java)
- 5.15 [Coordinating computation in a cellular automaton with CyclicBarrier.](src/main/java/net/jcip/examples/CellularAutomata.java)
- 5.16 [Initial cache attempt using HashMap and synchronization.](src/main/java/net/jcip/examples/Memoizer1.java)
- 5.17 [Replacing HashMap with ConcurrentHashMap.](src/main/java/net/jcip/examples/Memoizer2.java)
- 5.18 [Memoizing wrapper using FutureTask.](src/main/java/net/jcip/examples/Memoizer2.java)
- 5.19 [Final implementation of Memoizer.](src/main/java/net/jcip/examples/Memoizer.java)
- 5.20 [Factorizing servlet that caches results using Memoizer.](src/main/java/net/jcip/examples/Factorizer.java)

## Task Execution

- 6.1 [Sequential web server.](src/main/java/net/jcip/examples/SingleThreadWebServer.java)
- 6.2 [Web server that starts a new thread for each request.](src/main/java/net/jcip/examples/ThreadPerTaskWebServer.java)
- 6.3  [Executor interface.](http://java.sun.com/j2se/1.5.0/docs/api/java/util/concurrent/Executor.html#method_summary) (external link to Javadoc)
- 6.4 [Web server using a thread pool.](src/main/java/net/jcip/examples/TaskExecutionWebServer.java)
- 6.5 [Executor that starts a new thread for each task.](src/main/java/net/jcip/examples/ThreadPerTaskExecutor.java)
- 6.6 [Executor that executes tasks synchronously in the calling thread.](src/main/java/net/jcip/examples/WithinThreadExecutor.java)
- 6.7  [Lifecycle methods in ExecutorService.](http://java.sun.com/j2se/1.5.0/docs/api/java/util/concurrent/ExecutorService.html#method_summary) (external link to Javadoc, shows *all* methods, not just lifecycle methods)
- 6.8 [Web server with shutdown support.](src/main/java/net/jcip/examples/LifecycleWebServer.java)
- 6.9 [Class illustrating confusing Timer behavior.](src/main/java/net/jcip/examples/OutOfTime.java)
- 6.10 [Rendering page elements sequentially.](src/main/java/net/jcip/examples/SingleThreadRenderer.java)
- 6.11  [Callable](http://java.sun.com/j2se/1.5.0/docs/api/java/util/concurrent/Callable.html#method_summary) and  [Future](http://java.sun.com/j2se/1.5.0/docs/api/java/util/concurrent/Future.html#method_summary) interfaces. (external links to Javadoc)
- 6.12 Default implementation of newTaskFor in ThreadPoolExecutor. (See JDK source)
- 6.13 [Waiting for image download with Future.](src/main/java/net/jcip/examples/FutureRenderer.java)
- 6.14 QueueingFuture class used by ExecutorCompletionService. (See JDK source)
- 6.15 [Using CompletionService to render page elements as they become available.](src/main/java/net/jcip/examples/Renderer.java)
- 6.16 [Fetching an advertisement with a time budget.](src/main/java/net/jcip/examples/RenderWithTimeBudget.java)
- 6.17 [Requesting travel quotes under a time budget.](src/main/java/net/jcip/examples/TimeBudget.java)

## Cancellation and Shutdown

- 7.1 [Using a volatile field to hold cancellation state.](src/main/java/net/jcip/examples/PrimeGenerator.java)
- 7.2 [Generating a second's worth of prime numbers.](src/main/java/net/jcip/examples/PrimeGenerator.java)
- 7.3 [Unreliable cancellation that can leave producers stuck in a blocking operation.](src/main/java/net/jcip/examples/BrokenPrimeProducer.java)
- 7.4  [Interruption methods in Thread.](http://java.sun.com/j2se/1.5.0/docs/api/java/lang/Thread.html#method_summary) (external link to Javadoc, shows *all* Thread methods, not just interruption-related)
- 7.5 [Using interruption for cancellation.](src/main/java/net/jcip/examples/PrimeProducer.java)
- 7.6 Propagating InterruptedException to callers. (fragment)
- 7.7 [Noncancelable task that restores interruption before exit.](src/main/java/net/jcip/examples/NoncancelableTask.java)
- 7.8 [Scheduling an interrupt on a borrowed thread.](src/main/java/net/jcip/examples/TimedRun1.java)
- 7.9 [Interrupting a task in a dedicated thread.](src/main/java/net/jcip/examples/TimedRun2.java)
- 7.10 [Cancelling a task using Future.](src/main/java/net/jcip/examples/TimedRun.java)
- 7.11 [Encapsulating nonstandard cancellation in a Thread by overriding interrupt.](src/main/java/net/jcip/examples/ReaderThread.java)
- 7.12 [Encapsulating nonstandard cancellation in a task with newTaskFor.](src/main/java/net/jcip/examples/SocketUsingTask.java)
- 7.13 [Producer-consumer logging service with no shutdown support.](src/main/java/net/jcip/examples/LogWriter.java)
- 7.14 Unreliable way to add shutdown support to the logging service. (fragment)
- 7.15 [Adding reliable cancellation to LogWriter.](src/main/java/net/jcip/examples/LogService.java)
- 7.16 Logging service that uses an ExecutorService.
- 7.17 [Shutdown with poison pill.](src/main/java/net/jcip/examples/IndexingService.java)
- 7.18 [Producer thread for IndexingService.](src/main/java/net/jcip/examples/IndexingService.java)
- 7.19 [Consumer thread for IndexingService.](src/main/java/net/jcip/examples/IndexingService.java)
- 7.20 [Using a private Executor whose lifetime is bounded by a method call.](src/main/java/net/jcip/examples/CheckForMail.java)
- 7.21 [ExecutorService that keeps track of cancelled tasks after shutdown.](src/main/java/net/jcip/examples/TrackingExecutor.java)
- 7.22 [Using TrackingExecutorService to save unfinished tasks for later execution.](src/main/java/net/jcip/examples/WebCrawler.java)
- 7.23 Typical thread-pool worker thread structure. (fragment)
- 7.24  [UncaughtExceptionHandler interface.](http://java.sun.com/j2se/1.5.0/docs/api/java/lang/Thread.UncaughtExceptionHandler.html#method_summary) (external link to Javadoc)
- 7.25 [UncaughtExceptionHandler that logs the exception.](src/main/java/net/jcip/examples/UEHLogger.java)
- 7.26 Registering a shutdown hook to stop the logging service. (fragment)

## Applying Thread Pools

- 8.1 [Task that deadlocks in a single-threaded Executor.](src/main/java/net/jcip/examples/ThreadDeadlock.java)
- 8.2  [General constructor for ThreadPoolExecutor.](http://java.sun.com/j2se/1.5.0/docs/api/java/util/concurrent/ThreadPoolExecutor.html#ThreadPoolExecutor(int,%20int,%20long,%20java.util.concurrent.TimeUnit,%20java.util.concurrent.BlockingQueue,%20java.util.concurrent.ThreadFactory,%20java.util.concurrent.RejectedExecutionHandler)) (external link to Javadoc)
- 8.3 Creating a fixed-sized thread pool with a bounded queue and the caller-runs saturation policy. (fragment)
- 8.4 [Using a Semaphore to throttle task submission.](src/main/java/net/jcip/examples/BoundedExecutor.java)
- 8.5  [ThreadFactory interface.](http://java.sun.com/j2se/1.5.0/docs/api/java/util/concurrent/ThreadFactory.html#method_summary) (external link to Javadoc)
- 8.6 [Custom thread factory.](src/main/java/net/jcip/examples/MyThreadFactory.java)
- 8.7 [Custom thread base class.](src/main/java/net/jcip/examples/MyAppThread.java)
- 8.8 Modifying an Executor created with the standard factories. (fragment)
- 8.9 [Thread pool extended with logging and timing.](src/main/java/net/jcip/examples/TimingThreadPool.java)
- 8.10 [Transforming sequential execution into parallel execution.](src/main/java/net/jcip/examples/TransformingSequential.java)
- 8.11 [Transforming sequential tail-recursion into parallelized recursion.](src/main/java/net/jcip/examples/TransformingSequential.java)
- 8.12 [Waiting for results to be calculated in parallel.](src/main/java/net/jcip/examples/TransformingSequential.java)
- 8.13 [Abstraction for puzzles like the 'sliding blocks puzzle'.](src/main/java/net/jcip/examples/Puzzle.java)
- 8.14 [Link node for the puzzle solver framework.](src/main/java/net/jcip/examples/PuzzleNode.java)
- 8.15 [Sequential puzzle solver.](src/main/java/net/jcip/examples/SequentialPuzzleSolver.java)
- 8.16 [Concurrent version of puzzle solver.](src/main/java/net/jcip/examples/ConcurrentPuzzleSolver.java)
- 8.17 [Result-bearing latch used by ConcurrentPuzzleSolver.](src/main/java/net/jcip/examples/ValueLatch.java)
- 8.18 [Solver that recognizes when no solution exists.](src/main/java/net/jcip/examples/PuzzleSolver.java)

## GUI Applications

- 9.1 [Implementing SwingUtilities using an Executor.](src/main/java/net/jcip/examples/SwingUtilities.java)
- 9.2 [Executor built atop SwingUtilities.](src/main/java/net/jcip/examples/GuiExecutor.java)
- 9.3 Simple event listener. (fragment)
- 9.4 [Binding a long-running task to a visual component.](src/main/java/net/jcip/examples/ListenerExamples.java)
- 9.5 [Long-running task with user feedback.](src/main/java/net/jcip/examples/ListenerExamples.java)
- 9.6 [Cancelling a long-running task.](src/main/java/net/jcip/examples/ListenerExamples.java)
- 9.7 [Background task class supporting cancellation, completion notification, and progress notification.](src/main/java/net/jcip/examples/BackgroundTask.java)
- 9.8 [Initiating a long-running, cancellable task with BackgroundTask.](src/main/java/net/jcip/examples/ListenerExamples.java)

## Avoiding Liveness Hazards

- 10.1 [Simple lock-ordering deadlock.](src/main/java/net/jcip/examples/LeftRightDeadlock.java)
- 10.2 [Dynamic lock-ordering deadlock.](src/main/java/net/jcip/examples/DynamicOrderDeadlock.java)
- 10.3 [Inducing a lock ordering to avoid deadlock.](src/main/java/net/jcip/examples/InduceLockOrder.java)
- 10.4 [Driver loop that induces deadlock under typical conditions.](src/main/java/net/jcip/examples/DemonstrateDeadlock.java)
- 10.5 [Lock-ordering deadlock between cooperating objects.](src/main/java/net/jcip/examples/CooperatingDeadlock.java)
- 10.6 [Using open calls to avoiding deadlock between cooperating objects.](src/main/java/net/jcip/examples/CooperatingNoDeadlock.java)
- 10.7 Portion of thread dump after deadlock. (not a code listing)

## Performance and Scalability

- 11.1 [Serialized access to a task queue.](src/main/java/net/jcip/examples/WorkerThread.java)
- 11.2 Synchronization that has no effect. (fragment)
- 11.3 [Candidate for lock elision.](src/main/java/net/jcip/examples/ThreeStooges.java)
- 11.4 [Holding a lock longer than necessary.](src/main/java/net/jcip/examples/AttributeStore.java)
- 11.5 [Reducing lock duration.](src/main/java/net/jcip/examples/BetterAttributeStore.java)
- 11.6 [Candidate for lock splitting.](src/main/java/net/jcip/examples/ServerStatusBeforeSplit.java)
- 11.7 [ServerStatus refactored to use split locks.](src/main/java/net/jcip/examples/ServerStatusAfterSplit.java)
- 11.8 [Hash-based map using lock striping.](src/main/java/net/jcip/examples/StripedMap.java)

## Testing Concurrent Programs

- 12.1 [Bounded buffer using Semaphore.](src/main/java/net/jcip/examples/SemaphoreBoundedBuffer.java)
- 12.2 [Basic unit tests for BoundedBuffer.](src/main/java/net/jcip/examples/TestBoundedBuffer.java)
- 12.3 [Testing blocking and responsiveness to interruption.](src/main/java/net/jcip/examples/TestBoundedBuffer.java)
- 12.4 [Medium-quality random number generator suitable for testing.](src/main/java/net/jcip/examples/XorShift.java)
- 12.5 [Producer-consumer test program for BoundedBuffer.](src/main/java/net/jcip/examples/PutTakeTest.java)
- 12.6 [Producer and consumer classes used in PutTakeTest.](src/main/java/net/jcip/examples/PutTakeTest.java)
- 12.7 [Testing for resource leaks.](src/main/java/net/jcip/examples/TestBoundedBuffer.java)
- 12.8 [Thread factory for testing ThreadPoolExecutor.](src/main/java/net/jcip/examples/TestThreadPool.java)
- 12.9 [Test method to verify thread pool expansion.](src/main/java/net/jcip/examples/TestThreadPool.java)
- 12.10 Using Thread.yield to generate more interleavings. (fragment)
- 12.11 [Barrier-based timer.](src/main/java/net/jcip/examples/BarrierTimer.java)
- 12.12 [Testing with a barrier-based timer.](src/main/java/net/jcip/examples/TimedPutTakeTest.java)
- 12.13 [Driver program for TimedPutTakeTest.](src/main/java/net/jcip/examples/TimedPutTakeTest.java)

## Explicit Locks

- 13.1  [Lock interface.](http://java.sun.com/j2se/1.5.0/docs/api/java/util/concurrent/locks/Lock.html#method_summary) (external link to Javadoc)
- 13.2 Guarding object state using ReentrantLock. (fragment)
- 13.3 [Avoiding lock-ordering deadlock using try Lock.](src/main/java/net/jcip/examples/DeadlockAvoidance.java)
- 13.4 [Locking with a time budget.](src/main/java/net/jcip/examples/TimedLocking.java)
- 13.5 [Interruptible lock acquisition.](src/main/java/net/jcip/examples/InterruptibleLocking.java)
- 13.6  [ReadWriteLock interface.](http://java.sun.com/j2se/1.5.0/docs/api/java/util/concurrent/locks/ReadWriteLock.html#method_summary) (external link to Javadoc)
- 13.7 [Wrapping a Map with a read-write lock.](src/main/java/net/jcip/examples/ReadWriteMap.java)

## Building Custom Synchronizers

- 14.1 Structure of blocking state-dependent actions. (fragment)
- 14.2 [Base class for bounded buffer implementations.](src/main/java/net/jcip/examples/BaseBoundedBuffer.java)
- 14.3 [Bounded buffer that balks when preconditions are not met.](src/main/java/net/jcip/examples/GrumpyBoundedBuffer.java)
- 14.4 [Client logic for calling GrumpyBoundedBuffer.](src/main/java/net/jcip/examples/GrumpyBoundedBuffer.java)
- 14.5 [Bounded buffer using crude blocking.](src/main/java/net/jcip/examples/SleepyBoundedBuffer.java)
- 14.6 [Bounded buffer using condition queues.](src/main/java/net/jcip/examples/BoundedBuffer.java)
- 14.7 Canonical form for state-dependent methods. (fragment)
- 14.8 [Using conditional notification in BoundedBuffer.put.](src/main/java/net/jcip/examples/BoundedBuffer.java)
- 14.9 [Recloseable gate using wait and notifyAll.](src/main/java/net/jcip/examples/ThreadGate.java)
- 14.10  [Condition interface.](http://java.sun.com/j2se/1.5.0/docs/api/java/util/concurrent/locks/Condition.html#method_summary) (external link to Javadoc)
- 14.11 [Bounded buffer using explicit condition variables.](src/main/java/net/jcip/examples/ConditionBoundedBuffer.java)
- 14.12 [Counting semaphore implemented using Lock.](src/main/java/net/jcip/examples/SemaphoreOnLock.java)
- 14.13 Canonical forms for acquisition and release in AQS. (fragment)
- 14.14 [Binary latch using AbstractQueuedSynchronizer.](src/main/java/net/jcip/examples/OneShotLatch.java)
- 14.15 tryAcquire implementation from nonfairReentrantLock. (See JDK source)
- 14.16 tryAcquireShared and tryReleaseShared from Semaphore. (See JDK source)

## Atomic Variables and Nonblocking Synchronization

- 15.1 [Simulated CAS operation.](src/main/java/net/jcip/examples/SimulatedCAS.java)
- 15.2 [Nonblocking counter using CAS.](src/main/java/net/jcip/examples/CasCounter.java)
- 15.3 [Preserving multivariable invariants using CAS.](src/main/java/net/jcip/examples/CasNumberRange.java)
- 15.4 [Random number generator using ReentrantLock.](src/main/java/net/jcip/examples/ReentrantLockPseudoRandom.java)
- 15.5 [Random number generator using AtomicInteger.](src/main/java/net/jcip/examples/AtomicPseudoRandom.java)
- 15.6 [Nonblocking stack using Treiber's algorithm.](src/main/java/net/jcip/examples/ConcurrentStack.java)
- 15.7 [Insertion in the Michael-Scott nonblocking queue algorithm.](src/main/java/net/jcip/examples/LinkedQueue.java)
- 15.8 Using atomic field updaters in ConcurrentLinkedQueue. (fragment)

## The Java Memory Model

- 16.1 [Insufficiently synchronized program that can have surprising results.](src/main/java/net/jcip/examples/PossibleReordering.java)
- 16.2 Inner class of FutureTask illustrating synchronization piggybacking. (See JDK source)
- 16.3 [Unsafe lazy initialization.](src/main/java/net/jcip/examples/UnsafeLazyInitialization.java)
- 16.4 [Thread-safe lazy initialization.](src/main/java/net/jcip/examples/SafeLazyInitialization.java)
- 16.5 [Eager initialization.](src/main/java/net/jcip/examples/EagerInitialization.java)
- 16.6 [Lazy initialization holder class idiom.](src/main/java/net/jcip/examples/ResourceFactory.java)
- 16.7 [Double-checked-locking antipattern.](src/main/java/net/jcip/examples/DoubleCheckedLocking.java)
- 16.8 [Initialization safety for immutable objects.](src/main/java/net/jcip/examples/SafeStates.java)