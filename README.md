# reduce
```
Array.prototype.customReduce =  function(callback, initialValue) {
    if (typeof callback !== 'function') throw TypeError(`${callback} is not a function`);
    if (this.length === 0 && arguments.length === 1) throw TypeError("Reduce of empty array with no initial value");

    const argsLength = arguments.length;
    const forLength = this.length;
    const forStart = arguments.length === 1 ? 0 : 1;

    let result = argsLength ? this[0] : initialValue;

    for (let i = forStart; i < forLength; i ++) {
        result = callback(result, this[i], i, this);
    }

    return result;
}
```
## Description
Created a customReduce similar to the standard reduce
