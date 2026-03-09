# Challenge: AI Policy Q&A Service

## Context

When a client calls their broker with a question — "Am I covered if my car is stolen while parked outside?" — the broker often has to dig through a 40-page policy PDF to find the answer. This is slow, error-prone, and frustrating for everyone.

Brokers don't get many chances to have positive interactions with their clients. This challenge is about making one of those interactions better: a way to ask a policy document a question and get a direct, accurate answer — not a keyword search result, not a page number, but an actual answer in plain language.

The hard part isn't building a chatbot. It's building one that doesn't make things up. A broker telling a client "yes, you're covered" based on a hallucinated answer is worse than no answer at all.

## Objective

Build a proof of concept Q&A service for Marina, an insurance broker who works with auto and home insurance clients in Rio de Janeiro.

Marina should be able to:

1. Upload a policy PDF
2. Ask a question about it in plain Portuguese or English
3. Receive an accurate answer grounded in the document — or a clear "this isn't covered in the policy" response when the answer isn't there

## Inputs

- `sample-policy.txt` — a text version of relevant content from a policy PDF (based on a real policy; your system should ideally handle PDF but it's ok to start with txt)
- `sample-questions.txt` — 5 questions Marina's clients commonly ask, ranging from easy to ambiguous

Use these to build and test your solution. You don't need to handle arbitrary or very large PDFs.

## Constraints

- Backend in Python (FastAPI preferred)
- LLM of your choice — OpenAI, Anthropic, or open model. Keep costs minimal; we'll reimburse up to $10 if needed
- `POST /ask` should accept a question and return an answer
- No authentication required

## Deliverables

- A working backend with document upload and `POST /ask` endpoints
- A short README explaining your approach and decisions (see below)
- A demo: Loom or short video (under 5 min) showing the service working on the sample questions, including at least one "I don't know" case

**Want to stand out?** Choose one (or both):

**Option 1 — SUSEP Integration:** In Brazil, SUSEP (the insurance regulator) publishes a Condição Geral document for every insurance product from every carrier — it's the underlying contract that defines what's covered vs. what's excluded. When a client's policy references a SUSEP process number, that number maps to a specific version of the Condição Geral that was in force when they bought the product. A broker asking "is coverage for flexible tubing included?" might not find the answer in the one-page policy summary — but it's almost certainly in the Condição Geral. Extend your Q&A service to consider the relevant Condição Geral document when the policy alone doesn't have the answer. The SUSEP integration can be mocked — you don't need a live API — but the architecture should reflect that (a) the Condição Geral is looked up by process number, and (b) document versions matter.

**Option 2 — Chat UI:** Build a simple chat UI for Marina. Upload the policy, ask questions, see answers. What does it feel like to use? What happens when the model isn't confident? There's a lot of product thinking to be done here if you want to go there.

## README

Your README should answer:

1. How to run the project
2. How you process and retrieve content from the PDF — and why
3. How you prevent the model from answering questions the document doesn't cover
4. What breaks or degrades with a longer or more complex document, and how you'd address it
5. What you would build next if this were a real product

## What We're Looking For

The most important questions here aren't "how do I build a chatbot" — they're "how do I make sure it never lies" and "how do I make sure this would work talking directly to the end customer." Your approach to those questions, and how clearly you can explain it, matters more than the completeness of your implementation.
