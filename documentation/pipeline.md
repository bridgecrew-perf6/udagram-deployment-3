# Pipeline

app integrates with `CircleCi` to automate install, build, deploy process.

The CI/CD pipeline exists in `.circleci/config.yml` file.

---

## Orbs

Three orbs are required to run the `udagram` workflow and jobs:

- `circleci/node@4.1.0`
- `circleci/aws-cli@2.0.3`
- `circleci/aws-elastics-beanstalk@1.0.0`

## Jobs

- Install Node 16.13
- Check Node Version
- Checkout code
- Setup AWS CLI
- Setup EB CLI
- Install Frontend Dependencies
- Build Frontend
- Install Backend Dependencies
- Build Backend Dependencies
- Deploy Frontend Application
- Deploy Backend Application

## Scripts

Scripts are defined in `package.json` file in the root folder

```json
    "frontend:install": "cd udagram-frontend && npm install",
    "frontend:build": "cd udagram-frontend && npm run build",
    "frontend:deploy": "cd udagram-frontend && npm run deploy",
    "backend:install": "cd udagram-api && npm install",
    "backend:build": "cd udagram-api && npm run build",
    "backend:deploy": "cd udagram-api && npm run deploy"
```
