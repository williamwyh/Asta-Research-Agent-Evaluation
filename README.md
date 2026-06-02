# Asta: Evaluation and Architectural Exploration of AI Scientific Knowledge Agents

This repository documents my lab work evaluating **Asta**, an automated knowledge agent designed to assist in academic literature research. The study covers performance benchmarking, internal mechanism analysis, and an architectural proposal for future improvements based on citation graph traversal.

## 🚀 Key Findings

### 1. Performance vs. Google Scholar
Through rigorous testing on frontier topics, Asta demonstrated significant advantages:
* **Deep Semantic Alignment:** Accurately maps abstract user requirements to specific technical expressions in literature, outperforming rigid keyword-based search.
* **Breaking "Citation Hegemony":** Successfully retrieves cutting-edge preprints regardless of citation counts, enabling discovery of the latest research.
* **Explainable Evidence:** Provides high-density information extraction with relevant text excerpts attached to specific sub-queries, drastically reducing manual review time.

### 2. Black-Box Analysis
We conducted controlled experiments to probe Asta’s internal workflows:
* **Intent Parsing:** Asta utilizes a ReAct-based planner capable of translating complex natural language requirements into systematic grading rubrics.
* **Semantic Retrieval Bottlenecks:** Asta functions primarily as a semantic engine. Experiments showed it struggles with complex multi-domain reasoning when it attempts to interpret graph-topological tasks through pure vector similarity.
* **Full-Text Constraints:** Limitations in data access (metadata-only APIs) lead to feature dilution, constraining the agent's ability to perform deep, full-text data mining.

## 🛠 Proposed Upgrade: Asta-CG (Citation Graph Traversal)

To overcome the "semantic retrieval ceiling," I proposed integrating **Citation Graph Traversal** into the agent’s pipeline, inspired by the **PaperQA2** architecture.

### The Asta-CG Pipeline:
1. **Semantic Seeding:** Identifying high-relevance anchor papers (RCS ≥ 8).
2. **Omnidirectional Traversal:** Fetching backward references and forward citers via Semantic Scholar & Crossref APIs.
3. **Best-Effort Deduplication:** Normalizing DOIs and titles for unified graph construction.
4. **Overlap Filtering:** Using an overlap ratio ($\alpha$) to prune noise and isolate foundational/central papers.
5. **Graph Centrality Reranking:** Prioritizing citations based on future influence to ensure high-impact results.

## 📂 Repository Structure
- `reports/`: Full lab reports and documentation.
- `data/`: Extracted experimental findings and comparison logs.
- `proposals/`: Technical breakdown of the Citation Graph Traversal upgrade.

## 📑 Citation
This project is based on the findings from:
*Skarlinski, M., et al. (2024). Language agents achieve superhuman synthesis of scientific knowledge. ArXiv, abs/2409.13740.*

---
*Author: William Wu*
*Project Date: June 2026*
