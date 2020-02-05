# Introduction

Public Helm chart repo

## Adding Charts

Follow the steps below to add a new chart to the repo

1. `git clone https://github.com/krg7880/charts.git`
2. `helm create <chart_name>` - Create a new chart
3. `helm package <chart_name>` - Package up the chart as a \*.tgz tarball
4. `helm repo index .` - Generate or update an existing index.yaml
5. `git add .` - Add the index.yaml and the .tgz tarball
6. `git commit -m "<your commit message>"` - Commit your changes

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

## Searching For Chars

```
helm search repo <chart>
```
