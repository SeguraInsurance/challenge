# Challenge: WhatsApp Lead Intake Bot

## Problem 
One of the biggest challenges brokers face is capturing new leads efficiently — a potential client sends a WhatsApp message asking about car insurance, and the broker either responds hours later or loses the lead entirely.

## Context

 Segura is building a WhatsApp-native experience for brokers. The first step is automating lead intake: when a potential client messages a broker's WhatsApp number, a bot should guide them through a short conversation, collect the key information needed for a quote, and make that lead available to the broker immediately.

Today this is done manually. The goal is to give a single broker the ability to capture and qualify leads 24/7 without any manual effort on their end.

## Objective

Build a proof of concept for a WhatsApp lead intake bot for a fictional insurance broker named Carlos, who sells auto insurance in São Paulo.

When a potential client messages Carlos's number, the bot should:

1. Greet the client and explain it will gather information for a quote
2. Collect: full name, vehicle year/make/model, and desired coverage type
3. Confirm the information and let the client know Carlos will follow up

Collected leads should be stored and accessible via a `GET /leads` endpoint.

## Inputs

We've included:

- `sample-conversation.txt` — an example of how Carlos currently handles a lead intake conversation manually over WhatsApp
- `sample-lead.json` — the data structure Carlos's team uses to track leads today

Use these as reference for tone, flow, and data structure — or don't. How you interpret and use them is part of what we're evaluating.

## Constraints
Tech Stack: You are free to choose your preferred stack, though Python with FastAPI is preferred.

Messaging Integration: You may use the WhatsApp Cloud API, Twilio Sandbox, or simply simulate the webhook with a plain POST endpoint. Please provide a brief justification for your choice.

Conversation Flow: The bot interaction should be concise, completing the full journey in 5 messages or fewer from the client’s side.

Security: No authentication is required for this implementation

## Deliverables

- A working backend with a webhook endpoint and `GET /leads`
- A short README explaining your approach and decisions (see below)
- A demo: Loom or short video (under 5 min) showing the bot in action

**Want to stand out?** Build a simple UI for Carlos to review his leads. We're not looking for visual polish — we're looking for product instinct. What does Carlos actually need to see? How should he act on this information? 

## README

Your README should answer:

1. How to run and test the project
2. Why you structured the data model the way you did
3. How the bot handles a client who goes off-script or abandons the conversation
4. What you would build next if this were a real product

## What We're Looking For

Why you built it the way you did, what you consciously chose to skip, and what you'd do with more time tells us far more than the code alone. Play to your strengths — whether that's product instinct or deep technical knowledge on architecture.
