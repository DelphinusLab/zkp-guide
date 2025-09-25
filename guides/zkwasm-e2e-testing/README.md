# ZKWasm E2E Testing

[Repo](https://github.com/ZhenXunGe/playground-e2e-tests)

## Overview

The E2E Testing framework is a customisable solution for testing majority of the features of ZKWasm Playground (ZKP).

For complete documentation please see repo's [README](https://github.com/ZhenXunGe/playground-e2e-tests/blob/main/README.md)

## Quick Start

### 1. Install dependencies

```
npm install
```

### 2. Update Configs

`.env`

```
-CHAIN_IDS="$REPLACE_WITH_TEST_NET_CHAIN_ID_NUMBER ..."
```

`src/config.ts`

```
server_url: "http://localhost:$REPLACE_WITH_REST_SERVER_PORT",
privateKey: "$REPLACE_WITH_YOUR_METAMASK_NODE_PRIVATE_KEY",

export const NetworkConfigs = [
  {
    chainId: 97,
    name: "bsctestnet",
    rpcUrl: "https://data-seed-prebsc-1-s3.binance.org:8545",
  },
];
```

Example

```
export const NetworkConfigs = [
  {
    chainId: 97,
    name: "bsctestnet",
    rpcUrl: "https://data-seed-prebsc-1-s3.binance.org:8545",
  },
];
```

### 3. Run all test scripts

```
bash scripts/all_tests.sh
```

## Tips

### Automating Testing of Production Sample Images

`TEST-BRANCH-PRODUCTION-IMAGES` branch of the E2E repo provides many previous production images that can be used to test local deployment.


https://github.com/ZhenXunGe/playground-e2e-tests/tree/TEST-BRANCH-PRODUCTION-IMAGES

```
git clone git@github.com:ZhenXunGe/playground-e2e-tests.git e2e

cd e2e

git checkout TEST-BRANCH-PRODUCTION-IMAGES

bash scripts/cli/run_cli_tests.sh
```

For more documentation please this
[README](https://github.com/ZhenXunGe/playground-e2e-tests/blob/TEST-BRANCH-PRODUCTION-IMAGES/README.md#running-zkwasm-service-cli-tests).

