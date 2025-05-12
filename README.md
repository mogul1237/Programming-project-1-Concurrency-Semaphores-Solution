# Programming-project-1-Concurrency-Semaphores-Solution

Download Here: [Programming project #1 (Concurrency – Semaphores) Solution](https://jarviscodinghub.com/assignment/programming-project-1-concurrency-semaphores-solution/)

For Custom/Original Work email jarviscodinghub@gmail.com/whatsapp +1(541)423-7793

1.- In this assignment you will implement a deadlock free variant of the bounded-buffer producer/consumer using jBACI (C – -). C- – is a subset of C + + that allows you to declare semaphores and apply the operations P and V.

 
In the standard solution with one producer and one consumer, you will need at least three semaphores named:

a)      Full – to stop the producer from producing items when the buffer is full. (initial value n= buffer size)

b)      Empty – to stop the consumer from consuming items from the buffer when the buffer is empty (initial value zero)

c)      Mutex – to allow only one process in the critical section (initial value one)

In this variant of the producer/consumer, there will be one producer (P), one Consumer (C) and one buffer; the size of the buffer is 5.

The producer will produce 20 items and stop running.  

The consumer will consume items from the buffer until the 20 items have been consumed  

 

Project Direction 

You will write the program based on the BACI interpreter. Download jBACI   executable files, example files, and documentation from

 

https://code.google.com/p/jbaci/

 

https://www.weizmann.ac.il/sci-tea/benari/software/jbaci/index.html

 

or you can access a document on the folder JBACI in Webcourses that tells you how to download and install  jBACI on your computer.

 

The BACI support C– programming, which is a subset of C++ extended with primitives for process synchronization (Semaphores and Monitors).  

 

Program example in BACI:

 

line pc

1 0 // example of C– semaphore usage

2 0

3 0 semaphore count; // a “general” semaphore

4 0 binarysem output; // a binary (0 or 1) semaphore for unscrambling output

5 0

6 0 void increment()

7 0 {

8 0 p(output); // obtain exclusive access to standard output

9 2 cout << "before v(count) value of count is " << count << endl; 10 6 v(output); 11 8 v(count); // increment the semaphore 12 10 } // increment 13 11 14 11 void decrement() 15 11 { 16 11 p(output); // obtain exclusive access to standard output 17 13 cout << "before p(count) value of count is " << count << endl; 18 17 v(output); 19 19 p(count); // decrement the semaphore (or stop -- see manual text) 20 21 } // decrement 21 22 22 22 main() 23 23 { 24 23 initialsem(count,0); 25 26 initialsem(output,1); 26 29 cobegin { 27 30 decrement(); increment(); 28 36 } 29 37 } // main       Test your solution   You must run and test your solution for two cases as explain below and compare and comment on the results emitted by each test: a)      Test your first solution b)      Introduce a time delay in the consumer and test your solution. Time delay can be implemented using a dummy loop that iterates, for example,  1000 times
