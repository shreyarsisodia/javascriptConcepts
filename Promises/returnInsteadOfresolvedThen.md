## If we return a value instead of a promise from a .then() handler, it assumes that the value is a resolved promise. This means that the next .then() in the chain will receive that value as its input, and it will continue executing without waiting for any asynchronous operation.

fetch('https://api.example.com/data')
  .then(response => {

    // Instead of returning a promise, we return a direct value
    return response.json(); // This returns a promise
  })
  .then(data => {

    // This 'data' is the resolved value from the previous handler
    console.log(data);
    return "Processing complete"; // Returning a string value
  })
  .then(result => {

    // 'result' receives the string value from the previous handler
    console.log(result); // Outputs: Processing complete
  })
  .catch(error => {
    console.error('Error:', error);
  });
