# CHANAKYA

This is a public showcase of CHANAKYA. The main repository is private because it contains security findings in open-source projects that have not yet gone through coordinated disclosure to their maintainers. Source code and full details are available to admission committees and supervisors on request.

Contact: sujanaacharya17@gmail.com, https://github.com/sujanaacharya

## What CHANAKYA is

CHANAKYA is a tool I built that reads the source code of Java web applications written with Spring and looks for broken access control. This is when one user can read or change another user's data, for example by changing an order number in a request.

## Why it matters

Broken access control is A01 in the OWASP Top 10, in both the 2021 and 2025 lists. A line like `orderRepository.findById(id)` is fine for an admin and a serious bug if any user can pass in someone else's id. A tool has to know who is calling, which record they asked for, and whether some check ties the two together. Most scanners look for dangerous patterns. A missing ownership check is something that is not there, so there is no pattern to match.

## How it works

A rule-based engine reads the code, follows how a request reaches the database, and looks for checks that link the logged-in user to the record. It makes every final decision and works fully with AI turned off. When it cannot prove something, it says "uncertain", not "safe".

An optional AI layer can investigate and explain a finding, and it can disagree, but it can never create, change or hide a final verdict. A wrong "this is protected" answer is the worst mistake a security tool can make, so I watch for it most closely. The project has over 5,000 automated tests, and every change to the engine is checked against a fixed set of 13 reference repositories before it is accepted.

## Results

On my labeled set of third-party Java apps (99 access-control cases): precision 71.62%, recall 92.98% (TP 53, FP 21, FN 4). The tool made a confident decision on 78 of the 99 cases.

It also covers SQL injection (11 real-world cases: TP 8, FP 0, FN 0; on OWASP Benchmark Java it found 241 of 272 vulnerable cases) and unsafe deserialization (11 cases: TP 4, FP 0, FN 2). On IWA-Java, where every operation is labeled, access-control precision is only 13.79%. I keep it because it shows where the tool is weak.

I developed the tool against all of these sets, so none of them shows how it does on code it has never seen.

So I scanned real open-source projects and checked every candidate by hand. I confirmed 4 access-control bugs. In mogu_blog_v2, the tool found again, independently, a bug that already had a public CVE (CVE-2026-89261): anyone could delete search index entries without logging in. The other three are withheld until the maintainers have been told. One of those three is in a project I had used during development, so it is not a test on unseen code.

In my last pre-registered round, only four of the five chosen projects turned out to be truly unseen. I confirmed zero bugs in them. Two were scanned fully, with every candidate a false positive or out of scope. One crashed the tool (since fixed) and one was too large for my laptop.

## What I learned and what did not work

- Honest measurement made my numbers worse. On the SQL injection benchmark I used to count "no finding" on safe code as correct. When I stopped, the share of cases where it made a confident decision on that benchmark fell to 47.82%.
- My AI experiments have not worked yet. In two pre-registered experiments, every answer came back unresolved or abstained.
- Many false positives come from ownership checks written as plain `if` statements, which the engine often cannot connect to the record.
- Without a sealed holdout set, I cannot yet claim how well the tool generalizes.

## What I want to research next

I want to build a sealed, unseen test set and measure on it exactly once. I also want to study how an AI model can produce evidence that a rule-based checker can verify, instead of verdicts that must be trusted.

## How I built it

I used AI coding assistants (Claude Code) to write much of the code. I designed the system and the testing method, wrote the task for every session, reviewed the results, and decided what counted as proof. Every result was checked by tests or by reading the code by hand.

## Built with

Python, tree-sitter, NetworkX, Pydantic, pytest, mypy and ruff.

See [docs/METHOD.md](docs/METHOD.md), [docs/RESULTS.md](docs/RESULTS.md) and [examples/](examples/).
