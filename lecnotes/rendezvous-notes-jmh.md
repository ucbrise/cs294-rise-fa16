# Disorderly Programming: Rendezvous, Bloom and CALM

We expect you to read, understand, and remember the papers before class. I will not summarize the papers in detail; we will aim higher today. 

Today is atypical of the seminar.  My own idiosyncratic views on data, events, asynchrony, programming, distributed computation ... hopefully good foundation for a chunk of RISE lab systems activity and beyond.

In future sessions, we will read more broadly and students will do much of the presentation. I expect that student presentations will be more tightly tethered in paper details. Today is probably not a good model for most presentations.

## Readings:
1. *P Alvaro, T Condie, N Conway, et al.* 2010. [**BOOM Analytics: Exploring data-centric, declarative programming for the cloud.**](http://db.cs.berkeley.edu/papers/eurosys10-boom.pdf) In Eurosys 2010.
1. *P Alvaro, N Conway, JM Hellerstein, WR Marczak* 2012. [**Consistency Analysis in Bloom: a CALM and Collected Approach.**](http://db.cs.berkeley.edu/papers/cidr11-bloom.pdf) In CIDR 2012.
1. *N Conway, WR Marczak, P Alvaro, et al.* SoCC 2012. [**Logic and lattices for distributed programming**](http://db.cs.berkeley.edu/papers/socc12-blooml.pdf). In SOCC 2012.

## Some local Context, early 2000's
- Will skip this in class ... not enough time.
- NetSys pioneers DHTs ... "Overlay Networks".
	- Ratnasamy/Karp/Shenker's [CAN](http://conferences.sigcomm.org/sigcomm/2001/p13-ratnasamy.pdf), Stoica et al's [Chord](https://scholar.google.com/scholar?cluster=10556342542444957251), Joseph/Kubiatowicz's [Tapestry](https://scholar.google.com/scholar?cluster=6594110041683166008)
	- Is a DHT routing or is it storage?  Is a database index routing or storage? Hmmm!
- DB group building [Telegraph](http://telegraph.cs.berkeley.edu) system
	- *Adaptive* dataflow: data arriving with dynamic delivery rates, unknown distributions
		- [Eddies](https://scholar.google.com/scholar?cluster=13049208738754012194): Query processors as tuple routers
	- [TelegraphCQ](https://scholar.google.com/scholar?cluster=1537661248458276928): Continuous queries over streams
	    - Storage for queries rather than data? What does that imply? More hmm!
- Culler begins [TinyOS](https://scholar.google.com/scholar?cluster=16672264386160627744), Intel Research Berkeley
	- Proto-IoT. Wireless ad hoc sensor networks.
	- OS as "wiring up" event handlers
	- What do sensors do? They pump out data!
	- [TAG](https://scholar.google.com/scholar?cluster=15109435484888639161)/[TinyDB](https://scholar.google.com/scholar?cluster=8626088275659328767): The world as a streaming database.
		- Is data really data? Or evidence?
		- Take 2 (with Guestrin): Model-Driven data acquisition joins in models and closes loops.
			- graphs and networks seem important in this space too...

## Stepping Back: Rendezvous.
- **The Land of Two Mountains**
Once there were two bands of people who lived far apart: the Westers and the Easters.  Between them stood two border mountains: Westborder mountain stood to the east of Westerland, and Eastborder mountain stood to the west of Easterland. A large distance lay between the two mountains. Occasionally these peoples had cause to communicate. To do so, they developed technology they deployed at the top of their border mountains.
	- Smoke Signals -- communication across space!
	- Solitary Watchtower -- communication across space *and* time.  (A.k.a. [hash join](https://en.wikipedia.org/wiki/Hash_join).)
		- Sender persist: the watchfire
		- Receiver persist: the watchwoman
	- The Paired Watchtowers -- communication across space *and* time without coordination  (A.k.a. [symmetric hash join](https://scholar.google.com/scholar?cluster=4337745021863074078).)

- What are some familiar routing problems in computing?
	- Message delivery
	- Event handling
	- Code dispatch (function calls etc)
	- Dataflow: "push" and "pull"
	- Database join
	- Publish/Subscribe systems
	- Most things that computers do other than arithmetic!

- Ask questions:
	- Most are asymmetric. Sender vs. receiver persist? What happens if you flip the paradigm?
	- What is "persistence", really? Must it be continuous? (half-)Infinite? In what domain?
		- Is persistent state a register? A log? Is there a difference between a "stream" and a "table"?
	- How does this relate to physical phenomena? Physics? (Don't ask me.)
	- Given that software is malleable, what can we do for rendezvous that's "hard" physically?

- Language Expressivity: Rendezvous--specifically, logic languages based on relational join--can be shown to have signficant expressive power. A simple language of recursive selection, projection and join over sets and sequences (Semipositive Datalog a.k.a Fixed Points on First Order Logic) *covers all of PTIME* (the [Immerman](https://scholar.google.com/scholar?cluster=1660603149772070343)-[Vardi](https://classes.soe.ucsc.edu/cmps277/Fall08/Papers/vardi-stoc82.pdf) Therem) -- and can be implemented asynchronously via the Paired Watchtower metaphor (see discussion of Bloom below.)

- System Architecture: 

## Declarative Networking, Overlog and P2
- Skip this in class ... not enough time.
- Observations:
	- Networks are highly dynamic.  Should be programmed declaratively
		-  Codd's Data Independence, Hellerstein's Inequality.
	- Good fit. Core functions of the network are state management and routing
	- Routing--i.e. finding paths in a dynamic graph—-is a combination of:
		- recursive queries
		- asynchronous stream query processing
	- *P2* was a language/runtime for overlay networks based on recursive queries and asynch distributed dataflow
		- *Overlog* was the language of P2 -- a distributed, asynchronous query language
	- Interesting technology space, but limited audience...

## BOOM Project
- The Cloud: A new compute platform needs a new programming model. Orders Of Magnitude bigger than anything before it!
	- Question to ponder: how are we doing here, 10 years after AWS launched?
- Declarative Programming: OOM simpler programs
- Professor's Hypothesis: It's time to design a declarative language for the cloud!
- 1st-Year Students' (Alvaro, Conway) desire for validation:
	- Let's test the hypothesis on an existing language: Overlog.
	- Then we'll see!  (a few PhD theses later, we did).


## BOOM Analytics
- Idea: recast distributed programming in a data-parallel programming model
- *Data-centric* system design
- *Declarative* programming. 
	- Managing rendezvous and persistence for the system state!
If you take one thing away from today's lecture, this may be it.


### Overlog/Bloom: Basics
- Datalog heads and bodies: the all-paths example from BOOM Analytics, in Bloom. (You'll find no good documentation of Overlog online, but there's a fairly reasonable set of [docs for Bud], the 
Ruby interpreter for Bloom.)
```ruby
table :links, [:from, :to] => [:cost]
scratch :paths, [:from, :to, :via] => [:cost]


paths <= links{ |l| [l.from, l.to, l.to, l.cost] }
paths <= (links*paths).pairs(:to=>:from) { |l, p| [l.from, p.to, p.from, l.cost + p.cost] }
```
and the distributed version from the paper:
```ruby
table :links, [:from, :to] => [:cost]
scratch :paths, [:from, :to, :via] => [:cost]
channel :pathcomm, [:@from, :to, :via] => [:cost]


pathcomm <~ links{ |l| [l.from, l.to, l.to, l.cost] }
pathcomm <~ (links*paths).pairs(:to=>:from) { |l, p| [l.from, p.to, p.from, l.cost + p.cost] }
paths <= pathcomm
```
- Note how distribution is specified in Bloom -- declarative "placement", i.e. "send"
	- In Overlog this is implicit, via a location specifier on a globally-sharded table 
- Bloom assumptions minimalist!
	- Messaging via unreliable, unordered channels
	- State only visible locally
	- These bare-bones assumptions can be "relaxed" by writing protocols in Bloom and layering!
- Execution: The logical timestep
- Durable tables vs. "scratch" tables vs. "channels"
- "Materialized Views": caches on computations.
- Synchronous Datalog vs. Asynch Overlog/Bloom
	- Imagine Internet routers exploring paths in coordinated, expanding radii. Crazy nonsense, right?
	- Takes some work to prove that the execution model here produces the right answer. But it does, regardless of ordering of asynchronous messages. More on this soon!


### HDFS State
- Table 1 of the paper: pretty straightforward!

#### Metadata Protocol
- For each API command:
	- a single client rule placing messages at the NameNode
	- two/three rules at the NameNode
		1. specify the result (results placed async back at the client)
		2. specify an error message (results placed async back at the client)
		3. update NameNode state tables (results placed in tables at NameNode)

#### Heartbeat Protocol
- Illustrates the use of Periodics
	- Logical tables with tuples that "appear" on a schedule.  Again, in Bloom:
```ruby
# Send all messages in the message queue every 100 msec
periodic :timer, 0.1
channel :chan
table :messageQ

chan <~ (timer * messageQ) { |t, m|  m }
```

#### Language Summary:
- Data-centric state:

> *Having identified the relevant data and captured it in relations, the task of writing code
to coordinate the data was relatively easy and could have been
written fairly quickly* **in any language with good support for
collection types**.

- Declarative programming

> *(a) express paths as simple recursive queries over parent
links, and (b) flexibly decide when to maintain materialized
views (i.e., cached or precomputed results) of those paths
separate from their specification*

- Not so good: global invariants! These aren't trivially checkable via *local rules*.
	- Local rules can be used to *implement* global invariants, but that feels low-level
	- Premonitions of CALM: the desire (?) for distributed coordination

### Systems Validation
#### Availability
- Goal: "hot standby": *consistently* replicated NameNode state
- Paxos implementation in Overlog
	- "Ledgers" (tables), "Decrees" (messages in streams) and "invariants" (logic rules)
	- Basic implementation almost line-for-line from pseudocode!
		- This is a theme in many of the declarative language papers on distributed and network protocols
		- Event specifications with invariants fit quite nicely with these languages
	- Less pretty once you add multiple rounds, liveness checking, and catchup
    - See "I do Declare" workshop paper on distributed protocols in Overlog

- Note: Two layers to data-centricity here!
   - High-level: once everything is in tables, "all" you need to do is replicate tables to get availability
   		- Hot standby: fully consistent replication
   		- Warm standby: simpler consistency (e.g. causal or snapshot)
   - High-level: specification of events, state and invariants is often elegant
   - Lower-level: Implementing consistent replication *protocols* using a data-centric style
	    - Declarative networking languages can be quite nice for this
	    - But it doesn't "feel declarative", at the high level
	    - Is this good or bad?
	    - What does "declarative" mean?
	    	- E.g., what if my declaration for task T has to be: "produce a trace of the execution of algorithm X for task T"? 

#### Scalability
- Almost trivial win of data-centric approach: "Shard" your state tables! (by hash(fqname))
	- And if you replicate, then share each replica.

#### Monitoring/Logging
- In a declarative language, easy to specify invariants
- Monitoring the data movement: application state and messages are closer to application semantics
- Trivial to tap the dataflow: just write another rule with a log in the head
	- Can use syntactic sugar to auto-generate these logging rules
	- Helped by the fact that the internal JOL parser/optimizer is metaprogrammed:
		- Its state is kept in tables and the algorithms implemented in Overlog!
- 1 day to implement code coverage tools!

#### Scheduling in Hadoop
- An embedded DSL scenario, more nice elegant code.

### Big picture
- A lot of the benefit is from hewing to a data-centric philosophy.
	- [Reify](https://en.wikipedia.org/wiki/Reification) all program state as data

> *When you examine the tables we defined to implement HDFS and MapReduce, it
seems natural that the system implementation on top should
be fairly simple,* **regardless of the language used.**

- Also makes interposition easy -- dataflows are easy to re-route
	- Especially nice in a setting where distributed, async dataflow is supported: interposition of remote services.

- We burned our fingers on "distributed tables" in Overlog, and did not use them in BOOM Analytics or Bloom
	- Far better to reason locally, and write protocols to achieve distributed properties
	- Today it seems worthwhile to go back and layer

- A take-away quote

>  One simple lesson of our
experience is that modern hardware enables “real systems” to
be implemented in very high-level languages. We should use
that luxury to implement systems in a manner that is simpler
to design, debug, secure and extend — especially for tricky
and mission-critical software like distributed services.

- Kind of like the argument for GC.
    - But... what makes for simpler distributed programming?!
    - And at what cost?


## CALM & Bloom
### What's hard in distributed programming?
	1. Message reordering ("temporal non-determinism")
	2. Partial failure
	3. Performance variation (relates to (1))
- 2nd and 3rd issues traditionally solved via replication
	- but that only makes the 1st harder!
- Let's focus on the first issue.  What can we do to help?
- Let's think about what's hard with C for a minute
	- E.g. bad pointer errors
		- freed memory
		- array bounds
		- "stray overwrites"
		- bad pointer arithmetic
- How did we help
	1. stronger typing *discourages/forbids risky things*
		- difficult to do stray overwrites, ptr arithmetic
	2. GC conservatively *manages tricky things*
		- no worries about access-after-free or access-before-allocate
		- note that temporal dependencies are especially tricky!
- What's the equivalent in distributed?
	How can we (a) discourage risky things and (b) manage tricky things?
- Well, as a point of reference, let's look at "embarrassingly" easy distributed programming!
	- Queries and Functional pipelines like MapReduce
	- Why easy?
		- Much of is is order-insensitive! 
		- Known results about monotonicity from the stream/distributed query literature.
			- Join queries!
			    - Including the recursive queries we used for path finding!
			- Count/sum queries, a la the [TAG](https://scholar.google.com/scholar?cluster=15109435484888639161) paper.
	    - We're accustomed to simple coordination protocols: blocking operators, barriers for others
	    		- MapReduce.
- In retrospect:
	1. *Message reordering* is one of the trickiest things.  Solution: encourage *disorderly programming* with collection types.
	2. *State update* is one of the riskiest things.  Answer: discourage state update. Constrain updates in time- and value-domains.

#### A note on the Von Neumann model
- The roots of our standard computational models.
- Deeply focused on Order and the State.
- A terrible choice for thinking about distributed systems!
	- And yet we seem to be stuck with it!?

#### A note on Transactions
- Transactions are a *programming model*, not a database feature.
- Based on a general-purpose von Neumann sequential read/write API.
- They shield the programmer from concurrency concerns
	- It's as if you are running in a sequential execution!
- I.e. they preserve the Von Neumann illusion for application developers
	- With nice pretty theory and practical implementations
- But they get quite expensive in distributed and loosely-coupled contexts
	- Require unanimous votes for commit, for example.

- NoSQL/Internet era:
	- Reason about tolerating reordering at application level!
		- Well above the read/write API where we can actually *think*
		- A very nice paper here is Helland/Campbell's [Building on Quicksand](https://scholar.google.com/scholar?cluster=16618321304471660853)
	- [Eventual Consistency](https://scholar.google.com/scholar?cluster=13516383847362211388)
	    - What could go wrong :-)

### Bloom/CALM big idea:
- Can we give application developers tools to reason about reordering robustly at application level?
	- Pretty theory and practical implementations, in the spirit of Transactions?

- This is a *programming model* problem (as Transactions were), at a higher level
	- Nicer for exploiting program semantics than read/write
	- Hard to be as general-purpose as read/write (or is it??)

- Back to data-centric declarative programming!
	- State: 
		- "tables" -- i.e. relations or HashMaps, etc.: *unordered* collections, with unordered operations
		- "streams" -- *unordered* semantics inevitable: every streaming system that assumes order eventually has to support "late arrivals" etc. "Windows" need to be "closed", though. We'll come back to that!
	- Declarative languages: 
		- mappings from unordered collections to unordered collections. Sounds kinda commutative/order-insensitive, no?
		- dataflows are immutable. Again sounds kinda order-insensitive, right?

- Bloom
	- Much like Overlog... BUT
	- No implicitly distributed tables partitioned by LocSpec. Explicitly local tables.
	- Time as a first-class form of data, with syntactic sugar: Now, Next, Async
		- Based on a logic called [Dedalus](https://scholar.google.com/scholar?cluster=4658639044512647014)

- So... when are we order-sensitive, when insensitive?  

## CALM: Consistency As Logical Monotonicity
- Bi-directional theorem (formalized later in a [series](https://scholar.google.com/scholar?cluster=17698312205502058807) [of](https://scholar.google.com/scholar?cluster=8124818622578912111) [papers](https://scholar.google.com/scholar?cluster=5352420254036649723) by Ameloot et al.)
	- Programs are eventually Consistent (without resort to coordination protocols) iff they have a Logically Monotonic implementation.
	- Consistent here means something quite specific: Confluent.  I.e. order-insensitive.
		- Discussion: is this different from Eventual Consistency? If so, is it good?
	- Coordination also means something quite specific
		- This is harder to summarize
		- What is "the communication you do that's not intrinsic to your program"??
	- Monotonicity (in Logic):
		- If you make the input sets "bigger", the output sets get "bigger" (via containment)
Intuition from relational algebra:
	- Select is monotone and order insensitive
	- Project is monotone order insensitive
	- Join/Rendezvous is monotone and order insensitive (if you use enough state!)
	- Set Difference is NOT monotone, and NOT order insensitive
	- All the monotone aggregation functions are order-insensitive.
		- But is aggregation order-insensitive???  See paper:

> *For example, the expression
“MIN(x) < 100” is monotonic despite containing an aggregate, by
virtue of the semantics of MIN and <: once a subset S satisfies this
test, any superset of S will also satisfy it. Many refinements along
these lines exist, increasing the ability of program analyses to verify
monotonicity.*			

## Bloom + Lattices
- A simpler, more ancient take on order insensitivity:
	- "Just program with commutative building blocks!"
		- Sagas and other "long-running transaction" models
		- "ACID 2.0" (Associative, Commutative, Idempotent, Distributed)
		- CRDTs
		- ACID 2.0 and CRDTs: Join semilattices
	- Much easier said than done.
		- Some of the CRDT work degenerates into "my entire program is a CRDT". 
			- If you say so. Basically punts on the problem entirely.
- Meanwhile...
	- Many of the distributed protocols were a pain in Bloom 1.0 due to the lack of monotonicity "beyond sets"
	- Maybe we can "extend" a logic language with simple lattices and get complex programs with guarantees through composition?

- A note on Monotonicity and Lattices
	- We often think of monotonicity as growth along some partial order
		- This is as true for sets as it is for counters
	- A lattice *defines* a partial order!
	- Lattice monotonicity is a generalization of set (relation) monotonicity

- What are the key composition properties of logic?
	- Monotone functions: a < b implies f(a) < f(b)
	- Morphisms: g(a + b) = g(a) + g(b). A subset of the monotone functions are morphisms.
		- "Dataflow" is an exploitation of morphisms on sets... differential computation!
			- think "tuples" flowing between operators
			- or "minibatches"
		- Especially important for iterative/recursive queries (cyclic dataflows) like graphs:
			- don't want to recompute rounds 1..k when computing round k+1!

- It is quite natural to compose lattices in a logic or functional style:
	- for "small" lattices, any monotone functions will do. recompute f(a) as (a) grows.
	- for "big" lattices, want morphisms to enable "flow"

## Examples in the paper: pretty nice!
- vector clocks
- quorums
- A monotonic version of the "shopping cart" from Amazon Dynamo and Bloom
	- This turns out to be a relatively big deal: we are *sealing* discrete components of a dataflow without barriers!
		- Much like closing windows in a stream query engine
		- Used in the Blazes tool for auto-providing consistency in both Bloom and Storm


## Summing Up
- Many systems and computing issues boil down to:
	- Representing state in space and time
	- Rendezvous of state across space and time
	- Patterned "flows" of state through compositions of computatons
- Distributed systems challenge us to do this
	- With non-deterministic ordering of compute and communication
	- With replication for handling partial failure
- Data-centric thinking is the ticket here
	- Not limited to heavyweight synchronous systems like MapReduce and Spark
	- Asynch "dataflow" over streams and tables is quite general
	- Higher-level languages (functional/logical) provides benefits
		- Witness the power of monotonicity analysis as one (very central) example


