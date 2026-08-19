# Weekly HR/ESG Industry Brief

## What it does, and for whom

A four-step pipeline that turns five fixed HR/ESG sub-topics (HR analytics, ESG regulation, AI in HR, compensation trends, sustainability reporting) into a short, source-grounded weekly brief in my own voice, ready to post to LinkedIn or share with colleagues. Built for myself, as an HR/ESG professional who wants to stay current without spending an hour a week reading scattered articles.

## Setup (for a stranger to follow)

1. Create a Claude Project (any Claude.ai account with web search enabled works).
2. Add this standing instruction to the Project:

"Weekly HR/ESG Brief pipeline: For each of the 5 topics (HR analytics, ESG regulation, AI in HR, compensation trends, sustainability reporting), search for current news, then synthesize into 1-2 sentence findings using only facts from search results, no invented figures. Write each finding in my voice: serious, professional, specific, fact-based, no cliches. Cite the source name, not exact quotes over 15 words. Format the final output as a 5-item scannable list."

3. Start a new chat inside that Project and send: "Run this week's brief."
4. The model runs one web search per topic, synthesizes, and returns the formatted brief.

No API keys, no code, no paid tools, everything runs inside the free Claude.ai chat interface.

## Usage example

Input: Run this week's brief.

Output excerpt:
ESG Regulation: The EU's Omnibus simplification has cut CSRD/CSDDD scope by roughly 85-90% of previously covered companies and reduced mandatory ESRS data points by more than 60%, while the US SEC has moved to rescind its 2024 climate-disclosure rules entirely. Source: Pulsora, KnowESG.

## Architecture (simple sketch)

Step 1: Me typing "Run this week's brief" into the Claude Project chat.
Step 2: The Claude Project instruction fires automatically.
Step 3: GATHER, the model runs one web search for each of the 5 fixed topics.
Step 4: SYNTHESIZE, the model dedupes results and extracts the key facts.
Step 5: DRAFT, the model writes each finding in my voice.
Step 6: REVIEW/FORMAT, the model checks facts against sources and outputs a 5-item scannable list.
Result: a finished weekly brief, ready to post.

This is a workflow, not an agent. The four steps and five topics are fixed by me in advance. The model doesn't decide what to search next or when to stop, it executes the same sequence every run.

## v2 Eval Results

Manual research: about 10-12 minutes per topic, about 55-60 minutes total for 5 topics.
Pipeline (this build): about 3.5-4 minutes per topic, about 18-20 minutes total, plus a 15 minute one-time setup.
Time saved after setup: roughly 60% faster.

Cross-model check (Claude vs ChatGPT, same prompt, same dataset in a related exercise): both correctly applied the requested output format, but ChatGPT missed one data anomaly that Claude caught, a reminder that output format compliance doesn't guarantee equal accuracy between models.

## Limitations

Source quality isn't filtered. The model doesn't reliably distinguish an independent report from a vendor's self-promotional blog post, I still have to check sources before publishing.

Recency isn't guaranteed by search ranking. A couple of top results were several months old despite ranking highly, I manually favor sources dated within 4-6 weeks.

Conflicting numbers aren't resolved automatically. When two sources gave different figures for the same statistic, the model picked one without flagging the conflict, I have to catch this by re-reading.

Voice drift. Draft language occasionally leans toward the source's phrasing instead of my own, I do a final read-through before publishing.

No memory across weeks. Each run is independent, it doesn't know what it covered last week, so repeat stories aren't automatically filtered out.

## What I built with AI, and what I checked myself

I designed the four-step structure (gather, synthesize, draft, review/format), fixed the five topics, and wrote the voice constraints myself. Claude wrote the actual Project instruction wording and executed every run. I checked every run for fabricated numbers (none found after adding the anti-fabrication rule), source credibility (caught two vendor-blog sources I chose not to cite), and voice consistency (rewrote a handful of sentences that leaned too close to source phrasing). The time-accounting numbers above are my own estimate, not AI-generated.
