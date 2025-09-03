---
layout: default
title: About
permalink: /about/
---


# Vigya Sharma
I'm a Principal Engineer at Amazon Search and a Committer & PMC member for the [Apache Lucene](https://lucene.apache.org/) project. I specialize in building and scaling distributed search systems. The best way to reach me is through a direct message on my [LinkedIn](https://www.linkedin.com/in/vigyasharma/) profile.

.

## Professional Journey

### Amazon Product Search (2021 – Present)
I currently lead technical initiatives in Amazon's Product Search platform, where I architect systems that serve billions of customer queries across billions of products on Amazon's e-commerce platform. My work sits at the intersection of distributed systems, traditional information retrieval and modern AI-powered search, focusing on making search more scalable, intelligent, and responsive to natural language queries.

While specifics of my work are confidential to Amazon, my projects have broadly been in one of the following buckets:

* **Applying Modern ML techniques to Improve Search Quality:** I provide technical vision and oversight for applying machine learned models across different stages of a search request: query understanding, lexical and semantic matching, and relevance ranking and irrelevant result pruning. Working closely with machine learning scientists, I guide the integration of both traditional as well as deep learned models, according to the size and scale of the problems they solve. Examples include bi-encoder models for semantic matching, as well as cross encoder models for relevance ranking and MLPs and traditional smaller models for numerous other search, annotation and pruning tasks. My projects involve optimizing Lucene's aNN layer using techniques like quantization, SIMD, and multi-vectors to achieve memory and compute efficiency at high recall, as well as architecting large scale inference systems for ranking, which run billion-plus parameter models on Amazon scale traffic.

* **Improving Amazon Search for Modern Shopping Experiences:** I drive the strategic initiative to improve search and shopping experience for customers early in their shopping journey. Focusing on customers that don't yet know what they want to purchase, I work to improve product discovery, our understanding of shopping intent, and user experience with multi-faceted shopping missions. I scoped and sponsored the development of a document understanding engine that aligns product knowledge with customer intent. I spearheaded the expansion of Amazon's core search platform to search and rank a wide variety of "non-product" content like videos, articles and RAG evidence stores, including the development of a video understanding pipeline for multi-media content. I lead cross-functional initiatives to develop, identify and integrate information sources that help improve product understanding, like the integration of insights from customer product reviews into Amazon search algorithms, ensuring your search for "breathable running shoes", prefers shoes that customers actually claim were breathable. To ensure these efforts are successful, I also guide teams on the design of appropriate training datasets and evaluation metrics.

* **Scaling and Optimizing the Core Search Engine:** As a Principal Engineer on the core search platform I am responsible for optimizing our Apache Lucene based search engine, while ensuring high availability and fault tolerance. My projects involve making improvements to compute and memory efficiency, as well as resiliency improvements deep in the search engine. As an example, I architected the change to decouple our indexing and search fleets, allowing each to scale  independent of the other. This unlocked the ability to run deep product understanding improvements at indexing time for near-realtime updates, without requiring a corresponding scale-out of our search fleet. By independently scaling indexing, we achieved a 76% reduction in full-crawl time while maintaining system stability.

<br>

### Amazon OpenSearch Service, AWS (2014 – 21)
I find it useful to describe my time in Amazon OpenSearch Service (formerly known as Amazon Elasticsearch Service) in two phases:

**Early Days (2014 – 18):** As founding engineer for the service, I was directly involved in building the service from ground up. I took it to launch, saw it take off, and found everything we'd built get outnumbered and outscaled within a few months – scrambling to change engine parts while the jet was in full throttle! 

I wrote core data plane components to ensure cluster membership, prevent and detect split brain issues, expose and integrate with control plane APIs, and provide failure detection and crash-recovery. I built the observability layer for the managed, cloud native, distributed search engine. Over the next 3 years, I would rewrite the monitoring layer twice, as the service scaled by another order of magnitude each time. This gave me some hard learned lessons on responsive caches, API contracts and limits, efficient aggregations, push v/s pull models, async communication and dividing responsibilities across independently scalable systems. I designed and led an in-memory configuration management system that reduced the time to update cluster access policies from 16 mins to under 3 seconds, while reducing deployment costs by 2x. The framework continues to serve as a vehicle for major configuration changes.

This era was like drinking from a technical firehose, and in three short years, I grew from a "green behind the ears" SDE-1 to an SDE-3 (Senior Engineer) responsible for multiple technical teams.

.

