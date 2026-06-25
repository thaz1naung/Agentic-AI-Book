# Security

This repo discusses AI agents, tools, automation, and DevOps workflows. Please keep examples and reports safe by default.

## Do Not Submit Secrets

Do not submit:

- API keys
- tokens
- passwords
- private configs
- credentials
- `.env` files
- private customer or company data

If you accidentally include a secret, rotate it immediately before opening an issue or pull request.

## Automation Safety

Do not include destructive automation examples without a clear lab-only warning.

Examples that delete files, modify infrastructure, rotate credentials, run shell commands, or mutate production systems should be clearly marked as unsafe outside a controlled lab.

Agent/tool examples should be safe by default.

## Reporting Security Concerns

If a private security contact exists, use that private channel.

If no private channel exists, ask the maintainer before posting sensitive details publicly. A short public issue like "I found a possible security concern; where should I report details?" is safer than posting exploit details.
