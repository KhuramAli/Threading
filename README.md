
# JAM Benchmark

## Introduction
This benchmark is an effort to compare lock-synchronized and lock-free softwares. It has simple enough examples using plain C11 and C++17 as well as used some available lock-free data structure libraries, like Boost and embb. https://github.com/siemens/embb
It also includes an attempt to migrate a program from SPLASH-2 Benchmark to lock-free. 

### Explaination of Name
The name of the Benchmark reflects the three members for the effort and motivation. 

#### Motivation and idea: 

Jasmin Jahić

jasmin.jahic@iese.fraunhofer.com

Fraunhofer IESE

Kaiserslautern, Germany


#### Development: 

Khuram Ali 

khuram.ali@aim.com


#### Testing:

Milad Chatrangoon

chatrang@rhrk.uni-kl.de

Technical University of Kaiserslautern

Kaiserslautern, Germany


## Building and running the examples
Please run shell script ./buildall.sh to build all examples with all their dependencies. 
It will also install boost and embb libraries. 
You can run make and make clean in the root directory also.

## Performance measurement
A Script is there which can run all the programs 1000 times based on following criteria, 
* A Linux tool MultiTime is used to run the programs.
* A random delay is introduced between each run.
* A delay of 2 seconds is introduced after complition of each 1000 run as calming period.
* A description of hardware/software platform is entered as header of reslut file
* result file named "test.txt" is stored in each program's folder.

Certainly depanding on hardware the measurement tests can take quite long time to complete. 


There are three catagories of the examples, 

### 1- Same program with lock-synchronized and lock-free,


Multi-producer_Multi-consumer_Lock-free_boost

Multi-producer_Multi-consumer_Lock-Synchronized_boost

Single-Producer_Single-Consumer_RingBuffer_Lock-free_boost

Single-Producer_Single-Consumer_RingBuffer_Lock-Synchronized_boost

Summation_lock_free_cppThread

Summation_lock_synchronzied_cppThread



### 2- Examples with lock-synchronization and lock-free in one program

counter_example_1_pthread

counter_example_2_pthread

lock_and_lockfree



### 3- examples of lock-free data structures

mpmc_queue_lockfree_embb

stack_lockfree_embb

queue_lockfree_boost

spsc_queue_lockfree_boost

### 4- SPLASH-2 Barnes
  including Binary and inputs and code. only one lock is migrated to lock-free C11 atomic. 
  The Original version can be obtained from https://github.com/staceyson/splash2.git