**Later Days (2018 – 21):** Even though the service kept growing at an insane rate, it was now more mature. The org size had grown and we had a lot of help across geographies. As our problems shifted from survival and scaling to deep core innovation, I shifted my focus into  Elasticsearch (later forked into OpenSearch) internals. 

Given the diverse nature of customer scenarios and businesses supported by the service, optimal workload management was a central to ensuring stable, efficient, and cost-effective clusters. This responsibility lies with the 'shard management' engine, which is responsible for shard allocation and movement within OpenSearch. 

Over the next several years, I acted as the area lead for this space, leading multiple technical efforts to optimize cluster performance and scale shard management.

* I was the primary author and inventor of 'allocation constraints framework' – a mechanism to inject optional hints into the complex shard weight calculations that controlled all shard geometry. My work helped mitigate a recurring shard hotspot problem that emerged with skewed scale-outs in some of our largest clusters. The framework was eventually open-sourced as XXX, and has since been extended to support multiple OpenSearch features like segment replication.

* I designed and implemented an extreme scale shard allocator for Ultrawarm – the low cost offering for large scale read only indexes. My work increased cluster scale by 10x, supporting ~500,000 shards per cluster. This work has also since been open-sourced as part of XXX.

* Like most complex systems, OpenSearch (and its underlying JVM) offer a multitude of configurable options that can be tuned to provide workload specific optimizations. Not having to worry about these knobs though, is the primary reason customers opt for a managed cloud service. However, given the diverse set of workloads our service would manage, there was no good one size fits all. 
  
  To address this challenge, I led the cross-functional technical initiative for "Autotune", an intelligent system that combines deep observability and metric collection with intelligent decision making, automatic cluster tuning, and feedback learning loops. The system is 'on' by default for all OpenSearch clusters, and works in the background to tune clusters with workload specific optimizations.

<br>
## Speaking, Writing, and Community Work

