# CI/CD Pipeline

This repository helps to maintain the steps to create a CI/CD pipeline using GitHub Actions.

## List of Events to Trigger an Action and What Actions Need to Run

### Name
- Name of the workflow

### On
- It can have push, pull request, releases
  - If multiple triggers are used: `[push, pull_request]`
  - It can have another event underneath that like branch, schedule

### Workflow_dispatch
- For manual triggering of the workflow

### Job
- It defines what needs to be run
  - **Job name**: It must have alphabets and underscores
  - **runs-on**: Define the OS that needs to be used to run the workflow
    - If multiple OS is used, define it with matrix

### Steps
- Tasks within the job
  - **name**: Description of the step
  - **uses**: This defines the action that needs to run in any OS

    **Image syntax:**
    ```markdown
    ![Alt text](C:\Users\PJAIN6\OneDrive - Cox Automotive\Documents\GHA\CICDpipeline\uses_event_actions.png "Actions")
    ```
    
  - **run**: Execute commands in OS
    - Single line command: `run: {command}`
    - Multi line command:
      ```yaml
      run: |
        {Command}
        {Command}
      ```

### With
- This is a conditional part which creates a dependency on previous job