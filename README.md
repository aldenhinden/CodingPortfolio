Some of Alden's sample [projects](https://aldenhinden.github.io/UW-Coding-Projects/) from the [UW Paul Allen School of Computer Science](https://www.cs.washington.edu/). 

---

<details>
<summary><b>Distributed System:</b> A Java Non-Relational Database Similar to Amazon’s DynamoDB or 
Google’s Spanner</summary><br>
<p>
The quarter-long goal of this project was to build a sharded, linearizable, scalable, fault-tolerant, 
highly available key-value store, with dynamic load balancing and atomic multi-key transactions.
</p>
<p>
The project was primarily written in Java, beginning with the creation of a personalized key-value store. Fault 
tolerance was attempted first with a primary/backup system, wherein two servers act together to 
guarantee no state is lost or altered from the client's perspective. The client talks to the primary, 
who executes after the backup has processed the request as well. The servers interact with a ViewServer 
who tells them who is primary and who is backup at any given time. Linearizability was guaranteed through "exactly
once" semantics, where clients would retry requests on timers and servers use cached results for already executed 
requests. 
</p>
<p>
To guarantee linearizability of commands in the event that the ViewServer goes down, a Paxos protocol 
was then implemented. The version implemented in class was adapted from <a href="https://paxos.systems/">this</a> 
paper. In general, clients send requests to all replicas, of which only the leader of the Paxos group processes, 
then broadcasting the request to all other replicas for consensus. Once consensus on the order of commands has 
been reached, the leader processes the request and replies to the client, with the replicas doing the same, all storing 
commands in their own log which is updated by the leader through heartbeat messages. Servers talk to each other through 
a series of messages that each contain their own functionality, and timers are used to solve network latency issues, 
including message delays, reorders, and drops. "Exactly once" semantics are still guaranteed. 
</p>
<p>
Scalability is addressed by creating a transactional key-value store that can handle sets of client requests, while 
the keys are sharded across the servers using consistent virtual hashing. A ShardMaster manages a sequence of numbered 
configurations describing a set of replica groups and an assignment of shards. Each replica group runs the previously 
implemented Paxos protocol to guarantee linearizability of commands. To help guarantee high availability, the 
ShardMaster will dynamically load balance the store, determining if a new configuration is necessary and redistributing 
shards to new groups as they come and go or as keys become more popular. Lastly, transactions are processed using a 
two-phase commit strategy so that commands can be executed across shard groups. 
</p>
<p>
Please reach out to me via email at aldenhinden@gmail.com or aghs@cs.washington.edu for code. I would be happy to 
discuss this project further as it was one of my favorites, and this is a very succinct description. 
</p>
</details>


<details>
<summary><b>ReWrite:</b> A ChatGPT Integrated PDF Summarizer</summary><br>
Full stack development on a team integrating the ChatGPT API into an Angular CLI website, using prompt engineering and JavaScript web scraping to return summaries of uploaded PDFs. Experience configuring a virtual private server to fully deploy the website using Vultr. Continuous integration and testing experience.
</details>


<details>
<summary><b>Campus Map:</b> A Pathfinding Resource for the UW Campus</summary><br>
Full implementation of Dijkstra’s algorithm to find the shortest path between buildings on UW campus using a personalized, generic graph data structure in Java. Front-end UI integration with HTML and ReactJS. Practice with simple HTTP servers in Java.
</details>


<details>
<summary><b>G333gle:</b> A C/C++ File System Crawler, Indexer, and Search Engine</summary><br>
Created LinkedList and HashMap data structures in C to integrate with C++ index file to serve as back-end of a simple word-matching “mini Google”. Practice with C/C++ HTTP server implementation.
</details>


<details>
<summary><b>PacMan Search:</b> AI Driven Maze Pathfinding in Python</summary><br>
Optimizing maze pathfinding in Python with BFS, DFS, UCS, A* search, Alpha-Beta Pruning, and practice with evaluation functions. Further exploration into reinforcement learning with value iteration, Epsilon Greedy, Q-learning, and particle filtering
</details>