### Publications
- ["Introducing Auto-Tune in Amazon ES" - AWS Big Data Blog (2021)](https://aws.amazon.com/blogs/big-data/introducing-auto-tune-in-amazon-es/)
- ["The Elasticsearch Weight Function" - OpenSearch Blog, Linux Foundation (2020)](https://opensearch.org/blog/the-elasticsearch-weight-function/)
- ["Demystifying Elasticsearch Shard Allocation" - AWS Open Source Blog (2019)](https://aws.amazon.com/blogs/opensource/open-distro-elasticsearch-shard-allocation/)

.

### Conference Talks
- **OpenSearchCon NA '25 (Upcoming)**: "Adaptive Refresh Strategies for Large-Scale Search Systems"
- **Community Over Code '24**: "HNSW in Action: Lucene's Secret Sauce for Vector Search"
- **ApacheCon NA '22**: "Decoupling Indexing and Search Scalability"
- **AWS Talk Show '21**: Featured speaker on Auto-Tune for Amazon ES

.

### Others
 * In the summer of '25, served as an industry mentor at Carnegie Mellon University (CMU) for their summer course, ["Applied Software Engineering for the Real World with Distributed Teams"](https://www.cmu.edu/education-office/resources/99-520-course-listings.html).

   It was a uniquely rewarding challenge to introduce college students to a complex open source project like Apache Lucene. Connecting with them and seeing their fresh perspective was a new learning experience for me.

 * I had the honor to serve as Co-Chair for the Search Track at ["Community Over Code, NA. '25"](https://communityovercode.org/schedule/).

<br>
## Open Source Work
As committer and PMC member for Apache Lucene, I develop features, review code, and help shape project direction. Some of my contributions like in Elasticsearch (primarily bug fixes) and [OpenSearch](https://github.com/opensearch-project/OpenSearch), where my past internal projects have been open-sourced. 

Public artifacts for my open source work are readily available on the internet. Below is a living summary of my more notable patches.

.

### **Apache Lucene**
- **Reranking with Late Interaction Model Multi-Vectors:** Late Interaction models, like [ColBERT](https://arxiv.org/abs/2004.12832) and [ColPali](https://arxiv.org/html/2407.01449v2), capture rich semantic interaction between documents and queries, and have been shown to outperform single-vector (no-interaction) models on search relevance. These models operate by using multi-vector representations for query (and document) embeddings.
  
  * One challenge with including late interaction models in search, has been working with multi-vectors at scale. This change provides an efficient workaround, by adding support to rerank results of a query using late interaction multi-vectors. – [lucene#14729](https://github.com/apache/lucene/pull/14729)

  * A `DoubleValuesSource` that scores on full precision vectors can be used on top of quantized knn vector queries to rerank with full precision similarity scores. – [lucene#14708](https://github.com/apache/lucene/pull/14708), [lucene#14776](https://github.com/apache/lucene/pull/14776)

- **Adaptive Refresh for Lucene Searchers:** In segment based replication systems, a large replication payload (checkpoint) can induce heavy page faults, cause thrashing for in-flight search requests, and affect overall search performance.

  A potential way to handle these bursts, is to leverage multiple commit points in the Lucene index. Instead of refreshing to the latest commit for a large replication payload, searchers can intelligently select the commit point that they can safely absorb. By processing through multiple such points, searchers can eventually get to the latest commit, without incurring too many page faults. 
  
  This change lets users define a commit selection strategy, controlling which commit the searcher manager refreshes on. – [lucene#14443](https://github.com/apache/lucene/pull/14443)


- **Full Multi-Vector Support in Approx NN Search (WIP):**

	- **1:** Changes to add deep tensor based support to Lucene vectors. In addition to max-similarity aggregations like parent-block joins, this change supports ColBERT style distance functions that compute interaction across all query and document vector values. Documents can have a variable number of vector values, but to support distance function computations, we require all values to have the same dimension. – [lucene#13525](https://github.com/apache/lucene/pull/13525)

	- **2:** The following PR adds support for independent multi-vectors, i.e. scenarios where a single document is represented by multiple independent vector values. The most common example for this, is the passage-vector search use case, where we create a vector for every paragraph chunk in the document.
	  Currently, Lucene only supports a single vector per document. Users are required to create parent-child relationships with the chunked vectors of a document, and call a ParentBlockJoin query to run passage vector search. This change allows indexing multiple vectors within the same document. – [lucene#14173](https://github.com/apache/lucene/pull/14173)


- **Support for Parent-Join Benchmarks in KNN Search:** We use the passage search use-case with cohere embeddings created from wikipedia. Each parent document corresponds to a wikipedia article, and child documents correspond to paragraphs (chunk) within the article. Embeddings are only present for child documents.

  This change leverages Lucene's `DiversifyingChildrenFloatKnnVectorQuery`, using `exactSearch()` for baseline, and `approximateSearch()` for knn search. Recall is computed by calculating overlap between the two. – [luceneutil#296](https://github.com/mikemccand/luceneutil/pull/296), [luceneutil#283](https://github.com/mikemccand/luceneutil/pull/283)


- **Adding concurrency to add-indexes API:** The `addIndexes(CodecReader...)` API merges all provided readers into a single merge, in one large blocking call. We want to add concurrency here by invoking multiple parallel merges on subsets of readers, in a way that is configurable by users. The merged segments created, can later be merged further in the regular, non-blocking, background merges triggered by Lucene. 
  
  Users are responsible for managing their API run times, by invoking it multiple times with subsets of readers. – [lucene#633](https://github.com/apache/lucene/pull/633)

.

### **OpenSearch:**

- Allocation Constraints Framework:
	- Original issue in Elasticsearch describing the core technique – [ES#43350](https://github.com/elastic/elasticsearch/issues/43350)
	- OpenSearch issue where this was open-sourced – [OpenSearch#487](https://github.com/opensearch-project/OpenSearch/issues/487)
	- Allocation Constraints help simplify shard management in segment replication – [[1]](https://github.com/opensearch-project/OpenSearch/pull/6325#discussion_r1108264474), [[2]](https://github.com/opensearch-project/OpenSearch/issues/6210#issuecomment-1444438462)
- Ultrawarm Shard Allocator:
  - Remote Shards Allocator for Searchable Snapshots: [OpenSearch#4870](https://github.com/opensearch-project/OpenSearch/pull/4870/commits/694c89fd70cf544345b7b370bce7d3498e8587d6)
- Adding support for Late Interaction Models:
  - [OpenSearch#18091](https://github.com/opensearch-project/OpenSearch/issues/18091)

.

### **Miscellaneous:**

- Elasticsearch bug fixes: [1](https://github.com/elastic/elasticsearch/commit/25218733e6b0398ad88c758d0e334f6759f8a168), [2](https://github.com/elastic/elasticsearch/commit/130c832e10738308fed8a1c35321ef722dd521e4)
- Performance Analyzer RCA:
  - Sitting at the heart of Amazon AutoTune, this component is responsible for making cluster tuning decisions. I designed the decision maker and strategy for metrics and decision flow.

<br>
## Education
 - **Master of Technology (M.Tech)** - Computer Science, Indian Institute of Technology, Delhi (2011 – 13)
 - **Bachelor of Technology (B.Tech)** - Computer Science, College of Technology, G.B.P.U.A & T (2007 – 11)
