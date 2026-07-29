# Research Knowledge, Md Omar Faruqe (Riyad)

*Last updated: 2026-07-18. For PhD applications, research internships, the research CV, and the research-experience / publications pages. Shared facts and writing rules live in [README.md](README.md).*

## Contents

1. [Research identity](#1-research-identity)
2. [SREGym: AI for site reliability engineering](#2-sregym-ai-for-site-reliability-engineering)
3. [Publications (verified citations)](#3-publications-verified-citations)
4. [Undergraduate thesis](#4-undergraduate-thesis)
5. [Competitions and rankings](#5-competitions-and-rankings)
6. [Teaching and service](#6-teaching-and-service)
7. [PhD application kit](#7-phd-application-kit)
8. [Research-CV conventions](#8-research-cv-conventions)

---

## 1. Research identity

**Interests (canonical phrasing)**: "AI agents for site reliability engineering and software engineering; NLP for low-resource languages."

Shorthand: AI+SRE, AI+SWE, low-resource NLP. Keep the phrasing plain; "reliability of cloud-native systems" style wording was rejected as not sounding genuine.

**The narrative in one paragraph**: three years of production systems engineering (government-scale Jakarta EE, distributed pipelines, an open-source JVM tool) plus a shared-task NLP publication record, now converging on the question of whether AI agents can operate real systems reliably. The SREGym work is exactly that intersection: it takes someone who has debugged production Kubernetes-adjacent systems to design benchmark scenarios that expose where agents fail. The systems background is not a detour from research; it is the qualification for this research.

---

## 2. SREGym: AI for site reliability engineering

> **Role**: Research Intern, advised by Prof. Tianyin Xu (UIUC), 2026 (formal internship; the title is exact)
> **Project**: SREGym, an open-source benchmark for evaluating AI agents on realistic cloud-native system failures
> **Repo**: github.com/SREGym/SREGym

### Current work: the SREGym v2 paper

Working on the SREGym v2 paper: extending the benchmark from synthetic faults to **real-world failure scenarios**, and analyzing how agents behave on them. Method: case studies and postmortem analysis of real-world outages, projected into reproducible benchmark problems.

Scenario and oracle design targets documented agent failure modes: cross-layer reasoning gaps, greedy diagnosis anchoring, and reward hacking (as characterized in the SREGym and Stratus papers).

### Merged contribution: fault scenario PR #886

- **The incident**: reproduced Kubernetes issue #128162, where multiple mutating admission webhooks' cumulative timeouts exceed the API server's global admission deadline, silently blocking all pod creation. No crash, no obvious error: the control plane just stops admitting pods.
- **Realistic, agent-resistant design**: real HTTPS admission servers and ecosystem-named decoy webhooks (not dummy backends) so agents cannot dismiss the setup, plus a deliberate "near-miss" policy that looks corrective but fails.
- **Reward-hack-resistant oracle**: a four-property mitigation oracle culminating in a fresh probe-pod admission test. It rejects fixes that mask the symptom (for example, deleting all webhooks) without restoring the required control-plane network path.
- **Stack**: Python, Kubernetes (admission webhooks, NetworkPolicy, RBAC), Docker/kind.
- Links: PR github.com/SREGym/SREGym/pull/886; incident github.com/kubernetes/kubernetes/issues/128162.

### Talking points

- Why oracles must be adversarial: an agent that deletes all webhooks "fixes" the symptom; a naive oracle passes it. The probe-pod test checks the system actually admits pods through the restored path.
- Why real-world scenarios over synthetic faults: synthetic faults test detection; real incidents test cross-layer causal reasoning, which is where current agents break.
- Presentation rule (standing): the research entry stays bird's-eye (program framing, role, direction); the concrete merged PR lives under Projects. Verify PR state on GitHub before writing about it anywhere.

---

## 3. Publications (verified citations)

Verified against the ACL Anthology on 2026-07-18. Use these exact citations; bold my name; always label the co-location honestly.

1. **Omar Faruqe Riyad** and Jahedul Alam Junaed. 2025. AdversaryAI at BLP-2025 Task 2: A Think, Refine, and Generate (TriGen) System with LoRA and Self-Refinement for Code Generation. In *Proceedings of the Second Workshop on Bangla Language Processing (BLP-2025)*, pages 629–641, Mumbai, India. Association for Computational Linguistics. (Workshop co-located with IJCNLP-AACL 2025.)
   - First author. Ranked **4th of 32 teams** (Pass@1 0.85).
   - Method: LoRA fine-tuning of Llama 3, TigerLLM, and Qwen; Chain-of-Thought prompting; an execution-guided self-refinement loop that critiques and corrects generated code; error analysis categorizing failures by type (syntax, runtime, misread problem statements).
   - PDF: aclanthology.org/2025.banglalp-1.65.pdf
   - Pitfalls already fixed once, do not reintroduce: the venue is the **Second** Workshop (not Third); publication date is **December 2025** (not January); the co-author is named (never "et al." on a two-author paper); the metric is **Pass@1**, not "accuracy".

2. Trina Chakraborty, Marufur Rahman, and **Omar Riyad**. 2024. Deja Vu at SemEval 2024 Task 9: A Comparative Study of Advanced Language Models for Commonsense Reasoning. In *Proceedings of the 18th International Workshop on Semantic Evaluation (SemEval-2024)*, pages 1239–1244, Mexico City, Mexico. Association for Computational Linguistics. (Co-located with NAACL 2024.)
   - Third author.
   - Method: data augmentation for robustness on the BRAINTEASER lateral-thinking benchmark; comparison of fine-tuned and prompted language models on sentence- and word-level puzzles.
   - PDF: aclanthology.org/2024.semeval-1.180.pdf

3. **Omar Faruqe Riyad**, Trina Chakraborty, and Abhishek Dey. 2023. Team_Syrax at BLP-2023 Task 1: Data Augmentation and Ensemble Based Approach for Violence Inciting Text Detection in Bangla. In *Proceedings of the First Workshop on Bangla Language Processing (BLP-2023)*, pages 247–254, Singapore. Association for Computational Linguistics. (Co-located with EMNLP 2023.)
   - First author. Ranked **12th in post-evaluation** (19th official).
   - Method: semi-supervised self-training against class imbalance; back-translation (Googletrans) for dataset diversity; bagging and majority-voting ensembles of Bangla transformer models.
   - PDF: aclanthology.org/2023.banglalp-1.32.pdf

**Venue framing rule**: these are workshop shared-task system papers. Say "workshop papers co-located with EMNLP 2023, NAACL 2024, and IJCNLP-AACL 2025". Never "published at EMNLP/NAACL"; every professor knows the difference, and the honest label reads as competence, not weakness.

---

## 4. Undergraduate thesis

**Visual Question Answering (VQA) Data Synthesis**, 2022, SUST.

- Addressed the answer-space diversity limitation in VQA v2 by augmenting training data with automatically generated, contextually relevant question-answer pairs (template-based synthesis).
- Surveyed VQA methods to identify where models fall back on answer-frequency bias instead of visual reasoning.
- Demonstrated improved performance on long-tail answer categories, reducing bias toward frequent answers.

---

## 5. Competitions and rankings

Canonical framings (each fact appears once per document; as of 2026-07-29 ranks live in the Honors section on **both** CVs, since the research CV's Publications list is now a concise citation list and its Research Experience entries carry methods, not ranks):

- **4th of 32 teams**, Code Generation in Bangla Shared Task, IJCNLP-AACL 2025, Pass@1 0.85. Leaderboard: noshinulfat.github.io/blp25_code_generation_task/ (plain URL; no `#:~:text=` fragments, they are fragile)
- **6th of 30 teams**, DSI AI Agent Hackathon 2025 (KnowledgeRelay, 24-hour onsite)
- **Ranked 12th in post-evaluation (19th official)**, Violence Inciting Text Detection, BLP 2023. Never "Top 20"
- **11th place**, BUET CSE Fest 2022 AI Contest
- **AMD Hackathon Act II, Track 1** (2026): token-efficient LLM query router. No final leaderboard rank is published, so claim none; the entry earns its place on method (precision-gated cascade, LoRA fine-tuning, LLM-as-judge evaluation harness), not placement. Full deep-dive in [dev-knowledge.md](dev-knowledge.md) §4.4.

---

## 6. Teaching and service

- **Course Instructor**, Dynamic Learning, 2024 to present: authored and teach *Enterprise Web Development with JEE, JSF, and PrimeFaces* (YouTube playlist linked from CV). For academic audiences this is a teaching-experience signal.
- **Volunteer**, IEEE International Conference on Bangla Speech and Language Processing (ICBSLP), 2019. Community service; keep as a one-liner.

---

## 7. PhD application kit

### SOP raw material (the arc)

1. **Systems foundation**: three years building and operating production systems (government-scale Jakarta EE, distributed ML pipelines, an open-source JVM tool used team-wide). I know how real systems fail because I have debugged them.
2. **NLP research track**: three shared-task workshop papers (two first-author), each an exercise in making models work under low-resource constraints: LoRA fine-tuning, self-refinement with execution feedback, semi-supervised learning, ensembling.
3. **Convergence**: SREGym. AI agents for SRE need exactly this combination: systems intuition to design realistic failure scenarios, and ML methodology to evaluate agent behavior rigorously. My merged contribution reproduces a real Kubernetes control-plane incident with an oracle that resists reward hacking; my current work extends the benchmark to real-world failure scenarios for the v2 paper.
4. **Direction**: agents that operate real systems (SRE, software engineering) evaluated against benchmarks that reflect production reality, not synthetic toy faults.

### Evidence checklist per application

- Research CV compiled fresh from `resume/Omar_research_cv/main.tex` (2 pages preferred; see §8 on length)
- Verified citations (§3), Scholar link without `&authuser=2`
- Links that must resolve: SREGym PR #886, PrimeFaces PR #12865, gf repo, leaderboards
- GRE 317/340, TOEFL 104/120: submit through application forms; on the CV they stay as one compact line below CGPA (locked decision)
- Letters: line up three; strongest angles are the research advising relationship, the thesis supervision, and professional engineering leadership. Contact details and drafts stay in the private layer.

### What professors check (from the 2026-07 professor-persona review)

- Author order and full citations. Team-name-only entries hide first-authorship; the citation list is the fix.
- Venue honesty. "Published at EMNLP" for a co-located workshop paper poisons trust in everything else.
- Title accuracy for collaborations. One email can verify any claimed affiliation; keep titles exactly what the advisor would confirm.
- Whether stated research interests match the visible work. Interests must be backed by artifacts (papers, PRs, benchmarks), not aspirations.
- "Studied X" bullets. Reading is not a contribution; only design, build, measure, and publish verbs count.
- The publications page of the portfolio. Sloppy metadata (lowercase titles, "et al." hiding a single co-author, wrong workshop number) reads as carelessness about one's own work.

---

## 8. Research-CV conventions

- **Order**: header (with one-line research interests), Education, Research Experience, Publications, Experience (trimmed to 3 or 4 systems-relevant bullets per job), Projects, Honors, Teaching & Service, Skills.
- **Research Experience** (revised 2026-07-29) holds four entries: SREGym, then one entry per shared task where the contribution was substantial (Code Generation for Bangla, BLP-2025, first author; Violence Inciting Text Detection, BLP-2023, first author), then the undergraduate thesis. Each carries method-level bullets, because a citation list alone hides what was actually done. **Deja Vu / SemEval 2024 stays in Publications only**: the contribution there was small, and padding it would be the kind of inflation the professor review flags.
- **SREGym entry stays bird's-eye** (v2 paper, case studies, scenario and oracle design). The concrete PR #886 specifics live under Projects on both CVs. No sentence appears in both places.
- **Publications** are a concise numbered list: authors (mine bolded), linked title, short venue with honest co-location, year. No pages, no city, no "Association for Computational Linguistics", no method line, no ranks. The full citations in §3 remain the source of truth for application forms and BibTeX.
- **Projects** on the research CV: SREGym fault scenario, LLM query router, KnowledgeRelay, PrimeFaces.
- **Industry experience is evidence of systems skill, not the headline.** Keep EC-BVRS (scale), gf, observability, and a compressed security clause; drop enterprise-CRUD detail (approval workflows, file storage) from this variant. Altri keeps the async 10x rewrite, Postgres job coordination, and the ingestion pipeline; Champion/Challenger was swapped out for the ingestion pipeline on 2026-07-29 as the stronger data-systems bullet, then folded back on as a holdout-gated-promotion clause so the evaluation discipline stays visible to a research reader. **Always state the promotion gate as human-in-the-loop**: a challenger beats the champion on a gold-standard holdout slice and a human signs off. Never phrase it as automatic; the manual gate is a deliberate design choice (valuation is monetary, aggregate metrics hide slice regressions), not missing automation.
- **Length: 2 pages is the preference, not a hard ceiling.** Never delete content to make it fit. If an edit pushes the CV to 3 pages, compile it, see what actually overflows, and **report that to Omar with the candidate cuts before removing anything**. He decides whether to cut, to accept a third page, or to tighten wording instead. Rewording for concision without losing a fact is fine to do unprompted; dropping a bullet, an entry, or a claim is not.
- If cuts are agreed, the usual order to consider is: extra bullets on the older shared tasks, then the thesis second bullet, then the ICBSLP volunteer line. Treat that as a starting proposal, not a mandate.
