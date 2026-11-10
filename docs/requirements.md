# POC requirements

What Anas and Kashif build and test in weeks 2–4. Each requirement passes only when its acceptance check works in the week 5 demo. Values marked *proposed* are Kashif's to confirm before build starts.

## Roles

| Role | Who | Can do |
| --- | --- | --- |
| Learner | Operator or trainee | Register, take the course and exam, download own certificate |
| Evaluator | ITS inspector | See learners who passed theory, record the practical assessment |
| Admin | ITS training staff | Create courses, lessons and questions; view learners and results; revoke a certificate |
| Public | Anyone with the QR code | See whether a certificate is valid |

## Functional requirements

| ID | Requirement | Acceptance check |
| --- | --- | --- |
| R1 | Home page and catalogue showing the Forklift Operator (Counterbalance) course | Course card shows title, duration, language and a short description |
| R2 | Arabic and English, switchable on every page | Arabic renders right to left with no broken layouts on desktop and phone |
| R3 | Sign-up and login with email and password; password reset by email | A new learner registers and logs in within 2 minutes |
| R4 | Course player with modules and lessons: video (YouTube embed or uploaded file), PDF, text | Learner moves through all modules; progress shows as a percentage |
| R5 | Next module unlocks only when the previous one is complete | Skipping ahead is blocked |
| R6 | Final exam: random draw from the question bank (*proposed*: 20 of 30), pass mark (*proposed*: 80%), attempts (*proposed*: 2) | Each attempt gets a different question order; a third attempt is blocked |
| R7 | Practical assessment form for the evaluator, on a tablet | Evaluator marks each checklist item, adds a note and signs; any failed critical item fails the assessment |
| R8 | Certificate issued only when theory and practical are both passed | Learner who failed the practical gets no certificate |
| R9 | Certificate PDF with name, ID number, certificate number, course, scores, evaluator, issue date, expiry date (*proposed*: 3 years) and QR code | PDF downloads and prints cleanly on A4 |
| R10 | Public verification page opened by the QR code: valid, expired or revoked | Scanning on a phone shows the right status within 3 seconds |
| R11 | Admin: add or edit courses, lessons and questions; upload question bank from Excel | Admin adds a new lesson without developer help |
| R12 | Admin: learner list with progress, exam scores, practical result and certificate status; export to Excel | Export opens in Excel with one row per learner |
| R13 | Audit trail of exam attempts, practical results and certificate changes | Every record shows who, what and when |

## Non-functional requirements

- Works on the latest Chrome, Edge and Safari, on desktop and phone.
- HTTPS only; passwords hashed; personal data limited to what the certificate needs.
- Hosted on one Linux server in Docker, with a nightly database backup.
- Certificate numbers cannot be guessed (random, not sequential).
- Certificate says "ITS Certificate of Completion", never "accredited", until a licence is granted.

## Data the system stores

| Entity | Key fields |
| --- | --- |
| User | Name (Arabic and English), email, phone, ID or Iqama number, role, language |
| Course | Title, description, equipment type, version, status |
| Module / Lesson | Order, type (video, PDF, text), content link, duration |
| Question | Module, text (AR/EN), four options, correct answer, active flag |
| Exam attempt | User, questions drawn, answers, score, pass or fail, date |
| Practical assessment | User, evaluator, checklist results, notes, signature, date, result |
| Certificate | Number, user, course, issue date, expiry date, status, QR link |

## Decisions for Kashif before build starts

- [ ] Exam: questions drawn, pass mark and attempts
- [ ] Certificate validity period
- [ ] Waiting time before a retake after two failed attempts
- [ ] Whether learners need an ID or Iqama number on the certificate
- [ ] Domain name for the POC (for example a test subdomain of the ITS site)
