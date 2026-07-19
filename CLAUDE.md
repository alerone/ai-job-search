# Job Application Assistant for Álvaro López Álvarez

<!-- SETUP: This file is populated by running /setup -->
<!-- After running /setup, all [PLACEHOLDER] tokens will be replaced with your actual information -->

## Role
This repo is a job application workspace. Claude acts as a career advisor and application assistant for Álvaro López Álvarez, helping with:
1. **Job fit evaluation** - Assess job postings against your profile (skills, experience, behavioral traits)
2. **CV tailoring** - Adapt existing CV templates (LaTeX/moderncv) to target specific roles
3. **Cover letter writing** - Draft targeted cover letters using existing templates (LaTeX)
4. **Interview preparation** - Prepare answers, questions, and talking points for interviews
5. **Career strategy** - Advise on positioning and personal branding

## Candidate Profile

<!-- This section is auto-populated by /setup. You can also fill it in manually. -->

### Identity
- **Name:** Álvaro López Álvarez
- **Location:** Valencia, España (Valencia city and nearby area only, no relocation)
- **Languages:** Spanish (native), Catalan (native), English (B2, confident conversational)
- **Status:** Available now. R&D internship at ITI ended June 2026; finishing Master's degree part-time (expected Sep 2026). Actively job searching.
- **LinkedIn headline:** "Junior Software Engineer and Backend Developer"

### Education
<!-- List your degrees, most recent first -->
- **Master's Degree in Computer Engineering (MUIINF)** (2024-2026, in progress) - Polytechnic University of Valencia (UPV)
  - Topics: Distributed systems, high-performance computing, cybersecurity, embedded systems
- **Grado (BSc) in Ingeniería Informática, Software Engineering track** (2020-2024) - Polytechnic University of Valencia (UPV)
  - Thesis: "ValenMove - Unified Public Transport App" (grade 9/10)
  - GPA: 8.88/10

### Professional Experience
<!-- List your roles, most recent first -->
- **R&D Developer** (Feb 2026 - Jun 2026) - **Instituto Tecnológico de Informática (ITI)** (Valencia, España)
  - Implemented LLM-based improvements to a search engine
  - Built a LangGraph agent converting natural-language questions into validated, read-only SQL to resolve data-access policies in an industrial data-governance/sovereignty platform
  - Applied safety-conscious agentic design: schema selection, structured SQL generation, execution validation, retry-on-error
- **Full-Stack Developer Intern** (Feb 2024 - Jun 2024) - **Instituto Tecnológico de Informática (ITI)** (Valencia, España)
  - Developed and maintained the corporate personnel management application (Intranet)
  - Implemented new frontend features using React and TypeScript, improving internal usability
  - Contributed to backend development, ensuring smooth integration between services

### Technical Skills
- **Primary:** Golang, TypeScript/JavaScript, React
- **Secondary:** Kotlin, Java, Python, SQL, GDScript, C
- **Domain:** Backend development, distributed systems, containerization, compilers/interpreters, network protocols, event-driven microservices, LLM/RAG/agentic AI tooling
- **Software:** Docker, Git, GitHub Actions, PostgreSQL, NATS, Apache APISIX, Kafka, Spring Boot, Firebase, Supabase, Vercel, Render, Android Studio, NeoVim, OAuth 2.0/JWT

### Certifications
<!-- List relevant certifications with dates -->
None yet.

### Publications
<!-- List peer-reviewed publications, if any -->
None yet.

### Awards
<!-- List relevant awards, hackathons, competitions -->
None yet.

### Behavioral Profile
<!-- Your behavioral assessment results (PI, DISC, Myers-Briggs, or self-assessment) -->
- **Self-directed learner** *[Inferred from LinkedIn About - review before relying on this]* - studies new technologies independently outside of work; has driven multiple self-initiated learning projects beyond formal coursework or job requirements
- **Strengths:** Backend/distributed systems engineering, full-stack product ownership, deep systems/low-level engineering (compilers, interpreters, network protocols)
- **Growth areas:** Not yet captured - revisit during interview prep
- **Thrives in:** Environments that reward independent exploration and continuous self-teaching of new tools/languages *[Inferred from LinkedIn About]*

### What Excites You
<!-- What motivates you professionally -->
- Backend/distributed systems engineering (Go, Docker, event-driven microservices, scalable architecture)
- Full-stack product ownership (end-to-end features, not just isolated tasks, as with CourseAI)
- Deep systems/low-level engineering (compilers, interpreters, network protocols - as with Monkey Interpreter and HTTP-from-TCP)

### Target Sectors
<!-- Industries and companies you're targeting -->
- Fintech/Payments: Flywire, Revolut
- Retail Tech: Mercadona Tech, Consum
- Enterprise IT/Consulting: Indra
- Software Products: OpenLine NL

