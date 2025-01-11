## If we return a value instead of a promise from a .then() handler, it assumes that the value is a resolved promise. This means that the next .then() in the chain will receive that value as its input, and it will continue executing without waiting for any asynchronous operation.

fetch('https://api.example.com/data')
  .then(response => {
  
    Instead of returning a promise, we return a direct value
    
   return response.json(); // This returns a promise
  })
  .then(data => {

      This 'data' is the resolved value from the previous handler
  console.log(data);
  return "Processing complete"; // Returning a string value
    
     if we do not return anything and chain the .then handler we will get undefined in data unlike when we chain promise with a resolve with  
     .then()
  })
  .then(result => {

    result' receives the string value from the previous handler-because we are returning a string if we dont return anything we will get 
    undefined
  console.log(result); // Outputs: Processing complete
  })
  .catch(error => {
    console.error('Error:', error);
  });
