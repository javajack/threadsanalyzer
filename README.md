threadsanalyzer
===============

A simple command to show the top N cpu consuming threads of a JVM process. It merges the jstack output with the cpu usage of each thread from the top unix command output

Usage
===============

threadsanalyer.sh pid [stackTraceLines] [topThreads]

pid: The jvm 

stackTraceLines: # lines of the jvm thread stack trace

topThreads: the top N threads


Example
===============
threadsanalyzer.sh 12510 10 5


*************************************************************************************************************
 11:06:54 up 251 days, 30 min,  1 user,  load average: 3.19, 3.18, 3.24
Analyzing top 5 threads
*************************************************************************************************************
61% [12772] "http-9290-4" daemon prio=10 tid=0x00007f3e94006000 nid=0x31e4 runnable [0x00007f3dd7dfc000]
   java.lang.Thread.State: RUNNABLE
	at java.net.SocketInputStream.socketRead0(Native Method)
	at java.net.SocketInputStream.read(SocketInputStream.java:129)
	at org.apache.coyote.http11.InternalInputBuffer.fill(InternalInputBuffer.java:735)
	at org.apache.coyote.http11.InternalInputBuffer.parseRequestLine(InternalInputBuffer.java:366)
	at org.apache.coyote.http11.Http11Processor.process(Http11Processor.java:814)
	at org.apache.coyote.http11.Http11Protocol$Http11ConnectionHandler.process(Http11Protocol.java:602)
	at org.apache.tomcat.util.net.JIoEndpoint$Worker.run(JIoEndpoint.java:489)
	at java.lang.Thread.run(Thread.java:662)


39% [9533] "http-9290-73" daemon prio=10 tid=0x00007f3e94080000 nid=0x253d runnable [0x00007f3db4747000]
   java.lang.Thread.State: RUNNABLE
	at java.net.SocketInputStream.socketRead0(Native Method)
	at java.net.SocketInputStream.read(SocketInputStream.java:129)
	at org.apache.coyote.http11.InternalInputBuffer.fill(InternalInputBuffer.java:735)
	at org.apache.coyote.http11.InternalInputBuffer.parseRequestLine(InternalInputBuffer.java:366)
	at org.apache.coyote.http11.Http11Processor.process(Http11Processor.java:814)
	at org.apache.coyote.http11.Http11Protocol$Http11ConnectionHandler.process(Http11Protocol.java:602)
	at org.apache.tomcat.util.net.JIoEndpoint$Worker.run(JIoEndpoint.java:489)
	at java.lang.Thread.run(Thread.java:662)


36% [32216] "http-9290-67" daemon prio=10 tid=0x00007f3e94077800 nid=0x7dd8 runnable [0x00007f3dcdedd000]
   java.lang.Thread.State: RUNNABLE
	at java.net.SocketInputStream.socketRead0(Native Method)
	at java.net.SocketInputStream.read(SocketInputStream.java:129)
	at org.apache.coyote.http11.InternalInputBuffer.fill(InternalInputBuffer.java:735)
	at org.apache.coyote.http11.InternalInputBuffer.parseRequestLine(InternalInputBuffer.java:366)
	at org.apache.coyote.http11.Http11Processor.process(Http11Processor.java:814)
	at org.apache.coyote.http11.Http11Protocol$Http11ConnectionHandler.process(Http11Protocol.java:602)
	at org.apache.tomcat.util.net.JIoEndpoint$Worker.run(JIoEndpoint.java:489)
	at java.lang.Thread.run(Thread.java:662)


36% [14957] "repository-pool184899" prio=10 tid=0x00007f3eb0081000 nid=0x3a6d waiting on condition [0x00007f3dccfce000]
   java.lang.Thread.State: TIMED_WAITING (parking)
	at sun.misc.Unsafe.park(Native Method)
	- parking to wait for  <0x0000000641379ad8> (a java.util.concurrent.SynchronousQueue$TransferStack)
	at java.util.concurrent.locks.LockSupport.parkNanos(LockSupport.java:196)
	at java.util.concurrent.SynchronousQueue$TransferStack.awaitFulfill(SynchronousQueue.java:424)
	at java.util.concurrent.SynchronousQueue$TransferStack.transfer(SynchronousQueue.java:323)
	at java.util.concurrent.SynchronousQueue.poll(SynchronousQueue.java:874)
	at java.util.concurrent.ThreadPoolExecutor.getTask(ThreadPoolExecutor.java:945)
	at java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:907)
