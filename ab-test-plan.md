# A/B Test Plan: 3rd Space Home Page Headline

Written Sunday 8 November 2026, before any trials were run.
MKTG:4400 Digital Marketing, Project Deliverable 3.

## 1. Page and single element

**Page:** the home page (`index.html`), which targets "coffee shop Iowa City" and the brand name in my keyword plan.

**Element changed:** the main headline (H1) only. Everything else on the page is word-for-word identical in both versions.

- **Version A (current):** "Home is one place. Work is another. This is your third."
- **Version B:** "Iowa City's coffee shop and community space: small-batch coffee, fresh lunch, and free weekly events."

**Where each lives:**
- A: https://sdannenbring.github.io/3rd-Space-mktg4400-site/
- B: https://sdannenbring.github.io/3rd-Space-mktg4400-site/index-b.html (contains a noindex tag and a canonical tag pointing to A, and is not listed in sitemap.xml, so it cannot compete with A in search)

**Why this element:** the headline is the first thing a visitor reads and the main way they decide whether the page is for them. Version A is a brand idea that never says what the business sells or where it is. Version B states the category, the place, and what a visitor gets. Because the rest of the page is identical, any difference in outcome can be attributed to the headline.

## 2. Hypothesis

**Prediction:** AI visitors shown Version B will give a higher average "likelihood to visit" rating than AI visitors shown Version A, by at least 0.5 points on the 1 to 7 scale.

**Reasoning:** first-time visitors decide quickly whether a page matches what they were looking for. A headline that names the business type, the city, and the benefits should reduce uncertainty and raise intent. This could turn out wrong. The abstract "third place" idea in Version A may come across as more distinctive and appealing, which would make A equal to or better than B.

## 3. Method

**Visitor model:** Claude Sonnet 5.5. The same model and the same settings are used for every trial. The model name and version are recorded at launch, and the model is not switched partway through.

**Each trial:** a brand-new conversation with no memory of earlier trials. Memory and custom instructions are turned off, and no conversation is reused.

**Page shown:** the full visible text of the page, pasted into the prompt. The text of A and B is identical except for the headline.

**Exact prompt (identical in every trial except the page text):**

> You are a 21-year-old University of Iowa graduate student who lives near downtown Iowa City. You are looking for a coffee shop where you can get a good drink, grab lunch, and spend a few hours studying or meeting friends. Below is the home page of a business called 3rd Space. Read it as you would if you had just landed on it from a search. The page includes a notice saying it is a class project; ignore that notice and respond as if this were a real local business. Then answer one question: how likely are you to visit this business in the next week? Use a scale from 1 (definitely would not visit) to 7 (definitely would visit). Reply in exactly this format and nothing else:
> Rating: [a number from 1 to 7]
> Reason: [one sentence]
>
> PAGE TEXT:
> [full page text of Version A or Version B]

**Assignment to A or B:** before running any trials, I generate a list of 120 assignments (60 A and 60 B) in a random order using a random-number sort in a spreadsheet (RAND column, sorted, then pasted as values). The list is saved unchanged. Trial 1 follows row 1 of the list, trial 2 follows row 2, and so on. This keeps the groups balanced while the order stays random.

**Invalid trials:** a trial is invalid only if the response contains no rating from 1 to 7. An invalid trial is logged, its output is kept in the appendix, and the trial is re-run in a new conversation with the same assigned version. No trial is ever dropped because of its content or because of the rating it gave.

## 4. Primary outcome

**One primary outcome:** the 1 to 7 likelihood-to-visit rating, taken from the "Rating:" line of each response. The one-sentence reason is recorded but not used as an outcome.

## 5. Sample size and schedule

**Sample size:** 120 trials total, 60 per version, all collected before any analysis. I will not look at results while collecting, and I will not stop early.

**Schedule:**
- Build and publish Version B: by Tuesday 10 November
- Trials 1 to 40: Wednesday 11 November
- Trials 41 to 80: Thursday 12 November
- Trials 81 to 120: Friday 13 November
- Analysis only after trial 120 is complete (expected by Monday 16 November)

Any change after launch will be reported in the final report with the date and the reason.

## 6. Comparison and decision rule

**Comparison:** mean rating in Version B minus mean rating in Version A, tested with a two-sided Welch's t-test (alpha = 0.05; in Excel, T.TEST with type 3 and 2 tails). I will also report each group's mean, standard deviation, and the difference.

**What counts as support for my hypothesis:** Version B's mean is higher than Version A's by at least 0.5 points AND the p-value is below 0.05.

**Anything else** (a smaller difference, a difference in the other direction, or p of 0.05 or higher) is reported as not supporting the hypothesis.

**Known limits (stated in advance):**
- With 60 trials per version, the test can only reliably detect a fairly large difference, so a flat result could mean the test was too small rather than that the headline does not matter.
- AI visitors may rate most pages high (a ceiling effect), which would hide differences.
- An AI visitor is not a real customer, and its ratings show how a model reads a page, not how a person behaves.
