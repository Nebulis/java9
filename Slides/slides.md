# Java 9
## What's coming


### Roadmap

61 JEPS targeted, 1 proposed

* 18/03/2014 -> Java 8 <!-- .element: class="done" -->
* 10/12/2015 -> <!-- .element: class="progress" --> [Feature Complete](http://openjdk.java.net/projects/jdk8/milestones#Feature_Complete) <!-- .element: class="progress" -->
* 04/02/2016 -> <!-- .element: class="todo" --> [All Tests Run](http://openjdk.java.net/projects/jdk8/milestones#All_Tests_Run)<!-- .element: class="todo" -->
* 25/02/2016 -> <!-- .element: class="todo" --> [Rampdown Start](http://openjdk.java.net/projects/jdk8/milestones#Rampdown_start)<!-- .element: class="todo" -->
* 21/04/2016 -> <!-- .element: class="todo" --> [Zero Bug Bounce](http://openjdk.java.net/projects/jdk8/milestones#Zero_Bug_Bounce)<!-- .element: class="todo" -->
* 16/06/2016 -> <!-- .element: class="todo" --> [Rampdown Phase 2](http://openjdk.java.net/projects/jdk8/milestones#Rampdown_phase_2)<!-- .element: class="todo" -->
* 21/07/2016 -> <!-- .element: class="todo" --> [Final Release Candidate](http://openjdk.java.net/projects/jdk8/milestones#Final_Release_Candidate)<!-- .element: class="todo" -->
* 22/09/2016 -> <!-- .element: class="todo" --> [General Availability](http://openjdk.java.net/projects/jdk8/milestones#General_Availability)<!-- .element: class="todo" -->

Note:
JEP = JDK Enhancement Proposal, available to JDK committers



### JEP 102: Process API Updates


Java 8

```java
Process proc = Runtime.getRuntime().exec(new String[]{ "/bin/sh", "-c", "echo $PPID" });

if (proc.waitFor() == 0)
{
  InputStream in = proc.getInputStream();
  int available = in.available();
  byte[] outputBytes = new byte[available];

  in.read(outputBytes);
  String pid = new String(outputBytes);

  System.out.println("Your pid is " + pid);
}
```


Java 9

```java
System.out.println("Your pid is " + Process.getCurrentPid());
```


Goals
* get current PID JVM
* get system processes
* handle process trees
* handle subprocesses with multiplexing



### JEP 110: HTTP/2 Client


HttpURLConnection API issues 
* API predates HTTP/1.1 and is too abstract
* Hard to use, with many undocumented behaviors
* It works in blocking mode only (i.e., one thread per request/response).


Goals
* Asynchronous notification mechanism (headers received, body received)
* Websocket 
* HTTP/2
  * ability to upgrade from 1.1
  * server push
* HTTPS/TLS support



### JEP 201: Modular Source Code
### JEP 220: Modular Run-Time Images
Jigsaw



### JEP 222: jshell: The Java Shell (Read-Eval-Print Loop)
Kulla



### JEP 223: New Version-String Scheme



### JEP 226: UTF-8 Property Files
Alleluia !



### JEP 238: Multi-Release JAR Files




