## Questions

1. How would you scale this system to:

- 1M+ leads
- Multiple enrichment providers
- CRM integrations
- Campaign automation

2. Team & Process
   If you joined Al Sales Doctor:

- First 90-day engineering priorities
- Team structure (who to hire first), assuming you are the only engineer now
- Dev process (CI/CD, reviews, releases)

3. Tradeoffs
   What shortcuts did you take due to time?

## Answer

### 1M+ Leads

here the things what I think need to do to improve this current project to scale to 1M+ leads:

- Enable UUID V7 for lead IDs to support cursor pagination
- Change Offset pagination to Cursor-based pagination
- Implement Authentication & Authorization
- Enable Rate Limiting & Caching with Upstash Redis
- Implement Bulk Import/Export functionality
- Implement Data Retention & Archiving
- Implement Data Backup & Recovery
- Implement Logging & Monitoring Mechanism may be using Sentry & Grafana

### Multiple enrichment providers

- Implement API key management for multiple providers
- Implement proper integrations for each provider
- Implement error handling and retry logic
- Implement rate limiting and quotas
- Implement data mapping for each provider
- Preparing fallback logic for each provider

### CRM integrations

- Implement proper webhook integration for each CRM
- Implement proper API integration for each CRM
- Implement proper data mapping for each CRM
- Preparing fallback logic for each CRM

### Campaign automation

let say it will be multiple campaign running on the same day means we also need to prepare Queueing system to handle the load:

- Implement Queuing system for campaign automation
- Implement DLQ for failed campaigns
- Implement retry logic for failed campaigns
- Implement monitoring for campaign automation
- Using Kafka / RabbitMQ / SQS for queuing
  For the automation we can used CRON jobs for campaign automation, then connecting it with the queuing system

### First 90-day engineering priorities

If I joined AI Sales Doctor, my first 90-day engineering priorities would be:

- Create standard and SOP to make sure DX on the future will be scalable and maintainable
- Create standard CI/CD pipeline for deployment
- Prepare infrastructure as code for deployment
- Setup monitoring and alerting system
- Setup Unit Testing & End to End Testing Standards
- Setup Code Review Process
- Setup Code Formatting & Linting Standards
- Setup Documentation Standards
- Setup Security Standards
- Setup Scrum Board & Documentation for project management per each features

### Team structure (who to hire first)

Based on the current state of the project and the priorities, here's who I'd recommend hiring first:

1. **Senior Backend Engineer** (immediate)
   - Handle database schema changes, pagination, authentication, and rate limiting
   - Implement bulk operations and data archiving
   - Set up monitoring and logging infrastructure

2. **DevOps Engineer** (week 2-4)
   - Set up CI/CD pipeline
   - Implement infrastructure as code
   - Configure monitoring and alerting systems

3. **Frontend Engineer** (week 4-6)
   - Implement cursor-based pagination
   - Build admin dashboard for API key management
   - Create data visualization for monitoring

4. **QA Engineer** (week 6-8)
   - Set up unit testing and end-to-end testing standards
   - Implement code review processes
   - Create testing automation

### Dev process (CI/CD, reviews, releases)

- Start with planning and create target release branch
- 1 Ticket on Jira = 1 Branch on Github
- 1 Branch = 1 Pull Request (PR)
- Commit should using conventional commit format
- Unit testing is a mandatory for each feature
- Will be have formatted, linter, and type checking for each commit
- 1 PR must be success running CI/CD pipeline
- CI/CD pipeline will be include unit testing, end-to-end testing, and deployment
- 1 Pull Request (PR) will be always targeting release branch (release/v1.0.0, v1.2.0)
- PR will be reviewed by at least 1 other engineer
- After PR is approved, it will be merged to release branch
- Each release branch will be deployed to release environment and able to used for testing
- After testing is done, it will be merged to main branch and deployed to staging environment
- After business team validation, it will be create a released tag and deployed to production environment
- If there is a bug on production, it will be create a hotfix branch and deployed to production environment

### What shortcuts did you take due to time?

- Make the things simple and straightforward
- Cut / Simplify some features that not critical for MVP
- Create SOP and Documentation on the Go, Focus on making things happens first
- Make the things work first, then optimize later
- Sometimes make decision based on gut feeling rather than perfect analysis
- Focus on delivering value quickly rather than perfect implementation
- Take only critical testing, skip edge case testing
