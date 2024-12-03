## A custom polyfill for `Array.prototype.reduce()` to ensure compatibility across all JavaScript environments, including older browsers.

## Overview

The `reduce1` method is a custom implementation of the native `reduce()` function. It allows you to iterate over an array and accumulate a single result, just like `Array.prototype.reduce()`. If the environment doesn't support `reduce()`, you can use this polyfill.

let arr=[4,10,5,11,3]
Array.prototype.reduce1=function(callback,initialValue){
    let acc=0,start=0
    if(initialValue!==undefined)
    acc=initialValue
    else
    acc=this[0]
    for(i=initialValue!==undefined?0:1;i<this.length;i++)
    {
        acc=callback(acc,this[i],i,this)
    }
    return acc;
}
let a=arr.reduce1((acc,curr)=>acc+curr,0)