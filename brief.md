Version: NAFATH-V3
Track: Data

## Overview

A government AI chat assistant inside a mobile app depends on all six fields working together. Software practice keeps the assistant's API stable, using Semantic Versioning so app updates do not break older versions. AI techniques such as RAG ground answers in official service information to reduce wrong answers. On mobile, iOS App Transport Security forces the app to reach the API only over HTTPS. Networking with IPv6 keeps the service reachable as connected devices grow. Cybersecurity defends the assistant against prompt injection that could make it ignore its rules. Finally, data protection decides how citizens' chat logs are stored safely and lawfully.

## Software

Under Semantic Versioning (MAJOR.MINOR.PATCH), the assistant's public API must increase MAJOR when it makes incompatible changes, such as removing an endpoint or renaming a field the mobile app depends on. MINOR increases when new features are added in a backward-compatible way, such as a new optional parameter. PATCH increases for backward-compatible bug fixes. This tells app developers whether an update could break existing versions of the app.

## AI

Retrieval-Augmented Generation (RAG) combines a language model with a search step. Before answering, the assistant retrieves relevant passages from a trusted knowledge source, such as the entity's official service pages, and uses them to generate its answer. Because answers are grounded in retrieved documents rather than only the model's memory, they are more factual and specific. The knowledge base can also be updated without retraining, and answers can show where they came from.

## Mobile

App Transport Security (ATS) requires the iOS app's network connections to use HTTPS secured by TLS 1.2 or later, with trusted certificates, strong ciphers and forward secrecy. If the app tries to call a plain HTTP endpoint, ATS blocks the connection and logs an error. Developers can add exceptions in the Info.plist file, but Apple discourages this and may require justification during App Store review. The assistant's API should therefore be served only over HTTPS.

## Networking

## Cybersecurity

## Data

## Misconception in My Track

## Open Question
