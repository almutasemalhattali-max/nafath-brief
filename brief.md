Version: NAFATH-V3
Track: Data

## Overview

A government AI chat assistant inside a mobile app depends on all six fields working together. Software practice keeps the assistant's API stable, using Semantic Versioning so app updates do not break older versions. AI techniques such as RAG ground answers in official service information to reduce wrong answers. On mobile, iOS App Transport Security forces the app to reach the API only over HTTPS. Networking with IPv6 keeps the service reachable as connected devices grow. Cybersecurity defends the assistant against prompt injection that could make it ignore its rules. Finally, my Data track examines whether citizens' chat logs should be anonymized or pseudonymized, since only truly anonymous data falls outside data protection law.

## Software

Under Semantic Versioning (MAJOR.MINOR.PATCH), the assistant's public API must increase MAJOR when it makes incompatible changes, such as removing an endpoint or renaming a field the mobile app depends on. MINOR increases when new features are added in a backward-compatible way, such as a new optional parameter. PATCH increases for backward-compatible bug fixes. This tells app developers whether an update could break existing versions of the app.

Resource: Semantic Versioning 2.0.0 - https://semver.org/spec/v2.0.0.html

## AI

Retrieval-Augmented Generation (RAG) combines a language model with a search step. Before answering, the assistant retrieves relevant passages from a trusted knowledge source, such as the entity's official service pages, and uses them to generate its answer. Because answers are grounded in retrieved documents rather than only the model's memory, they are more factual and specific. The knowledge base can also be updated without retraining, and answers can show where they came from.

Resource: Retrieval-Augmented Generation for Knowledge-Intensive NLP Tasks (Lewis et al., 2020) - https://arxiv.org/abs/2005.11401

## Mobile

App Transport Security (ATS) requires the iOS app's network connections to use HTTPS secured by TLS 1.2 or later, with trusted certificates, strong ciphers and forward secrecy. If the app tries to call a plain HTTP endpoint, ATS blocks the connection and logs an error. Developers can add exceptions in the Info.plist file, but Apple discourages this and may require justification during App Store review. The assistant's API should therefore be served only over HTTPS.

Resource: Preventing Insecure Network Connections (Apple Developer Documentation) - https://developer.apple.com/documentation/security/preventing-insecure-network-connections

## Networking

IPv4 addresses are 32 bits long, allowing about 4.3 billion addresses, which is too small for the growing number of connected devices. IPv6 expands addresses to 128 bits, giving a vastly larger number of addressable devices, more levels of addressing hierarchy and simpler address auto-configuration. It also simplifies the packet header. As more citizens' phones and devices connect, supporting IPv6 keeps the assistant's servers reachable for every user.

Resource: RFC 8200 - Internet Protocol, Version 6 (IPv6) Specification - https://www.rfc-editor.org/rfc/rfc8200

## Cybersecurity

Prompt injection is an attack where crafted input makes the assistant ignore its instructions and behave in unintended ways. In direct injection, a user types the malicious instruction into the chat, for example to reveal its rules. In indirect injection, the instruction is hidden in external content the assistant reads, such as a web page or document retrieved by RAG. Two ways to reduce risk are limiting the assistant to least-privilege access and filtering inputs and outputs.

Resource: LLM01:2025 Prompt Injection (OWASP Gen AI Security Project) - https://genai.owasp.org/llmrisk/llm01-prompt-injection/

## Data

Pseudonymization replaces identifiers in chat logs, such as names or civil ID numbers, with codes, while the key that links codes to people is stored separately. Because citizens can still be re-identified with that key, pseudonymized logs remain personal data and the law still applies. Anonymization removes identifying details so that no one can reasonably identify the person. Only truly anonymous data falls outside data protection law, which is hard to achieve with free-text chats.

Resource: Regulation (EU) 2016/679 (General Data Protection Regulation), Recital 26 - https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=CELEX:32016R0679

## Misconception in My Track

A common misconception is that replacing citizens' names and civil ID numbers with codes makes chat logs anonymous, so they can be stored or shared freely. This is wrong. Replacing identifiers is only pseudonymization. If the organization can link the codes back to people using additional information, such as a lookup table, the logs are still personal data and data protection law still applies. Data is only anonymous when the person can no longer be identified by any means reasonably likely to be used. Recital 26 of the GDPR states this: pseudonymised data that could be attributed to a person using additional information is still information on an identifiable person.

## Open Question

How long should a government entity keep pseudonymized chat logs before deleting or anonymizing them, and who should decide this retention period?
