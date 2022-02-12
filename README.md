# FINTEL Gitflow Proposal

## Main Branches

- **master**: Production. Fintel production system is up and running based on the code. Expected no bugs, no BETA, no WIP state in the branch
- **staging**: Pre-production. Expecting Fintel client test the platform and decide whether we can deploy to the production or not. No bugs, not beta, wip status of codes in the branch BEFORE the production release
- **dev**: Development. This is where the development activities goes first.
- **demo**: Demo. Demo system is up and running based on the code. Every time deployment happens, the demo need to be updated at the same time

## Branch Rules

- **master**: we **SHOULD NOT** push any changes/Pull Request directory **EXCEPT** hotfix.
- **staging**: We **SHOULD NOT** push any changes/Pull Request directory **UNLESS** test passed in dev.
- **dev**: We **SHOULD NOT** push changes directory. 
- **demo**: No one need to push PR to the branch.
## Dev Flow

- Always create branch from **master**
- Always the order of **dev -> staging -> master -> demo** except hotfix. Make Pull Request to **dev** first. After approval on dev, push to **staging**. Once the package approved, the changes goes to **master**
- Use **Squash** option when merging Pull Request

## Branch Name Convention

Recommend to set prefix on branch name to distinguish task type
- **feat**: The task describe new **feature implementation** i.e. `feat/FIN-123`, `feat/sserving`
- **fix**: The task describe **bug fix** i.e. `fix/FIN-123`
- **hotfix**: The task describe **emergency fix on production** i.e. `hotfix/FIN-123`
- **wip**:  The task describe **work on progress**. i.e. `wip/FIN-123`
## Examples
#### Case1: Working on Bug fix

- **Step 1**. Pick a ticket from JIRA
  (1) Check the JIRA board and you select a bug task `FIN-123`
  (2) Move FIN-123 ticket to `In Development` column

- **Step 2**. Work on the bug ticket
  - 1. Create branch name **fix/FIN-123** from **master**
  - 2. Push changes to the branch
  - 3. Before pushing to dev, make sure it functionally working on your locally

- **Step 3**. Make Pull Request to dev
  - 1. Create branch name **fix/FIN-123-dev** from **dev**


1. After implementation completed, create "fix/FIN-{JIRA-TASK-ID}-dev" from **dev**
1. Cherry picking commits and stash on "fix/FIN-{JIRA-TASK-ID}-dev"
1. Open Pull Request to the dev
1. Once it's merged in dev then approved by internal tester, create "fix/FIN-{JIRA-TASK-ID}-dev" from **staging**
1. Cherry picking commits and stash on "fix/FIN-{JIRA-TASK-ID}-dev"
1. Open Pull Request to the staging