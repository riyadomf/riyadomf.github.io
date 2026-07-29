# Knowledge Base, Md Omar Faruqe (Riyad)

*Last updated: 2026-07-18. Supersedes `~/Documents/personal-notes/career-kb.md` for facts, bullets, stories, and citations.*

This is the workshop. The portfolio site, both CVs, cover letters, and SOPs are *outputs* of this folder. Update here first, then propagate.

> **PUBLIC ARTIFACT.** This folder is committed to the public portfolio repo. It is excluded from the Jekyll build (`docs` in `_config.yml` exclude), so it never renders on the site, but anyone can read it on GitHub. Everything here must pass the sanitization rules below.

## Sanitization rules (what may never enter this folder)

1. No phone number or home address.
2. No client-confidential security findings or anything covered by an employer NDA.
3. No private-repository file paths or line numbers.
4. No compensation targets or negotiation notes.
5. No interview strategy or candid self-assessment written for my own eyes.
6. Employer project internals only at the level already published on the portfolio or CVs.

Anything in those categories lives in the **private layer**: `~/Documents/personal-notes/career-kb.md` (local-only, never committed anywhere).

## Files

| File | What it holds | Use it when |
|---|---|---|
| [dev-knowledge.md](dev-knowledge.md) | Experience deep-dives, STAR stories, technical deep-dives, CV bullet pool, skills matrix | Applying for engineering jobs; updating the dev CV, job-experience, projects, or skills pages |
| [research-knowledge.md](research-knowledge.md) | SREGym research, verified publication citations, thesis, rankings, PhD application kit | Applying for PhD programs or research internships; updating the research CV, research-experience, or publications pages |

## Core facts (shared by both tracks)

**Md Omar Faruqe Riyad**
- Email: riyad.omf@gmail.com
- LinkedIn: linkedin.com/in/riyadomf | GitHub: github.com/riyadomf
- Portfolio: https://riyadomf.github.io
- Google Scholar: https://scholar.google.com/citations?user=dq62ho4AAAAJ (link WITHOUT `&authuser=2`; that variant breaks for other viewers)

**Education**
- B.Sc. in Computer Science and Engineering, Shahjalal University of Science and Technology (SUST), Sylhet, Bangladesh, 2018–2023
- CGPA: 3.53/4.00 (last two years: 3.83)
- GRE: 317/340 | TOEFL: 104/120

**Employment (as of July 2026)**
- **Dynamic Solution Innovators (DSI)**, Dhaka: Software Engineer, April 2023 to present. Current project: EC-BVRS.
- **Altri.ai / RevestAI**, remote (US): Full-Stack AI Engineer, part-time. Kept deliberately undated on CVs.
- **Dynamic Learning**: Course Instructor (Enterprise Web Development with JEE, JSF, and PrimeFaces), 2024 to present.
- **UIUC / SREGym**: Research Intern, advised by Prof. Tianyin Xu, 2026.

## Locked decisions (2026-07-18 review round; do not relitigate)

1. **Both CVs target 2 pages, but that is a preference, not a hard ceiling.** Never delete content to make a CV fit. When an edit pushes it past two pages, compile, look at what actually overflows, and **tell Omar what is spilling and what could go, then wait for his decision**. Tightening wording without losing a fact is fine unprompted; removing a bullet, entry, or claim is his call.
2. **GRE/TOEFL stay** on the research CV and about page, as one compact line below CGPA, never as the CV's first bullets.
3. **Altri.ai stays undated** ("Part-time") on the CVs.
4. **Off the dev CV**: the "built the foundational architecture / package structure / CDI-EJB" bullet. The site keeps the softened concrete version ("defined the security model and CDI/EJB conventions...").
4b. **OWASP Top 10 is off every output** (both CVs, about, job-experience, skills) as of 2026-07-30: not a depth Omar wants to claim or defend. The ISC2 CC certification stays, since holding a credential is a different claim from claiming expertise. See [dev-knowledge.md](dev-knowledge.md) §2.7.
5. **Kafka, Redis, Spring Boot stay in skills** everywhere: backed by EC-BVRS. Neo4j is out (coursework only).
6. **SREGym title is "Research Intern, advised by Prof. Tianyin Xu, UIUC".**
7. **Metric and rank honesty**: "Pass@1 0.85", never "85% accuracy". "Ranked 12th in post-evaluation (19th official)", never "Top 20". "Workshop papers co-located with EMNLP / NAACL / IJCNLP-AACL", never "published at EMNLP".

## Writing rules (apply to every output)

1. **No em dashes** anywhere. Commas, periods, colons, parentheses. En dash only for numeric ranges.
2. **Bold at most one thing per bullet**; prefer bolding only ranks and metrics.
3. **No labeled bullet prefixes** ("**Error Analysis:** ..." style).
4. **Break the uniform bullet shape.** At most half the bullets may end in "-ing" participial tails; use two short sentences sometimes.
5. **No filler adjectives** ("rigorous", "comprehensive", "significantly", "advanced") unless followed by a number. No number? Drop the claim, do not hedge it.
6. **Never repeat the same tagline sentence verbatim across pages.**
7. **Each fact lives in exactly one place per document** (a rank appears in Publications OR Honors, not both).
8. **Model tone**: the SREGym projects-page entry ("reward-hack-resistant oracle", "ecosystem-named decoy webhooks"). Specific beats polished.

## Workflows

**Applying for a job**: open [dev-knowledge.md](dev-knowledge.md). Pick bullets from the CV bullet pool matching the JD, remix into `resume/Omar_Dev_cv/main.tex`, recompile, drop the PDF into `files/` if it becomes the active variant.

**Applying for a PhD / research internship**: open [research-knowledge.md](research-knowledge.md). SOP raw material, verified citations, and the honest-framing rules are there. The research CV is `resume/Omar_research_cv/main.tex` (2 pages preferred; never cut content to fit without asking, see locked decision 1).

**Updating portfolio or CV**: this folder is the source of truth for facts and framing; `_pages/` and `resume/` are downstream. After any real-world change (new project, paper accepted, rank earned), update the relevant KB file first, then the site and CVs.

## Maintenance cadence

- **After every project milestone** (15 min): update the project's deep-dive section, within the sanitization rules.
- **After research milestones** (paper submitted/accepted, PR merged): update research-knowledge.md with verified facts (check the ACL Anthology / GitHub before writing).
- **Before each CV iteration**: pull from the bullet pool; keep the locked decisions above.
- **Interview-specific notes** (new questions received, answers to polish, anything strategic): private layer, not here.
