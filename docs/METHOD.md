# How I did the work and measured it

This page explains how I worked on CHANAKYA and how I tried to keep my own results honest. It does not describe the engine's internals.

## Labeled test cases

I built a labeled set of cases from public Java applications. For each case I read the source code and decided by hand whether it was vulnerable or safe. The tool is then scored against those labels. The scorer keeps three outcomes apart: the tool says vulnerable, the tool says protected, or the tool is uncertain. Uncertain answers are not counted as correct, and safe cases the tool never analyzed are not counted as confident decisions either.

Every change I made to the engine had to keep these scores at or above fixed floors. If a change made a floor fail, the change was wrong, not the floor. When a number had to go down for an honest reason, for example because I added harder cases, I wrote down why.

I also keep one deliberately harsh test. In the IWA-Java app every operation is labeled, not only the ones the tool happened to flag. The numbers there are much lower, and I report them anyway.

## Seen and unseen code

I learned that "third-party code" is not the same as "unseen code". If I fixed the engine after looking at a project, that project can no longer tell me how the tool does on new code. So all my labeled numbers are development numbers, and I say so.

For a real test I used pre-registered rounds on unseen projects. Before cloning anything, I wrote down the selection rules (for example a minimum number of stars, recent activity, and a real user-facing API) and checked that no chosen project overlapped with anything I had used before. Then I scanned them with AI turned off and checked every flagged candidate by hand against the source.

This process caught one of my own mistakes. In one round, I later found that one project had already been used in an earlier experiment. My overlap check had used an old exclusion list. I recorded the correction and counted that project as not unseen.

## Stopping instead of forcing a pass

I followed a simple rule: if the only way to make a test pass is to weaken the tool's caution, stop and write down why. Some examples of when I stopped:

- a fix would only work for one specific project, not in general
- a change would make the tool say "protected" when it could not prove it
- I could not measure something on my machine, so I did not report a guess

Stopping and writing down the evidence counted as a valid result.

## Independent reviews

When work was done in a separate session, including work done with AI coding assistants, I treated the result as untrusted until it was reviewed. A review checked each requirement against the actual code and tests and marked it as met or missing. Things marked missing were left open and recorded, not quietly fixed up.

## Null results

I report rounds that found nothing. In my last pre-registered round, on four unseen popular projects, I confirmed zero bugs. That is a real result. It tells me the tool's flagged candidates on hardened code are mostly false positives, which is where I need to improve.

## The AI experiments that failed

I ran pre-registered experiments to see whether an AI model could help resolve the engine's uncertain findings.

- In the first, I compared three setups: the model on its own, the model with extra context, and the model inside my tool. Every answer in every setup came back unresolved, so the experiment gave no evidence that any setup was better.
- In the second, the model investigated real uncertain findings. The run was stopped early, and every completed investigation ended in "abstain".

What these showed me: the model was not able to turn the engine's evidence into a firm answer, and my experiment setup had gaps too, such as a run that did not save its results until the very end. I fixed the setup problems and kept the rule that an AI answer can never replace the engine's decision.
