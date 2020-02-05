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
