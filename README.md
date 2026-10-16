# Lab 5: Static Code Analysis — Hotel Booking System

- **Original repository:** https://github.com/SETAPESU26/L5_43_hotel_booking_system.git
- **My fork / clone:** https://github.com/<YOUR-USERNAME>/L5_43_hotel_booking_system  *(replace with your link)*
- **Course:** SETAPESU26 — Lab 5 (Static Code Analysis)

## About
A small hotel room reservation manager: tracks room inventory, books/cancels rooms, computes seasonal rates, generates guest hashes and booking references, and exports a ledger.

## Run
```bash
python3 -m venv venv && source venv/bin/activate
pip install pylint bandit flake8
python hotel_booking_system.py
# optional: export HOTEL_ADMIN_TOKEN="your-token"
```

## Static analysis
```bash
pylint hotel_booking_system.py > pylint_report.txt
bandit -r hotel_booking_system.py > bandit_report.txt
flake8 hotel_booking_system.py > flake8_report.txt
```

| Tool | Before | After |
|------|--------|-------|
| Pylint | 5.32 / 10 | 10.00 / 10 |
| Bandit | 6 issues (2 High, 1 Medium, 3 Low) | 0 |
| Flake8 | 7 violations | 0 |

## Commits
1. `Fix Bandit findings` — eval, os.system, MD5, `random`, hardcoded secret, try/except/pass
2. `Fix Pylint findings` — docstrings, naming, mutable default, f-string, `with open`, main guard
3. `Fix Flake8 findings` — unused import/variable, `is None`, trailing newline

## Files
| File | Purpose |
|------|---------|
| `hotel_booking_system.py` | Cleaned final version |
| `issues.md` | Issue table (17 issues) |
| `reflection.md` | Reflection answers |
| `reports/before/`, `reports/after/` | Tool reports before and after the fixes |
