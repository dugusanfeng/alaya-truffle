# Writing external scripts

Often you may want to run external scripts that interact with your contracts. alaya truffle provides an easy way to do this, bootstrapping your contracts based on your desired network and connecting to your PlatON client automatically per your [project configuration](../reference/configuration.md).

## Command

To run an external script, perform the following:

```
$ alaya-truffle exec <path/to/file.js>
```

## File structure

In order for external scripts to be run correctly, alaya truffle expects them to export a function that takes a single parameter as a callback:

```javascript
module.exports = function(callback) {
  // perform actions
}
```

You can do anything you'd like within this script, so long as the callback is called when the script finishes. The callback accepts an error as its first and only parameter. If an error is provided, execution will halt and the process will return a non-zero exit code.