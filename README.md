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
        uses: opslayer/wait-for-aws-amplify-deployment
        with:
          aws-access-key-id: ${{ secrets.AWS_ACCESS_KEY_ID }}
          aws-secret-access-key: ${{ secrets.AWS_SECRET_ACCESS_KEY }}
          aws-region: ${{ secrets.AWS_REGION }}
          amplify-app-id: '${{ secrets.AMPLIFY_APP_ID }}'
          branch-name: '${{ github.ref_name }}'
          commit-id: '${{ github.event.pull_request.head.sha }}'
```
