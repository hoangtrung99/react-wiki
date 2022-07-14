

```yaml
# .github/workflow/deploy.yaml
name: deploy LP

on:
  push:
    branches:
      - main
  pull_request:
    branches:
      - main
    types: [closed]

jobs:
  build-and-deploy-staging:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3

      - name: Cache package
        id: yarn-cache    
        uses: actions/cache@v3
        with:
          path: node_modules
          key: ${{ runner.os }}-yarn-${{ hashFiles('**/yarn.lock') }}
          restore-keys: ${{ runner.os }}-yarn-

      - uses: actions/setup-node@v3
        with:
          node-version: 17.6.0
      - run: yarn install
      - run: yarn build
      - run: yarn export

      - name: Configure AWS credentials
        uses: aws-actions/configure-aws-credentials@v1
        with:
          aws-access-key-id: ${{ secrets.AWS_ACCESS_KEY }}
          aws-secret-access-key: ${{ secrets.AWS_SECRET_KEY }}
          aws-region: ${{ secrets.AWS_SECRET_KEY }}
      - name: Copy files to the S3 Bucket with the AWS CLI
        run: |
          echo "AWS S3 Sync"  
          aws s3 sync out <bucket>
          echo "AWS CF reset"
          aws cloudfront create-invalidation --region <region> --distribution-id <cf-dist-id> --paths "/*"
```

```js
// CloudFront Function - replace route
function handler(event) {
  var request = event.request;
  var uri = request.uri;
  if (uri.endsWith("/")) {
    request.uri += "index.html";
  } else {
    if (!uri.includes(".")) {
      request.uri += "/index.html";
    }
  }
  return request;
}
```