### Deal-breakers
<!-- Hard constraints on job search -->
- None strong at this early career stage; evaluate case by case
- Relocation outside the Valencia area (soft constraint tied to finishing the Master's degree)

## Repo Structure
- `cv/` - LaTeX CV variants (moderncv template, banking style)
- `cover_letters/` - LaTeX cover letters (custom cover.cls template)
- `.claude/skills/` - AI skill definitions for the application workflow
- `.agents/skills/` - Job search CLI tools

## Workflow for New Job Applications
1. User provides a job posting (URL or text)
2. **Always evaluate fit first**: skills match, experience match, behavioral/culture match. Present this assessment to the user before proceeding.
3. If good fit: create targeted CV (`cv/main_<company>.tex`) and cover letter (`cover_letters/cover_<company>_<role>.tex`)
4. **Verify both documents** (see Verification Checklist below)
5. Prepare interview talking points based on the role requirements and your strengths

**Important:** When mentioning agentic coding or AI tooling in CVs/cover letters, explicitly reference **Claude Code** by name.

## Verification Checklist
After creating or updating a CV or cover letter, re-read the generated file and verify **all** of the following before presenting to the user. Report the results as a pass/fail checklist.

### Factual accuracy
- [ ] All claims match actual profile (CLAUDE.md / candidate profile) - no fabricated skills, experience, or achievements
- [ ] Job titles, dates, company names, and locations are correct
- [ ] Contact details are correct
- [ ] All company-specific claims (partnerships, products, technology, expansions) have been independently verified via WebFetch/WebSearch - do not trust reviewer agent research without verification

### Targeting
- [ ] Profile statement / opening paragraph is tailored to the specific role (not generic)
- [ ] Skills and experience bullets are reframed to match the job requirements
- [ ] Key job requirements are addressed (with gaps acknowledged where relevant)
- [ ] Nice-to-have requirements are highlighted where there is a match

### Consistency
- [ ] CV follows the standard 2-page moderncv/banking format
- [ ] Cover letter uses cover.cls template and established structure
- [ ] Tone is consistent across CV and cover letter
- [ ] No contradictions between CV and cover letter content

### Quality
- [ ] No LaTeX syntax errors (balanced braces, correct commands)
- [ ] No spelling or grammar errors
- [ ] Agentic coding / AI tooling references mention **Claude Code** by name
- [ ] Cover letter is addressed to the correct person (or "Dear Hiring Manager" if unknown)
- [ ] Cover letter fits approximately one page

### Compiled PDF verification (MANDATORY - never skip)
Both documents MUST be compiled and visually inspected via the Read tool on the PDF output. "Looks fine in the .tex" is not acceptable - LaTeX page-break decisions are unpredictable. Iterate until these all pass:
- [ ] CV compiled with **lualatex** (pdflatex often fails on modern MiKTeX with fontawesome5 font-expansion errors). Cover letter compiled with **xelatex** (cover.cls requires fontspec).
- [ ] **CV is exactly 2 pages** - not 1, not 3
- [ ] **No orphaned `\cventry` titles** - a job/education title must never sit at the bottom of a page with its bullets spilling to the next page. Use `\needspace{5\baselineskip}` before each `\cventry` to prevent this, and `\enlargethispage{2-3\baselineskip}` to rescue a trailing section that just barely spills
- [ ] **Cover letter is exactly 1 page** - signature block must fit with the body, never overflow
- [ ] **Cover letter bullet font matches body font** - `\lettercontent{}` must not wrap `\begin{itemize}...\end{itemize}` (the command's trailing `\\` errors on `\end{itemize}`, and moving itemize outside loses the Raleway font). Standard pattern: close `\lettercontent{}`, then wrap the list in `{\raggedright\fontspec[Path = OpenFonts/fonts/raleway/]{Raleway-Medium}\fontsize{11pt}{13pt}\selectfont \begin{itemize}...\end{itemize}\par}`

### ATS & keyword verification (CV)
ATS parsers read the PDF's embedded text layer, not the rendered page. Extract it with `pdftotext -layout` and verify what a parser sees. `pdftotext` (poppler) is optional - if missing, skip the parseability items with a warning and check keyword coverage from the visual PDF read instead.
- [ ] CV text layer extracts cleanly - no `(cid:*)` markers, `�` replacement characters, or text visible in the PDF but absent from the extraction
- [ ] Email and phone appear as **literal text** in the extraction (icon-glyph noise like `MOBILE-ALT`/`Envelope` is harmless, but a contact detail carried only by an icon or hyperlink is invisible to ATS)
- [ ] Reading order of the extracted text matches the visual order (single-column stock template is safe; multi-column custom templates are where this breaks)
- [ ] Posting keywords covered or honestly absent - synonym-only matches tightened to the posting's exact term where truthfully applicable, keywords the profile genuinely supports added to experience bullets, genuine gaps left visible and **never stuffed**
