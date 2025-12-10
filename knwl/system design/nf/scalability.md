# Scalability

- Strategies that improve or maintain the performance even when load increases.
- A common reason for degradation is increase in load

1. Describing Load
   - Load can be described with a few numbers which is called `load parameters` (The best choice of parameter is based of your system): Request per second, ratio of reads and writes in a db, numbers of simultaneous active users in a chat room, hit rate on a cache, etc.
2. Describing Performance
   - How much is the resource of the computer (CPU, memory, network bandwidth) is affected when laod increases. And, how much increase will be needed?
   - In online systems, `service's response time` (time taken from sending a request and receiving a response) is an important factor.
   - Response time varies,many factors are affecting it such as: more data to process, slow network connection, etc.
   - **Percentiles** are a good metric in response time for getting the distribution rates among users of what they experience. Atihmetic mean is good at getting average, but do not tell how many users experience delay.
   - `Tail Latencies` - High percentiles of response time. (Big companies like Google, AWS, Netflix optmize for p99 and p999, not for the average)
   - `Head-of-line blocking` - A process that blocks other process from completing until it completed first

## **Approaches for Coping with Load**

1. `Scaling up/Vertical Scaling`
   - Upgrading the resource of the server
   - The higher the specs the higher the price, and there is a limit on how much you can upgrade
2. `Scaling out/Horizontal Scaling`
   - Adding more servers, and distributing load among these servers

- In reality, good architecures are a mix of both.
- There are also what we called `elastic` systems where they can scale or add computing resource automatically
- Scaling out is hard for stateful systems so as much as possible opt for a vertical scaling for this and only scale out if its needs demands it.

Source:

1. **Desigining Data-Intensive Application: Chapter 1**
2. https://chatgpt.com/c/69393d82-7d18-8322-9191-b29aa122c013
