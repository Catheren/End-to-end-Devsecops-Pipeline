This repository contains a Jenkins pipeline configuration for a DevSecOps CI/CD process. The pipeline includes stages for compiling code, running static and dynamic security analysis, building Docker images, and performing container security scans.

_**Note:**EasyBuggy is a broken web application to understand the behavior of bugs and vulnerabilities, for example, [memory leak, deadlock, JVM crash, SQL injection and so on](https://github.com/k-tamura/easybuggy#clock4-easybuggy-can-reproduce)._

##Table of Contents
1. [Prerequisites](#Prerequisites)
2. [Pipeline Stages](#Pipeline-Stages)
3. [Compile and Run Sonar Analysis](#Compile-and-Run-Sonar-Analysis)
4. [Build](#Build)
5. [Run Container Scan](#Run-Container-Scan)
6. [Run Snyk SCA](#Run-Snyk-SCA)
7. [Run DAST Using ZAP](#Run-DAST-Using-ZAP)
8. [Usage](#Usage)
9. [Credentials](#Credentials)
10. [Contributing](#Contributing)
11. [License](#License)

 I have used the following tools in this project to implement the pipeline:
- SonarQube for SAST
- Snyk for Container Scan
- Snyk's SCA tool integrated with Maven for Software Composition Analysis
- DAST using ZAP

Other tools used in this example are Jenkins (Local host) and Maven for orchestration and bui

EasyBuggy Vulnerable Web App Modified 
=

EasyBuggy is a broken web application in order to understand behavior of bugs and vulnerabilities, for example, [memory leak, deadlock, JVM crash, SQL injection and so on](https://github.com/k-tamura/easybuggy#clock4-easybuggy-can-reproduce).


:clock4: Quick Start
To run EasyBuggy, perform the following steps:
-

    $ mvn clean install

( or ``` java -jar easybuggy.jar ``` or deploy ROOT.war on your servlet container with [the JVM options](https://github.com/k-tamura/easybuggy/blob/master/pom.xml#L204). )

Access to

    http://localhost:8080

:clock4: Quick Start(Docker)
-

    $ docker build . -t easybuggy:local # Build container image
    $ docker run -p 8080:8080 easybuggy:local # Start easybuggy

Access to

    http://localhost:8080

### To stop:

  Use <kbd>CTRL</kbd>+<kbd>C</kbd> ( or access to: http://localhost:8080/exit )



:clock4: EasyBuggy can reproduce:
-

* Troubles

  * Memory Leak (Java heap space)
  * Memory Leak (PermGen space)
  * Memory Leak (C heap space)
  * Deadlock (Java)
  * Deadlock (SQL)
  * Endless Waiting Process
  * Infinite Loop
  * Redirect Loop
  * Forward Loop
  * JVM Crash
  * Network Socket Leak
  * Database Connection Leak
  * File Descriptor Leak 
  * Thread Leak 
  * Mojibake
  * Integer Overflow
  * Round Off Error
  * Truncation Error
  * Loss of Trailing Digits

* Vulnerabilities

  * XSS (Cross-Site Scripting)
  * SQL Injection
  * LDAP Injection
  * Code Injection
  * OS Command Injection (OGNL Expression Injection)
  * Mail Header Injection
  * Null Byte Injection
  * Extension Unrestricted File Upload
  * Size Unrestricted File Upload
  * Open Redirect
  * Brute-force Attack
  * Session Fixation Attacks
  * Verbose Login Error Messages
  * Dangerous File Inclusion
  * Directory Traversal
  * Unintended File Disclosure
  * CSRF (Cross-Site Request Forgery)
  * XEE (XML Entity Expansion)
  * XXE (XML eXternal Entity)
  * Clickjacking

* Performance Degradation

  * Slow Regular Expression Parsing
  * Delay of creating string due to +(plus) operator
  * Delay due to unnecessary object creation

* Errors

  * AssertionError
  * ExceptionInInitializerError
  * FactoryConfigurationError
  * GenericSignatureFormatError
  * NoClassDefFoundError
  * OutOfMemoryError (Java heap space) 
  * OutOfMemoryError (Requested array size exceeds VM limit)
  * OutOfMemoryError (unable to create new native thread)
  * OutOfMemoryError (GC overhead limit exceeded)
  * OutOfMemoryError (PermGen space)
  * OutOfMemoryError (Direct buffer memory)
  * StackOverflowError
  * TransformerFactoryConfigurationError
  * UnsatisfiedLinkError

