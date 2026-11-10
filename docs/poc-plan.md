# ITS Training Academy — Forklift POC Plan

10 November 2026 · Kashif Khan · Draft for approval

The proof of concept is one forklift course built end to end, so the approvers see the whole learner journey working: Kashif scopes it in week 1, Anas and Kashif build and test it in weeks 2–4, and Salim and Abu Khidr decide go / no-go after the week 5 demo.

## POC scope

One course — Forklift Operator (Counterbalance) — working from catalogue to verified certificate. Breadth waits until the approvers say go.

**In scope**

1. Public home page and course catalogue with the one forklift course, in Arabic and English (right-to-left for Arabic).
2. Sign-up and login, with three roles: learner, ITS evaluator and admin.
3. Course player: modules of lessons with embedded videos (some from the reviewed Heavy Metal Learning list, plus one HeyGen sample), PDFs and progress tracking.
4. Final exam drawing questions at random from a bank, with a pass mark and limited attempts.
5. Practical assessment checklist the ITS inspector fills in on a tablet.
6. Certificate PDF with a certificate number, an expiry date and a QR code.
7. Public verification page that opens when the QR code is scanned.
8. Basic admin area for adding courses and questions and viewing learners.

**Out of scope until approved:** payments, company accounts, Moodle, a mobile app and SCORM.

## Who does what

The POC follows the four-step approval flow over five weeks.

| Week | Step | Owner | Output |
| --- | --- | --- | --- |
| 1 | 1. Business scope and requirements | Kashif | Signed-off scope; forklift material from ITS; about 30 exam questions; practical checklist; certificate wording and logo; one HeyGen sample script |
| 2–4 | 2. POC development and testing | Anas + Kashif | Working POC on a test server |
| 5 | 3. POC demonstration and validation | Kashif + Anas | The whole journey run live in both languages, and a certificate's QR code scanned on a phone |
| 5 | 4. Final POC approval | Salim + Abu Khidr | Go / no-go for the full build |

## Technology

Current, long-supported tools that cost nothing to license, on one Linux server.

| Layer | Choice | Note |
| --- | --- | --- |
| Backend | .NET 10 Web API, Entity Framework Core, PostgreSQL | .NET 10 is the long-term support release, supported to November 2028; ASP.NET Core Identity for logins |
| Frontend | React 19 + Vite + Ant Design 6 | react-i18next for Arabic and English; Ant Design 6 supports right-to-left layout |
| Certificates | QuestPDF for the PDF, QRCoder for the QR code | Check QuestPDF's licence terms against ITS's revenue |
| Hosting | One Linux server running Docker; code on GitHub | About USD 50–100 a month; no Windows Server licence needed |

## Cautions for the demo

- **No "accredited" wording yet.** Do not use the word on the certificate or the site until a licence is granted: TVTC in KSA, or the Ministry of Labour in Oman. Until then, title it "ITS Certificate of Completion".
- **Expert sign-off on all content.** An ITS inspector approves every lesson and exam question before the demo.
- **Third-party videos are embeds only.** Heavy Metal Learning videos play through YouTube's player as optional viewing; downloading, re-uploading or dubbing them needs their written licence.

## Week 1 checklist

What Kashif needs in hand to sign off the scope and hand over to Anas.

- [ ] Forklift course material from ITS (presentations, manuals, inspection checklists) — needed to check the drafts below
- [ ] Requirements and open decisions signed off — draft in Requirements
- [ ] Course outline and 30 exam questions reviewed by an ITS inspector — draft in Course and exam
- [ ] Practical assessment checklist reviewed by an ITS inspector — draft in Practical checklist
- [ ] Certificate wording, validity period and ITS logo approved — draft in Certificate and video script
- [ ] HeyGen sample script approved, Arabic checked by a native speaker, test video made on the free plan — draft in Certificate and video script
- [ ] Supplementary video shortlist confirmed (two counterbalance videos listed in the course outline)
- [ ] Test server and GitHub repository set up for Anas
