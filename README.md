# github-action

git-hub action we can use it for CICD.

it is also yaml based file

yaml file should be in the .github/workflows/blank.yaml

name: CICD : it is name of the workflows(we can have multiple workflows)

on: [push, workflow_dispatch]  : it indicates the event trigger. push means if we push it from any of the branch event will trigger:  workflow_dispatch:  manual trigger: with updated code.

on:
  push:
    - main      : it will trigger only from main branch(if we push the things from main)

jobs:   jobs is nothing n=but stages, we can have multiple jobs inside one workflopw.

steps: it like the steps inside the jobs, it can be multiple.

example:

jobs:
  BUILD:      ---------------------- name of the job
    runs-on: ubuntu-latest   ------- this job will run on ubuntu-latest

    steps:
    - name: Checkout repository  --- first activity
      uses: actions/checkout@v3

    - name: BUILD the application  --- 
      run: echo "APPLICATION IS BUILDING!"
