# Contact Validator

A Python utility library to validate, format, and mask contact details (emails and phone numbers) before database insertion, protected by automated GitHub Actions CI pipelines and strict branch protection rules.

---

## Features

- **Email Validation (`is_valid_email`)**: Validates standard email address formats using regex pattern matching.
- **Email Masking (`mask_email`)**: Obfuscates the local part of an email address for data privacy (e.g., `priya@example.com` -> `pr***@example.com`).
- **Phone Validation (`is_valid_phone`)**: Verifies that phone inputs contain exactly 10 digits (allowing hyphenated formatting).
- **Phone Normalization (`normalize_phone`)**: Strips non-digit characters to return uniform 10-digit strings (e.g., `555-123-4567` -> `5551234567`).

---

## Project Structure

```text
├── .github/
│   └── workflows/
│       ├── test.yml                 # Runs test suite on PRs targeting main
│       └── coverage.yml             # Enforces >= 85% test coverage policy
├── src/
│   ├── __init__.py                  # Package initializer
│   └── contact_validator.py         # Production validation and masking logic
├── tests/
│   └── contact_validator_test.py    # Unit tests and coverage edge cases
├── requirements.txt                 # Dependencies (pytest, coverage, pytest-cov)
└── README.md                        # Documentation
