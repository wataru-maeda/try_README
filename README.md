# FINTEL Gitflow Proposal

## Main Branches

- ***master***
  - Production. Fintel production system is up and running based on the code
  - Expected no bugs, no BETA, no WIP state in the branch

- ***staging***
  - Pre-production. Expecting Fintel client test the platform and decide whether we can deploy to the production or not.
  - No bugs, not beta, wip status of codes in the branch BEFORE the production release

- ***dev***
  - Development. This is where the development activities goes first
  - Create Pull Request then merged after someone approved code
  - We SHOULD NOT push changes directory. 
  - Use "Squash" option when merging Pull Request

- ***demo***
  - Demo code. Demo system is up and running based on the code.
  - Every time deployment happens, the demo need to be updated at the same time
  - demo === master

## Branch Rules

- ***master***
  - we ***SHOULD NOT*** push any changes/Pull Request directory ***EXCEPT*** hotfix.

- ***staging***
  - We ***SHOULD NOT*** push any changes/Pull Request directory ***UNLESS*** test passed in dev.

- ***dev***
  - We ***SHOULD NOT*** push changes directory. 
  - Use use ***Squash*** option when merging Pull Request

- ***demo***
  - No one need to push any PR to the branch.

## Git Development Flow

- Always create branch from ***master***
- Always make Pull Request to ***dev*** first. After approval on dev, push to ***staging***. Once the package approved, the changes goes to ***master***

### Working on Bug fix

1. Create branch name "fix/FIN-{NUMBER}" from master => push changes
1. After completed, create "fix/FIN-{NUMBER}-dev" from dev
1. Cherry picking commits and stash on "fix/FIN-{NUMBER}-dev"
1. Open Pull Request to the dev