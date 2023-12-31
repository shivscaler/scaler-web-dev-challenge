# scaler-web-dev-challenge

Q1. Consider the following complex asynchronous JavaScript scenario using async/await and Promises:

```
function resolveAfter1Second() {
  return new Promise(resolve => {
    setTimeout(() => {
      resolve("Resolved after 1 second");
    }, 1000);
  });
}

function rejectAfter2Seconds() {
  return new Promise((resolve, reject) => {
    setTimeout(() => {
      reject(new Error("Rejected after 2 seconds"));
    }, 2000);
  });
}

async function asyncFunction() {
  try {
    console.log("Start of asyncFunction");
    
    const [result1, result2] = await Promise.all([resolveAfter1Second(), rejectAfter2Seconds()]);
    console.log(result1);
    console.log(result2);
    
    const result3 = await resolveAfter1Second();
    console.log(result3);
    
    console.log("End of asyncFunction");
  } catch (error) {
    console.error("Error in asyncFunction:", error.message);
  }
}

asyncFunction();
```


Your task is to predict and explain the output of the asyncFunction when it is executed. Analyze the behavior of Promise.all, await, and error handling within the async function.


Q2. You are given the following JavaScript code snippet:

```
function outerFunction() {
  var x = 10;

  function innerFunction(y) {
    return x + y;
  }

  return innerFunction;
}

var result = outerFunction()(5);
console.log(result); // Output: ?

```
Your task is to determine the output of the console.log statement. Explain the concept of closure in JavaScript that applies in this scenario and how it affects the execution of the code.
