# Compiling Contracts

## Location

All of your contracts are located in your project's `contracts/` directory. As contracts are written in `Solidity` or `cpp(wasm contract)`, all files containing contracts will have a file extension of `.sol` or `cpp`

With a bare alaya truffle [project](../quickstart.md) (created through `alaya-truffle init`), you're given a single `Migrations.sol` file that helps in the deployment process. If you're using a `alaya-truffle Box`, you will have multiple files here.

## Command

To compile a alaya truffle project, change to the root of the directory where the project is located and then type the following into a terminal:

```shell
alaya-truffle compile
```

Upon first run, all contracts will be compiled. Upon subsequent runs, alaya truffle will compile only the contracts that have been changed since the last compile. If you'd like to override this behavior, run the above command with the `--all` option.

```eval_rst
.. _Artifacts:
```

## Build artifacts

Artifacts of your compilation will be placed in the `build/contracts/` directory, relative to your project root. (This directory will be created if it does not exist.)

These artifacts are integral to the inner workings of alaya truffle, and they play an important part in the successful deployment of your application. `You should not edit these files` as they'll be overwritten by contract compilation and deployment.

```eval_rst
.. _dependencies:
```

## Dependencies

You can declare contract dependencies using Solidity's `import` command. alaya truffle will compile contracts in the correct order and ensure all dependencies are sent to the compiler. Dependencies can be specified in two ways:

### Importing dependencies via file name

To import contracts from a separate file, add the following code to your Solidity source file:

```
import "./AnotherContract.sol";
```

This will make all contracts within `AnotherContract.sol` available. Here, `AnotherContract.sol` is relative to the path of the current contract being written.

Note that Solidity allows other import syntaxes as well. See the Solidity `import documentation` for more information.