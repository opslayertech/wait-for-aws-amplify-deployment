# wait-for-aws-amplify-deployment

GitHub Action to wait for an AWS Amplify Application Deployment

## Usage

```yaml
name: build
on:
  pull_request:

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout Code
        uses: actions/checkout@v4
      
      - name: Wait for AWS Amplify App Deployment
        uses: opslayer/wait-for-aws-amplify-deployment@v2
        with:
          aws-region: ${{ vars.AWS_REGION }}
          aws-role-to-assume: ${{ vars.AWS_ROLE }}
          amplify-id: ${{ vars.AMPLIFY_ID }}
          branch-name: '${{ github.ref_name }}'
          commit-id: '${{ github.event.pull_request.head.sha }}'
```
