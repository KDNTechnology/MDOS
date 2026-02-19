# MDOS
Medical Doctor Open System v5

\# MDOS — Medical Doctor Open System  

\### A Free, Modular, Event‑Sourced Clinical Operating System



MDOS is a \*\*fully free\*\*, \*\*open\*\*, and \*\*modular\*\* clinical data system designed to be assembled entirely in Python, migrated to Rust for performance and safety, and eventually paired with a UI that reconstructs patient state from pure event logs.



MDOS does \*\*not\*\* diagnose, interpret, or override clinical judgment.  

It records \*\*only what happened\*\*, and reconstructs state on demand.



This project is released freely for anyone to use, study, extend, or build upon.

******
Notes by Human
You may require python packages to use this product.
annotated-doc==0.0.4
annotated-types==0.7.0
anyio==4.12.1
bidict==0.23.1
blinker==1.9.0
certifi==2026.1.4
cffi==2.0.0
charset-normalizer==3.4.4
click==8.3.1
colorama==0.4.6
dnspython==2.8.0
eventlet==0.40.4
fastapi==0.128.0
Flask==3.1.2
flask-cors==6.0.2
Flask-SocketIO==5.6.0
greenlet==3.3.1
h11==0.16.0
idna==3.11
itsdangerous==2.2.0
Jinja2==3.1.6
MarkupSafe==3.0.3
pycparser==3.0
pycryptodome==3.23.0
pydantic==2.12.5
pydantic_core==2.41.5
PyNaCl==1.6.2
pyreadline3==3.5.4
python-engineio==4.13.0
python-socketio==5.16.0
requests==2.32.5
simple-websocket==1.1.0
starlette==0.50.0
typing-inspection==0.4.2
typing_extensions==4.15.0
urllib3==2.6.3
uvicorn==0.40.0
Werkzeug==3.1.5
wsproto==1.3.2

accept my pip freeze as an apology.

Medical Doctor Open System is project is a free project.  This project is currently intended as a sort of assessment scaffolding for a singular doctor, which can project an html view of information derived from patient event data such as vitals.  There is also 80+ potential modules listed outside of orderly/ which need to be converted also to this style and process.  Please expect new commitments here as we work to improve to v6.
Please contact us if you want to be a part of the team.

---



\## Vision



MDOS is built on a simple truth:



> \*\*A patient’s “record” is not a static object — it is a cryptographically signed event stream.  

> The UI is a reconstruction. The state is an illusion. The events are the truth.\*\*



Everything in MDOS is:



\- atomic  

\- sovereign  

\- immutable  

\- replayable  

\- auditable  

\- framework‑free  



The long‑term plan:



1\. \*\*Python\*\* — learn the vocabulary, assemble the modules, corner the event model into submission.  

2\. \*\*Rust\*\* — port the core reducer, dispatcher, and event engine for safety and speed.  

3\. \*\*UI\*\* — build a unified event viewer that reconstructs patient state from events.  

4\. \*\*Crypto\*\* — allow patient data to exist only as encrypted event logs + keys.



MDOS is designed so that clinicians can expand vocabulary, engineers can assemble the system, and patients can remain sovereign.



---



\## Why MDOS Exists



Most medical systems today are:



\- monolithic  

\- opaque  

\- hard to extend  

\- full of hidden logic  

\- difficult to audit  

\- tied to proprietary vendors  



MDOS takes the opposite approach.



It is:



\- pure Python  

\- event‑sourced  

\- modular at the clinical level  

\- easy to integrate  

\- easy to test  

\- easy to replace  

\- easy to understand  



Every clinical domain is represented as a \*\*standalone module\*\* with:



1\. \*\*Event Schemas\*\* — what happened  

2\. \*\*Projections\*\* — what the doctor needs to see  



No module depends on any other.  

No module hides logic.  

No module interprets clinical meaning.



---



\## Core Principles



\### Event‑Sourced  

All clinical data is stored as \*\*immutable events\*\*.  

State is derived by replaying events through projections.



\### Modular  

Each clinical domain is its own file.  

You can add, remove, or replace modules without affecting the rest of the system.



\### Transparent  

There is no hidden logic.  

Every rule is visible in the code.



\### Clinician‑Centered  

Modules reflect real clinical workflows:



\- assessments  

\- histories  

\- screenings  

\- treatments  

\- updates  

\- resolutions  



\### Framework‑Free  

No Django.  

No Flask.  

No ORM.  

No external dependencies.  

Just Python.



---



\## Included Modules



MDOS ships with a broad set of clinical modules, including:



\- Allergy Profile  

\- Immunization History  

\- Social History  

\- Family History  

\- Substance Use Assessment  

\- Nutrition Assessment  

\- Pain Assessment  

\- Pediatric Assessment  

\- Geriatrics Assessment  

\- Rheumatology Assessment  

\- Dermatology Rash Tracking  

\- Endocrine Diabetes Monitoring  

\- Infectious Disease Assessment  

\- Oncology History  

\- Obstetric History  

\- Neonatal Assessment  

\- Psychiatric Symptom Tracking  

\- Immunologic Assessment  

\- And more as clinicians expand vocabulary  



Each module contains:



\- \*\*Event Schemas\*\*  

\- \*\*Latest Snapshot Projection\*\*  

\- \*\*History Projection\*\*  



All modules follow the same structure for maximum clarity.



---



\## How MDOS Works



\### 1. Log Events  

Your application emits events like:



```json

{

&nbsp; "type": "PainAssessmentRecorded",

&nbsp; "patient\_id": "123",

&nbsp; "timestamp": "2026-02-14T22:00:00Z",

&nbsp; "recorded\_by": "clinician\_a",

&nbsp; "pain\_score": 7

}

2\. Feed Events Into Projections

Each module exposes projection classes:



python

proj = LatestPainAssessmentProjection()

proj.apply(event)

3\. Reconstruct State

There is no stored “patient record.”

The UI reconstructs state by replaying events.



4\. Add Persistence (Optional)

You may store:



raw event logs



cryptographically signed event streams



encrypted patient keys



But the truth is always the event log.



Who This Is For

Engineers

Build clinical systems without fighting monoliths



Extend modules without breaking anything



Replay events for debugging or audits



Integrate with any stack



Port the core to Rust when ready



Clinicians

See clean, structured, clinically meaningful data



Review histories without noise



Trust that nothing is hidden or auto‑interpreted



Expand vocabulary as needed



Researchers

Analyze event streams



Build reproducible datasets



Run projections for cohort studies



License

This project is released free for all, with no restrictions on use, modification, or distribution.

You may:



use it in clinics



integrate it into products



fork it



extend it



commercialize it



teach with it



research with it



MDOS is a gift to the world.



Contributing

Contributions are welcome.

New modules should follow the existing pattern:
EVENT\_SCHEMAS = {...}
LatestXProjection

X HistoryProjection
No dependencies.
No side effects.
No interpretation.

Future Directions

Rust core engine
Unified event viewer UI
Cryptographic patient identity
Clinician‑driven vocabulary expansion
Real‑time reducer pipelines
Multi‑clinic interoperability

Contact
Mike Mabes
Kernel Distributed Node Technology
goodstewardeos@gmail.com

