# workflow-replayer-bug-reproduction
Code and instructions that you can use to reproduce an error that 
occurs while replaying a Workflow Execution History in Go SDK 1.22.1.

# Reproduce Error with Workflow Replayer

The following steps can be used to reproduce the error, using
the code as it exists on the `main` branch in the git repo,
which references version 1.22.1 of the Go SDK.

1. `cd example`
2. `go test`
3. Observe test failing due to unexpected error
   `unknown field "workerVersioningId" in history.WorkflowTaskCompletedEventAttributes`

Now, checkout the `sdk-v1.19.0` branch in git, run `go mod tidy`, and 
repeat the steps. The code has not changed, only the version of the 
Go SDK (and its dependencies), yet the test now passes.
