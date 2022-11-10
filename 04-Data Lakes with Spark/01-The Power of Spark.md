# Introduction

## Why Spark?

- Spark is currently one of the most popular tools for big data analytics. 
- You might have heard of other tools such as Hadoop. Hadoop is a slightly older technology although still in use by some companies. 
- Spark is generally faster than Hadoop, which is why Spark has become more popular over the last few years.
- There are many other big data tools and systems, each with its own use case. For example, there are database system like **Apache Cassandra** and SQL query engines like ****Presto**. 
- But Spark is still one of the most popular tools for analyzing large data sets.

## What is Big Data?

- We can know we are working with big data if it is more easier to work with distributed system of multiple computers (100's of servers rented from AWS) rather than single system
- We need to understand modern hardware capabilities
    - How long does it take CPU do add two numbers?
    - How quickly can u look up an appointment if it is already cached in computer memory?
    - How long does it take to load up a song from SSD storage?
    - How much data can you download from Netflix in a minute?
- Knowing answers to these type of questions is critical. Data community often refers to these as **Numbers everyone should know**
-  Understanding these components helps determine whether you are working on a "big data" problem or if it's easier to analyze the data locally on your own computer.
    - **CPU (Central Processing Unit)** : The CPU is the "brain" of the computer. Every process on your computer is eventually handled by your CPU. This includes calculations and also instructions for the other components of the compute.

    - **Memory (RAM)** : When your program runs, data gets temporarily stored in memory before getting sent to the CPU. Memory is ephemeral storage - when your computer shuts down, the data in the memory is lost.

    - **Storage (SSD or Magnetic Disk)** : Storage is used for keeping data over long periods of time. When a program runs, the CPU will direct the memory to temporarily load data from long-term storage.

    - **Network (LAN or the Internet)** : Network is the gateway for anything that you need that isn't stored on your computer. The network could connect to other computers in the same room (a Local Area Network) or to a computer on the other side of the world, connected over the internet.

    - **Other Numbers to Know?**
        - You may have noticed a few other numbers involving the L1 and L2 Cache, mutex locking, and branch mispredicts. 
        - If you're curious to learn more, check out [Peter Norvig's original blog post](https://norvig.com/21-days.html) from a few years ago, and an [interactive version](https://colin-scott.github.io/personal_website/research/interactive_latency.html) for today's current hardware.

- Below is average specs for a laptop we can buy

- We need to focus on 4 components : CPU, RAM, SSD/HDD, Network
- Order of speed of these 4 components (fastest to slowest)
    1. CPU
    2. RAM
    3. SSD
    4. Network

## CPU

- The CPU is the brains of a computer. 
- The CPU has a few different functions including directing other components of a computer as well as running mathematical calculations. 
- The CPU can also store small amounts of data inside itself in what are called registers. These registers hold data that the CPU is working with at the moment.
- For example, say you write a program that reads in a 40 MB data file and then analyzes the file. When you execute the code, the instructions are loaded into the CPU. The CPU then instructs the computer to take the 40 MB from disk and store the data in memory (RAM). If you want to sum a column of data, then the CPU will essentially take two numbers at a time and sum them together. The accumulation of the sum needs to be stored somewhere while the CPU grabs the next number. This cumulative sum will be stored in a register. The registers make computations more efficient: the registers avoid having to send data unnecessarily back and forth between memory (RAM) and the CPU.

### Time for Execution

- A 2.5 Gigahertz CPU means that the CPU processes 2.5 billion operations per second. Let's say that for each operation, the CPU processes 8 bytes of data. How many bytes could this CPU process per second? 
- **ANS:** 20 billion bytes per second

### Analyzing a full day of Tweets

- Twitter generates about 6,000 tweets per second, and each tweet contains 200 bytes. So in one day, Twitter generates data on the order of:
- (6000 tweets / second) x (86400 seconds / day) x (200 bytes / tweet) = 104 billion bytes / day
- Knowing that tweets create approximately 104 billion bytes of data per day, how long would it take the 2.5 GigaHertz CPU to analyze a full day of tweets?
- **ANS:** 5.2seconds

## Memory (RAM)

## Storage

## Network

## Key Ratios

- Knowing these ratios will help us decide if we need distributed system or can use local machine for our computation

# Image

## Small Data Numbers

- One of the problem in data processing is the data extraction, pulling out just the data we need

## Big Data Numbers
## Medium Data Numbers
## History of Distributed Computing
## The Hadoop Ecosystem
## MapReduce
## Hadoop MapReduce [Demo]
## The Spark Cluster
## Spark Use Cases