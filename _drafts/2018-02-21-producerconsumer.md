---
layout: post
title: The Producer-consumer Problem
excerpt: Condensed instructions on how to install and add the latest Android SDK to IntelliJ IDE on macOS
---

This is a dangerous implementation of a critical region. Why?

* An instance of the consumer process is created
* Assume that the buffer is empty.
* Consumer executes line `if (count == 0)`, BUT the scheduler stops the consumer process right at this very moment and schedules a producer process. Note: the consumer did not have the opportunity to go to sleep yet.
* The producer will produce an item and proceed to wake up the consumer once `count == 1` holds true.
* The wakeup signal however, will be lost, because technically the consumer is not yet asleep.
* The producer will continue to produce items until the buffer is full and goes to sleep.
* Both producer and consumer will be asleep forevermore.
* Solution: Wakeup bit?

```C
#define N 100
int count = 0;

/* Producer process */
void producer(void) {
    int item;

    while(true) {
        item = produce_item();
        if (count == N) /* buffer full, can't insert anything */
            sleep();
        insert_item(item);
        count += 1;
        if (count == 1) /* now there are items in the buffer to take from */ 
            wakeup(consumer);
    }
}

/* Consumer process */
void consumer(void) {
    int item;

    while (true) {
        if (count == 0) /* buffer empty, nothing to take */
            sleep();
        item = remove_item();
        count -= 1;
        if (count == N - 1) 
            wakeup(producer);
        consume_item(item);
    }
}
```

What is a better approach? This one with semaphores.
The critical region that is just to be accessed by one process at a time is each encapsulated within a `down`- and `up`-call of our binary semaphore to maintain the mutual exclusion of the producer and consumer process.

```C
#define N 100
typedef int semaphore;

semaphore mutex = 1;
semaphore empty = N;
semaphore full = 0;

/* Producer process */
void producer(void) {
    int item;

    while(true) {
        item = produce_item();
        down(&empty);
            down(&mutex);
                insert_item(item);
            up(&mutex);
        up(&full);
    }
}

/* Consumer process */
void consumer(void) {
    int item;

    while (true) {
        down(&full);
            down(&mutex);
                item = remove_item();
            up(&mutex);
        up(&empty);
        consume_item(item);
    }
}
```
