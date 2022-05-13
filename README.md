# AWS

Practicas del Centro de recursos introductorios de Amazon AWS. Esta aplicación utiliza AWS Amplify, Amazon API Gateway, AWS Lambda y Amazon DynamoDB.

# Módulo 1

## Crear una aplicación web estatica.

En este módulo, usará la Consola de AWS Amplify para implementar los recursos estáticos para su aplicación web.

# Módulo 2

# Crear una función sin servidor.

En este módulo creará una función sin servidor utilizando AWS Lambda.

Codigo de la función JavaScript
`// Define handler function, the entry point to our code for the Lambda service // We receive the object that triggers the function as a parameter exports.handler = async (event) => { // Extract values from event and format as strings let name = JSON.stringify(`Hello from Lambda, ${event.firstName} ${event.lastName}`); // Create a JSON object with our response and store it in a constant const response = { statusCode: 200, body: name }; // Return the response constant return response; };`
JSON:
{
"firstName": "Ada",
"lastName": "Lovelace"
}
