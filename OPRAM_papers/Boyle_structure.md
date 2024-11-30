### What is ORAM?



### Tree based ORAM

<span style="color:#28a745">Definition</span> Cell, Bucket, 

Focus on tree based ORAM. 

Path ORAM.



### What is PRAM?

Goal: a combination of RAM and circuits:

- RAM handels random access, but is sequential. 
- Circuits handles parallelism, but not random access.

Want the best of both. 

# Oblivious Parallel RAM and Applications

> Authors: Boyle, Chung, Pass

### Assumptions

- Clients are mutually trusted. 
- Clients may have internal communications, but can be seen by server.

### Protocol Sketch

1. Parallel memory lookups
   - For accesses that collides, only one client performs the access, others perform dummy access.
   - This requires some **communication** between clients.
2. Parallel “put-backs”
   - In tree-based ORAM, we insert data in the root. But it is problematic when root size $<$ # client. 
   - Insert data in lower level (where # bucket $\geq$​ # client).
   - Requires some reshuffle. **Communication**!
3. Preventing overﬂows / Flush
   - Each client flush independently. All random $\implies$ natually oblivious.
   - Conflict resolved by **communication**. 

### Protocal Sketch

**Protocal:** $\operatorname{Access}\left(\mathrm{op}_i, \operatorname{addr}_i, v_i^{\prime}\right)$​

**Input:**
$$
\begin{cases}
\operatorname{op}_i \in  \{\text{Read, Write}\}\\
\operatorname{addr}_i = \text{cell address to access}\\
v_i^\prime = \text{data to be written in the cell at } \operatorname{addr}_i
\end{cases}
$$

**Output:**

- $v_i^\prime$ will be written if operation is Write.
- Outputs $\operatorname{Pos}(\operatorname{addr}_i)$.




1. Conﬂict Resolution: 
   - Each queried block $b$ has one unique representative.
2. Recursively Access to Position Map:
   - $\ell_i \leftarrow \operatorname{Access}\left(t+1,\left(b_i, \ell_i^{\prime}\right)\right)$
   - We get the original path that leads to $b_i$



### Difference



