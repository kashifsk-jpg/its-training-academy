# ITS Training Academy

Online training and certification platform for Inspection & Technical Survey (ITS), Dammam. Learners study online, pass an exam, complete a practical assessment with an ITS inspector, and receive a certificate with a QR code that anyone can verify.

**Status:** proof of concept (POC), week 1 — scope and requirements. Pilot course: Forklift Operator (Counterbalance).

## POC approval flow

| Week | Step | Owner |
| --- | --- | --- |
| 1 | Business scope and requirements | Kashif |
| 2–4 | POC development and testing | Anas + Kashif |
| 5 | POC demonstration and validation | Kashif + Anas |
| 5 | Final POC approval | Salim + Abu Khidr |

## What's in this repository

| Folder | Contents |
| --- | --- |
| `docs/` | POC plan, requirements, course outline and exam bank, practical checklist, certificate wording and HeyGen script (Markdown, plus one combined Word file); review of the Heavy Metal Learning video list (Excel) |
| `prototype/` | Design source of the clickable prototype (8 screens). These files run only inside the Claude design canvas; use the live link below to click through. |
| `src/` | *(to come)* .NET 10 Web API and React 19 + Ant Design 6 front end, built by Anas from week 2 |

## Links

- Clickable prototype: https://claude.ai/artifact/KMxA1i4Pz75f6X25GDoByo (private until shared from its Share menu)
- POC plan (live doc): https://claude.ai/artifact/RQBsSE8xKWEDcsux97PQZi

## Technology

| Layer | Choice |
| --- | --- |
| Backend | .NET 10 Web API, Entity Framework Core, PostgreSQL, ASP.NET Core Identity |
| Frontend | React 19, Vite, Ant Design 6, react-i18next (Arabic RTL and English) |
| Certificates | QuestPDF (PDF), QRCoder (QR code) |
| Hosting | One Linux server running Docker |

## Before anything goes live

- Course content, exam questions and the practical checklist are **drafts** written from general forklift safety practice. An ITS inspector must review every item against ITS material and the standard ITS will be accredited to.
- Certificates say "ITS Certificate of Completion". Do not use the word "accredited" until a training licence is granted (TVTC in KSA, Ministry of Labour in Oman).
- Third-party videos (Heavy Metal Learning) may only be embedded through YouTube's player; downloading, re-uploading or dubbing them needs the owner's written licence.
- Arabic text needs a check by a native speaker.
