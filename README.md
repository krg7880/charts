# Introduction

Public Helm chart repo

## Adding Charts

Follow the steps below to add a new chart to the repo

1. `git clone https://github.com/krg7880/charts.git`
2. `helm create <chart_name>`
3. `helm package <chart_name>`
4. `helm repo index .`
5. `git add <chart_name>`
6. `git commit index.yaml <chart_name> -m "<your commit message>"`

## Adding The Chart Repo

To add this repo as a source for charts, follow the steps below:

### Private Repo

To add a private repo, you need to specify your credentials.

```
helm repo add - username <your_github_username> - password <your_github_token> <repo_name> 'https://raw.githubusercontent.com/<your_org>/charts/master/
```

### Public Repo

To add a public repo, run the following command:

```
helm repo add <repo_name> https://raw.githubusercontent.com/<your_org>/charts/master/
```
