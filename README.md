# Ashoka AI Lab Template

## CI/CD
### Prerequisites:
- Project:
    - The project must have a unique `PROJECT_IDENTIFIER`
        - Based on this the following project URL will be created
        - `https://PROJECT_IDENTIFIER.ai.ashoka.org`
    - The project should be set up in such a way that endpoints and secrets for the third-party services can be defined in `.env` files
- Chainlit app:
    - The Chainlit app must be started with `chainlit run app.py` command.
    - The Chainlit app must have a unique port.

### One-time org setup:
1. In your Github org, add the following Github action secrets:
    - `AILABS_SERVER_DEPLOYMENT_KEY`: SSH Deployment private key.
        - Get this from the Ashoka ITI team.
    - `AILABS_SERVER_REMOTE_HOST`: Remote host IP.
        - Get this from the Ashoka ITI team.
    - `AILABS_SERVER_REMOTE_USER`: `webservices`

### Project setup

1. In your Github project repo add the following Github action secrets:
    - `PROJECT_IDENTIFIER`: A unique identifier for your project.
    - `PROJECT_PORT`: A unique port number for your project backend service.
    - `PROJECT_ENV`: Content of the `.env` file
    - `PROJECT_STAGING_ENV`: Content of the `.env` file for the staging server
2. Email Ashoka ITI (websupport@ashoka.org) with the following details to set up the XXX.ashoka.org domain names:
    - Link to Github repo
    - Project identifier
3. Copy the `.github/workflows/deploy.yml` file from this template to `.github/workflows/deploy.yml` in your project repo.

## Auto-deployment:
- Any push to the `main` branch will result in auto-deployment to the LIVE AILabs server.
- Any push to the `staging` branch will result in auto-deployment to the STAGING AILabs server.
