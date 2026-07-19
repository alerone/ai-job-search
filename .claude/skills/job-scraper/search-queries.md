# Search Queries for Job Scraper

<!-- SETUP: Customize these queries based on your skills, target roles, and location -->

## Search Sites

No Spain-specific job-portal integration exists yet (the built-in CLI tools target the Danish market: Jobindex, Jobbank, Jobdanmark, Jobnet). Until a dedicated portal skill is added via `/add-portal`, search via:

Primary:
- **linkedin.com/jobs** - LinkedIn job listings (filter: Valencia / Comunitat Valenciana / Spain)
- Google site-searches (`site:linkedin.com/jobs`, or direct company career pages)

Secondary (company career pages via Google):
- Direct Google searches with `site:` filters for named target companies (see "Target Companies" below)

Consider running `/add-portal` later to add a native integration for a Spanish job board (e.g. InfoJobs, Tecnoempleo).

## Query Categories

Queries are grouped by priority. Combine with location terms ("Valencia", "Comunitat Valenciana", "España") where the search supports it. **Always include a "junior" qualifier** - candidate has ~10 months of combined professional experience (two ITI internships) plus an in-progress Master's degree, so mid/senior-only postings should generally be filtered out.

### Priority 1: Backend Developer / Software Engineer (Go)

Strongest and most desired career direction.

```
site:linkedin.com/jobs "backend developer" junior Golang Valencia
site:linkedin.com/jobs "software engineer" junior Go Valencia OR "Comunitat Valenciana"
"Golang developer" junior Valencia España
```

### Priority 2: Full-Stack Developer

Matches React/TypeScript + Go/Java experience.

```
site:linkedin.com/jobs "full stack developer" junior React TypeScript Valencia
site:linkedin.com/jobs "desarrollador full stack" junior Valencia
"full-stack engineer" junior Golang React Valencia España
```

### Priority 3: Junior Software Engineer (general)

Wider net given early-career stage - always include this category.

```
site:linkedin.com/jobs "junior software engineer" Valencia España
site:linkedin.com/jobs "ingeniero de software junior" Valencia
"graduate software developer" Valencia OR "Comunitat Valenciana"
```

### Priority 4: Broader / Adjacent (wider net)

Domain-adjacent roles worth a periodic look, given real (if not top-preference) experience with distributed systems and LLM/agentic tooling from the ITI R&D internship.

```
site:linkedin.com/jobs "backend" OR "distributed systems" junior Docker Kafka Valencia
site:linkedin.com/jobs "AI engineer" OR "LLM engineer" junior Valencia España
```

## Target Companies

Monitor these specifically, in addition to the general queries above:
- **Flywire**
- **Mercadona Tech**
- **Consum**
- **Indra**
- **OpenLine NL**
- **Revolut**

```
site:linkedin.com/jobs/ Flywire Valencia OR Spain junior
site:linkedin.com/jobs/ "Mercadona Tech" junior
site:linkedin.com/jobs/ Consum Valencia junior
site:linkedin.com/jobs/ Indra Valencia junior software
site:linkedin.com/jobs/ "OpenLine" junior software
site:linkedin.com/jobs/ Revolut junior software Spain OR remote
```

## Location Filter

When evaluating results, verify the job location is within reasonable commute distance from Valencia, or fully remote. Define acceptable areas:
- **Ideal:** Valencia city
- **Acceptable:** Valencia metro area / l'Horta comarques (Paterna, Alboraya, Burjassot, Mislata, Torrent, etc.)
- **Borderline:** Rest of Comunitat Valenciana (Castellón, Alicante) - only if hybrid/mostly remote
- **Too far:** Anywhere else in Spain or abroad requiring relocation, unless the role is fully remote (remote-only roles are acceptable regardless of company HQ location)

## Date Filter

Only include jobs posted within the last 14 days, or with an application deadline that has not yet passed. If a posting date cannot be determined, include it but flag as "date unknown".

## Adapting Queries

If the user specifies a focus area, select queries from the matching category and also generate 2-3 custom queries for that focus. For example:
- "/scrape [focus_area]" -> relevant category queries + custom focus-specific queries
