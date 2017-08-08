# semantic-release condition-travis-enterprise

[![Build Status](https://travis-ci.org/jlengstorf/condition-travis-enterprise.svg?branch=master)](https://travis-ci.org/jlengstorf/condition-travis-enterprise)
[![Coverage Status](https://coveralls.io/repos/jlengstorf/condition-travis-enterprise/badge.svg?branch=master&service=github)](https://coveralls.io/github/jlengstorf/condition-travis-enterprise?branch=master)

[![semantic-release](https://img.shields.io/badge/%20%20%F0%9F%93%A6%F0%9F%9A%80-semantic--release-e10079.svg)](https://github.com/semantic-release/semantic-release)

For enterprise users, [`travis-deploy-once`](https://github.com/semantic-release/travis-deploy-once) fails because it attempts to log into public Travis CI and public GitHub. To work around this, this repo removes the call to `travis-deploy-once`.

## Installation and Usage

In your repo, install `condition-travis-enterprise`:

```sh
npm install -D condition-travis-enterprise
```

In `package.json`, add the following:

```diff
  "release": {
    "githubUrl": "<YOUR_GITHUB_ENTERPRISE_URL>",
    "githubApiPathPrefix": "api/v3",
+   "verifyConditions": "condition-travis-enterprise"
  }
```

### NOTE: If your build process runs tests in a matrix, this _does not_ ensure that `semantic-release` only runs once.

Please [submit a PR](https://github.com/jlengstorf/condition-travis-enterprise/pulls) if you know how to check this on enterprise Travis CI.
