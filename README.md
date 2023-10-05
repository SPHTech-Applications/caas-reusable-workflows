# CAAS Reusable Workflows
Repository that will hold all the reusable workflows for the CAAS related github action workflows

1. ***.github/workflows/workflow-dispatch-status-check.yaml*** : This reusable workflow is used to dispatch a remote or local repository , wait for the status and outputs the status
2. ***.github/workflows/workflow-dispatch-node-lambda-zip.yaml*** : This reusable workflow is used to dispatch a remote or local repository , deploy nodejs applications to AWS Lambda as specified in the inputs.
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
