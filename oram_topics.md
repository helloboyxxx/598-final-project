# Topics to Explore

### ORAM Types (?)

There are many possible ORAM that we can explore. First, there are a few recommended by professor Heath: 

- **OptORAMa: ** this one is hard. 
- **Circuit ORAM:** "path ORAM" but client is a circuit. 
- **Ring ORAM: ** Constant count. This is a practical improvement to Path ORAM.
- **Parallel ORAM: ** Tree-based Paralled Oram. Check out Jonathan Katz. 

There are some other possible interesting models: 

- **Onion ORAM / Onion Ring ORAM**
- **Weighted ORAM**
- **Two-Server ORAM**
- **Stateless ORAM**



---

### Circuits ORAM

#### [Circuit ORAM: On Tightness of the Goldreich-Ostrovsky Lower Bound](https://eprint.iacr.org/2014/672.pdf) (2014)

We propose a new **tree-based ORAM** scheme called Circuit ORAM. Circuit ORAM makes both theoretical and practical contributions. From a theoretical perspective, Circuit ORAM shows that the well-known Goldreich-Ostrovsky logarithmic ORAM lower bound is tight under certain parameter ranges, for several performance metrics. Therefore, we are the first to give an answer to a theoretical challenge that remained open for the past twenty-seven years. Second, Circuit ORAM earns its name because it achieves (almost) optimal circuit size both in theory and in practice for realistic choices of block sizes. We demonstrate compelling practical performance and show that Circuit ORAM is an ideal candidate for secure multi-party computation applications.

### Ring ORAM

#### [Constants Count: Practical Improvements to Oblivious RAM](https://eprint.iacr.org/2014/997.pdf) (2014)

Oblivious RAM (ORAM) is a cryptographic primitive that hides memory access patterns as seen by untrusted storage. This paper proposes Ring ORAM, the most bandwidth-efficient ORAM scheme for the small client storage setting in both theory and practice. Ring ORAM is the first tree-based ORAM whose bandwidth is independent of the ORAM bucket size, a property that unlocks multiple performance improvements. First, Ring ORAM's overall bandwidth is $2.3 \times$ to $4 \times$ better than Path ORAM, the prior-art scheme for small client storage. Second, if memory can perform simple untrusted computation, Ring ORAM achieves constant online bandwidth ( $\sim 60 \times$ improvement over Path ORAM for practical parameters). As a case study, we show Ring ORAM speeds up program completion time in a secure processor by $1.5 \times$ relative to Path ORAM. On the theory side, Ring ORAM features a tighter and significantly simpler analysis than Path ORAM.



### Onion ORAM 

#### [Onion ORAM: A Constant Bandwidth Blowup Oblivious RAM](https://eprint.iacr.org/2015/005.pdf) (2015)

We present Onion ORAM, an Oblivious RAM (ORAM) with constant worst-case bandwidth blowup that leverages poly-logarithmic server computation to circumvent the logarithmic lower bound on ORAM bandwidth blowup. Our construction does not require fully homomorphic encryption, but employs an additively homomorphic encryption scheme such as the Damg˚ardJurik cryptosystem, or alternatively a BGV-style somewhat homomorphic encryption scheme without bootstrapping. At the core of our construction is an ORAM scheme that has “shallow circuit depth” over the entire history of ORAM accesses. We also propose novel techniques to achieve security against a malicious server, without resorting to expensive and non-standard techniques such as SNARKs. To the best of our knowledge, Onion ORAM is the first concrete instantiation of a constant bandwidth blowup ORAM under standard assumptions (even for the semi-honest setting).



### Onion Ring ORAM 

#### [Onion Ring ORAM: Efficient Constant Bandwidth Oblivious RAM from (Leveled) TFHE](https://eprint.iacr.org/2019/736.pdf) (2019)

... Traditionally, ORAM algorithms assume the server acts purely as a storage device. Under this assumption, ORAM has at least $\log (N)$ bandwidth blowup for $N$ data entries. After three decades of improvements, ORAM algorithms have reached the optimal logarithmic bandwidth blowup. Nonetheless, in many practical use cases, a constant bandwidth overhead is desirable. To this purpose, Devadas et al. (TCC 2016) formalized the server computation model for ORAM and proposed Onion ORAM which relies on homomorphic computation to achieve constant worst-case bandwidth blowup. This line of work is generally believed to be purely theoretical, due to the large overheads of homomorphic computation. In this paper, we present Onion Ring ORAM, the first efficient constant bandwidth ORAM scheme in the single server model, based on the Onion ORAM construction and the leveled version of the TFHE scheme by Chillotti et al.. We propose a series of improvements, most notably including a more efficient homomorphic permutation protocol. We implement Onion Ring ORAM and show that it can outperform state-of-the-art logarithmic-bandwidth ORAM like Path ORAMs and Ring ORAM when the network throughput is limited. Under one setting, our construction reduces monetary cost per access by $40 \%$ and end-to-end latency by $35 \%$ over Ring ORAM.



