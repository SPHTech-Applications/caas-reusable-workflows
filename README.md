# CAAS Reusable Workflows
Repository that will hold all the reusable workflows for the CAAS related github action workflows

1. ***.github/workflows/workflow-dispatch-status-check.yaml*** : This reusable workflow is used to dispatch a remote or local repository , wait for the status and outputs the status

Example on how to trigger the workflow is in the **examples** folder, please refer to the workflow file **workflow-dispatch-runners.yaml**

```
Permissible inputs:

1. workflow
   File to trigger in another workflow.
   example: playwright.yml

2. repo
   Repo to be triggered for workflow dispatch
   example: SPHTech-Applications/caas-e2e

3. environment
  - options:
     - "dev"
     - "stg"
     - "prd"
  
4. branch-ref
   reference branch to trigger in another workflow
   example: main
   default: ${{ github.event.push.ref }}

5. inputs
   input is the one that needed to be send as input parameter to another workflow.
   example: It can be json inputs.
   { "env" : "dev", "source" : "caas-platform-media-extractor-dev" }

6. wait-for-completion
   Optional. If true, this action will actively poll the workflow run to get the result of the triggered workflow. It is enabled by default. If the triggered workflow fails due to either failure, timed_out or    cancelled then the step that has triggered the other workflow will be marked as failed too

7. hosted-machine
   - options:
     - "ubuntu-latest"
     - "linux/arm64"
   default: ubuntu-latest


Permissible secrets:

1. app_id
   app id that need to be sent from the client to get the GH token

2. app_secret
   app secret that need to be sent from the client to get the GH token

3. slack_failure_webhook_url
   slack webhook url in order to send failure notification for the workflow dispatch

```
**Reference:** [https://github.com/marketplace/actions/workflow-dispatch-and-wait](https://github.com/marketplace/actions/workflow-dispatch-and-wait)

8. ***.github/workflows/workflow-dispatch-node-lambda-zip.yaml*** : This reusable workflow is used to dispatch a remote or local repository , deploy nodejs applications to AWS Lambda as specified in the inputs.
```
Permissible inputs:
1. environment
   - options:
     - "dev"
     - "stg"
     - "prd"
     
2. platform
   - options:
     - "ubuntu-latest"
     - "linux/arm64"
 
3. additionalInstallOptions (string)
4. functionName (string) [exclusive of dev suffix]
```
