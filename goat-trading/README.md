# <h1 align="center"> Hardhat-Foundry Template </h1>

**Template repository for Hardhat and Foundry**

### Getting Started

- Use Foundry:

```bash
forge install
forge test
```

- Use Hardhat:

```bash
npm install
npx hardhat test
```

### Features

- Write / run tests with either Hardhat or Foundry or Both:

```bash
forge test
# or
npx hardhat test
# or
npm test (to run both)
```

- Install libraries with Foundry which work with Hardhat.

```bash
forge install transmissions11/solmate # Already in this repo, just an example
# and
forge remappings > remappings.txt # allows resolve libraries installed with forge or npm
```