### Parallel ORAM

#### [An Oblivious Parallel RAM with $O\left(\log ^2 N\right)$ Parallel Runtime Blowup](https://eprint.iacr.org/2016/1141.pdf) (2016)

... Oblivious Parallel RAM (OPRAM) is a PRAM counterpart of Oblivious RAM, i.e., it allows $m$ clients that trust each other to simultaneously access data from a server without revealing their access patterns. The best known OPRAM scheme $[2,3]$ achieves amortized client-server bandwidth of $O\left(\log ^2 N\right)$ per lookup, but they do not achieve perfectly linear access time speedup with clients. In fact, for each access, the blowup for the slowest client (also known as parallel runtime blowup) is $O\left(f(m) \log m \log ^2 N\right), f(m)=\omega(1)$. This implies that, for most accesses, some clients remain idle while others are accessing data. In this work, we show an OPRAM scheme that has parallel runtime blowup of $O\left(\log ^2 N\right)$ while maintaining $O\left(\log ^2 N\right)$ client-server bandwidth blowup for each client.

### Weighted ORAM

#### [Weighted Oblivious RAM, with Applications to Searchable Symmetric Encryption](https://eprint.iacr.org/2023/350.pdf) (2023)

Existing Oblivious RAM protocols do not support the storage of data items of variable size in a non-trivial way. While the study of ORAM for items of variable size is of interest in and of itself, it is also motivated by the need for more performant and more secure Searchable Symmetric Encryption (SSE) schemes.
In this article, we introduce the notion of weighted ORAM, which supports the storage of blocks of different sizes. In a standard ORAM scheme, each data block has a fixed size $B$. In weighted ORAM, the size (or weight) of a data block is an arbitrary integer $w_i \in[1, B]$. The parameters of the weighted ORAM are entirely determined by an upper bound $B$ on the block size, and an upper bound $N$ on the total weight $\sum w_i$ of all blocks - regardless of the distribution of individual weights $w_i$. During write queries, the client is allowed to arbitrarily change the size of the queried data block, as long as the previous upper bounds continue to hold.
We introduce a framework to build efficient weighted ORAM schemes, based on an underlying standard ORAM satisfying a certain suitability criterion. This criterion is fulfilled by various Tree ORAM schemes, including Simple ORAM and Path ORAM. We deduce several instantiations of weighted ORAM, with very little overhead compared to standard ORAM. As a direct application, we obtain efficient SSE constructions with attractive security properties.



### Two-Server ORAM

#### [Simple and Efficient Two-Server ORAM](https://eprint.iacr.org/2018/005.pdf) (2018)

We show a protocol for two-server oblivious RAM (ORAM) that is simpler and more efficient than the best prior work. Our construction combines any tree-based ORAM with an extension of a two-server private information retrieval scheme by Boyle et al., and is able to avoid recursion and thus use only one round of interaction. In addition, our scheme has a very cheap initialization phase, making it well suited for RAM-based secure computation. Although our scheme requires the servers to perform a linear scan over the entire data, the cryptographic computation involved consists only of block-cipher evaluations.

A practical instantiation of our protocol has excellent concrete parameters: for storing an $N$-element array of arbitrary size data blocks with statistical security parameter $\lambda$, the servers each store $4 N$ encrypted blocks, the client stores $\lambda+2 \log N$ blocks, and the total communication per logical access is roughly $10 \log N$ encrypted blocks.



### Stateless ORAM 

#### [Panacea: Non-interactive and Stateless Oblivious RAM](https://eprint.iacr.org/2023/274.pdf) (2023)

Many ORAM designs have been proposed to reduce the computational overhead and bandwidth blowup for the client. A recent work, Onion Ring ORAM (CCS'19), is able to achieve $O(1)$ bandwidth blowup in the online phase using fully homomorphic encryption (FHE) techniques, at the cost of a computationally expensive client-side offline phase. Furthermore, such a scheme can be categorized as a stateful construction, meaning that the client has to locally maintain a dynamic state representing the order of remote database elements.
We present Panacea: a novel design of ORAM based on FHE techniques, that is non-interactive and stateless, achieves $O(1)$ bandwidth blowup, and does not require an expensive offline phase for the client to perform; in that sense, our design is the first of its kind among other ORAM designs. To provide the client with such performance benefits, our design delegates all expensive computation to the resourceful server. We additionally show how to boost the server performance significantly using probabilistic batch codes at the cost of only $1.5 \mathrm{x}$ in additional bandwidth blowup and $3 \mathrm{x}$ expansion in server storage, but less amortized bandwidth. Our experimental results show that our design, with the batching technique, is practical in terms of server computation overhead as well. Specifically, for a database size of $2^{19}$, it takes only 1.16 seconds of amortized computation time for a server to respond to a query. As a result of the statelessness and low computational overhead on the client, and reasonable computational overhead on the server, our design is very suitable to be deployed as a cloud-based privacy-preserving storage outsourcing solution with a portable client running on a lightweight device.

















