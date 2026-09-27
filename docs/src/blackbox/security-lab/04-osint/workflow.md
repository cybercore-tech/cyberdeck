# OSINT workflow

OSINT tools use a separate workspace and browser profile from personal
browsing. Cases should be organized by identifier, not by private account
name.

```text
SecurityLab/
├── repos/
├── cases/
├── datasets/
├── reports/
└── quarantine/
```

For every case, record the question, authorization, collection time, source
URLs, hashes of downloaded artifacts, transformation steps, and retention
decision. Do not mix personal cookies, browser profiles, or cloud credentials
with collection tooling.
