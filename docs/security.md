# Security

The control room must not contain raw secrets.

Safe to document:

- key name
- provider
- scope
- storage location
- rotation date
- owner

Never commit:

- API key values
- OAuth refresh tokens
- passwords
- SSH private keys
- raw `.env` files
- Google OAuth token files

Use least privilege. Each agent should get only the credentials it needs.

Treat any token pasted into chat as needing rotation.

Keep dashboards and gateway APIs private unless deliberately exposed behind authentication.
