Some of Alden's sample [projects](https://aldenhinden.github.io/UW-Coding-Projects/) from the [UW Paul Allen School of Computer Science](https://www.cs.washington.edu/). 

---

<details>
<summary>Distributed System</summary>
The quarter-long goal of this project was to build a sharded, linearizable, scalable, fault-tolerant, 
highly available key-value store, with dynamic load balancing and atomic multi-key transactions; 
this is similar to Amazon’s DynamoDB or Google’s Spanner. 

The project was done in Java, beginning with the creation of a personalized key-value store. Fault 
tolerance was attempted first with a primary/backup system, wherein two servers act together to 
guarantee no state is lost or altered from the clients perspective. The client talks to the primary, 
who executes after the backup has processed the request as well. The servers interact with a ViewServer 
who tells them who is primary and who is backup at any given time. 

To guarantee linearizability of commands in the event that the ViewServer goes down, a Paxos protocol 
was then implemented. 

<img src="/docs/ds/pmmc.png">
</details>

<details>
<summary>ReWrite</summary>
Full stack development on a team integrating the ChatGPT API into an Angular CLI website, using prompt engineering and JavaScript web scraping to return summaries of uploaded PDFs. Experience configuring a virtual private server to fully deploy the website using Vultr. Continuous integration and testing experience.
</details>

<details>
<summary>Campus Map</summary>
Full implementation of Dijkstra’s algorithm to find shortest path between buildings on UW campus using a personalized, generic graph data structure in Java. Front-end UI integration with HTML and ReactJS. Practice with simple HTTP servers in Java.
</details>

<details>
<summary>G333gle</summary>
Created LinkedList and HashMap data structures in C to integrate with C++ index file to serve as back-end of a simple word-matching “mini Google”. Practice with C/C++ HTTP server implementation.
</details>


<details>
<summary>PacMan Search</summary>
Optimizing maze pathfinding in Python with BFS, DFS, UCS, A* search, Alpha-Beta Pruning, and practice with evaluation functions. Further exploration into reinforcement learning with value iteration, Epsilon Greedy, Q-learning, and particle filtering
</details>


<details>
<summary>Census Map</summary>
Practice with Java’s ForkJoinPool framework, using parallelism to compute query responses on a US population map.
</details>