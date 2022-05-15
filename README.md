# AWS

_Esto no es una guía, son notas a mi parecer relevantes de la verdadera guía en:_ <https://aws.amazon.com/es/getting-started/hands-on/build-web-app-s3-lambda-api-gateway-dynamodb/>

Practicas del Centro de recursos introductorios de Amazon AWS. Esta aplicación utiliza AWS Amplify, Amazon API Gateway, AWS Lambda y Amazon DynamoDB.

# Módulo 1

## Crear una aplicación web estática.

En este módulo, usará la Consola de [AWS Amplify](https://aws.amazon.com/es/amplify/hosting/) para implementar los recursos estáticos para su aplicación web.

# Módulo 2

# Crear una función sin servidor.

En este módulo creará una función sin servidor utilizando [AWS Lambda](https://aws.amazon.com/es/lambda/?e=gs2020&p=build-a-web-app-two).

Código de la función JavaScript
// Define handler function, the entry point to our code for the Lambda service
// We receive the object that triggers the function as a parameter
`exports.handler = async (event) => {`
// Extract values from event and format as strings
`let name = JSON.stringify(`Hello from Lambda, ${event.firstName} ${event.lastName}`);`
// Create a JSON object with our response and store it in a constant
`const response = { statusCode: 200, body: name };`
// Return the response constant return response; };

### JSON:

`{ "firstName": "Ada", "lastName": "Lovelace" }`

## Conceptos clave

**Servicio informático:** se trata de un servicio que brinda potencia de procesamiento informático.

**Función sin servidor:** es una porción del código que ejecutará un servicio informático, bajo demanda.

**Lambda Trigger:** se trata del tipo de evento que permitirá la ejecución de la función de Lambda (sin servidor). Puede ser otro servicio de AWS o un aporte externo.

# Módulo 3: enlazar una función sin servidor a una aplicación Web

## En este módulo implementará la función sin servidor utilizando API Gateway.

[API Gateway](https://aws.amazon.com/es/api-gateway/?e=gs2020&p=build-a-web-app-three) cumplirá la función de capa intermedia entre el cliente HTML que creamos en el Módulo Uno y el backend sin servidor que creamos en el Módulo Dos.

<https://d4kquj2ued.execute-api.us-west-1.amazonaws.com/dev>

## Conceptos clave

**RESTful API REST** significa “Transferencia de Estado Representacional” y se trata de un patrón arquitectónico para crear servicios Web. API significa “interfaz de programa de aplicación”. Por lo tanto, la RESTful API implementa el patrón arquitectónico.

**Métodos de solicitud HTTP:** los métodos HTTP están diseñados para permitir la comunicación entre clientes y servidores. Los métodos como GET o PUT definidos por el protocolo HTTP se utilizan para indicar qué acción realizar en los recursos.

**CORS:** los mecanismos CORS (intercambio de recursos de origen cruzado) utilizan encabezados HTTP para indicarle al navegador que debe permitir que una aplicación Web específica se ejecute en un origen (dominio) y que tenga permiso para acceder a los recursos seleccionados de un servidor en otro origen.

**Borde optimizado:** es un recurso que usa la infraestructura global de AWS para asistir mejor a los clientes de todo el mundo.

# Módulo 4: crear una tabla de datos

## En este módulo creará una tabla DynamoDB y habilitará la función Lambda para almacenar datos allí.

En este módulo crearemos una tabla para conservar los datos utilizando [Amazon DynamoDB](https://aws.amazon.com/es/dynamodb/).
DynamoDB es un servicio de base de datos clave-valor, por lo que no es necesario crear un esquema para los datos.
Además, usaremos el servicio [AWS Identity and Access Management (IAM)](https://aws.amazon.com/es/iam/?e=gs2020&p=build-a-web-app-four) para concederles a los servicios los permisos necesarios para interactuar entre sí, de forma segura. Específicamente, permitiremos que la función Lambda creada en el módulo dos escriba en la tabla DynamoDB que creamos recientemente mediante una política IAM.

## Conceptos clave

**Datos persistentes:** almacenamiento de datos para que podamos acceder a ellos en el futuro, independientemente de la ejecución de un programa.

**Base de datos no relacional:** las bases de datos no relacionales no utilizan un esquema tabular de filas y columnas. En lugar de ello, utilizan un modelo de almacenamiento optimizado para los requerimientos específicos de los tipos de datos que se almacenan.

**Base de datos clave-valor:** es un tipo de base de datos no relacional que almacena datos como un conjunto de pares clave-valor en los que la clave sirve como identificador único.

**Clave primaria:** se trata del valor que identificará cada elemento de los datos en una tabla DynamoDB. Este valor también servirá para dividir la tabla de modo que sea más escalable.

**Esquema:** es la organización de los datos que sirve como plano para ver el modo en que se deben construir los datos.

**SDK AWS:** SDK significa “Kit de desarrollo de software”. Los SDK AWS brindan un conjunto de herramientas, bibliotecas, documentación, muestras de código, procesos y guías que les permiten a los desarrolladores crear aplicaciones de software en una plataforma específica.

**Política IAM:** se trata de un documento que define a qué recursos de AWS puede acceder una entidad (p. ej., servicio, usuario, grupo).

# Módulo 5: agregue interactividad a la aplicación Web

## En este módulo, modificará su sitio Web estático para invocar la API y mostrar el texto personalizado ingresado.

Actualizaremos el sitio Web estático para invocar la API REST. Esto agregará la capacidad de mostrar el texto basado en lo que ingresó.

## Conceptos clave

**Implementación de un sitio Web:** Hacer disponible un sitio Web para los usuarios.
**Entorno:** Una etapa como "prod," "dev," o "staging" donde se puede ejecutar una aplicación o sitio web.
**Invocación de una API:** enviar un evento a una API para desencadenar un comportamiento específico.
