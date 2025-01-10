# Dockerfile Bug: Missing requirements.txt

This repository demonstrates a common error in Dockerfiles: attempting to copy a file that doesn't exist in the build context.  The `COPY` instruction in the original `Dockerfile` references `requirements.txt`, but this file is not included in the build context.

The `Dockerfile.fixed` file shows the corrected version, which includes the `requirements.txt` file and addresses the issue.

**To reproduce the bug:**
1. Build the original `Dockerfile` using `docker build -t buggy-app .`
2. Observe the build failure due to the missing `requirements.txt`.

**To see the solution:**
1. Build `Dockerfile.fixed` using `docker build -t fixed-app .`
2. Verify successful build and execution.