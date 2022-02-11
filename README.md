# FINTEL Gitflow Proposal

## Current Main Branches

- master
  - Production code.
  - Fintel production system is up and running based on the code
  - Expected no bugs, no BETA, WIP state of changes
  - We SHOULD NOT push any changes/Pull Request directory EXCEPT hotfix.

- staging
  - Pre-production code.
  - This is where the final test comes in.
  - No bugs, not beta, wip status of codes in the branch BEFORE the production release
  - We SHOULD NOT push any changes/Pull Request directory UNLESS test passed in dev.

- dev
  - Development code.
  - This is where the development activiies goes first
  - Create Pull Request then merged after someone approved code
  - We SHOULD NOT push changes directory. 
  - Use "Squash" option when merging Pull Request

- demo: Demo code
  - Demo code.
  - Fintel demo system is up and running based on the code.
  - Everytime deployment happens, the demo branch also need to be updated
  - demo branch should have the same status of master branch

## Working on Bug fix

ALWAYS CREATE BRACNH FROM MASTER


