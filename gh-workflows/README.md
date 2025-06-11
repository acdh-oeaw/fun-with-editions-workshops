# GitHub Workflows/Actions

## some definitions

### GitHub Actions
> GitHub Actions is a continuous integration and continuous delivery [(CI/CD)](https://en.wikipedia.org/wiki/CI/CD) **platform** that allows you to automate your build, test, and deployment pipeline. [source](https://docs.github.com/en/actions/about-github-actions/understanding-github-actions#overview)

> [!INFO]  
> GitHub Actions is a **platform/service/server** (Linux, Windows, and macOS virtual machines) provided by GitHub to execute any kind of code.

### [GitHub Workflows](https://docs.github.com/en/actions/about-github-actions/understanding-github-actions#workflows)

* > A workflow is a configurable automated process. 
* > Workflows are defined by a YAML file checked in to your repository 
* `.github/workflows/my-super-workflow.yml`

#### Event(https://docs.github.com/en/actions/about-github-actions/understanding-github-actions#events)

> An event is a specific activity in a repository that triggers a workflow run.

* push to (some/any) branch
* new release
* scheduled, e.g. every day at 12:00 (via cron syntax)
* webhook
* manually triggered `on: workflow_dispatch`
* ...

see [here](https://docs.github.com/en/actions/writing-workflows/choosing-when-your-workflow-runs/events-that-trigger-workflows) for a list of events.


#### [Jobs](https://docs.github.com/en/actions/about-github-actions/understanding-github-actions#jobs)
> A **job** is a **set of steps** in a workflow that is executed on the same **runner**.

##### [Steps](https://docs.github.com/en/actions/about-github-actions/understanding-github-actions#jobs)
>  Each step is either a **shell script** that will be executed, **or an action** that will be run. Steps are executed in order and are dependent on each other. Since each step is executed on the same runner, you can share data from one step to another. 

##### [Actions](https://docs.github.com/en/actions/about-github-actions/understanding-github-actions#jobs)
An action is a custom application for the GitHub Actions platform that performs a complex but frequently repeated task. Use an action to help reduce the amount of repetitive code that you write in your workflow files.

#### [Runner](https://docs.github.com/en/actions/about-github-actions/understanding-github-actions#runners)
> A runner is a server that runs your workflows when they're triggered. Each runner can run a single job at a time. 


