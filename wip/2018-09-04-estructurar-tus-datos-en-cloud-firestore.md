# ¿Cómo estructurar tus datos en Cloud Firestore?

Cloud Firestore es una base de datos basada en documentos, pero, ¿En que se traduce esto?.
Ten en cuenta un documento cualquiera y lo que contiene, ósea, **datos**, pero de manera estructurada y encapsulada en este documento. Al igual que MongoDB, cada documento en Cloud Firestore tiene la forma de un JSON pero que no lo es literalmente, como su antecesor, Firebase Realtime Database.

Entonces si lo almacena como un JSON (JavaScript Object Notation), pongan en su cabeza lo siguiente:

```
{
  firstName: 'Jason',
  lastName: 'Borges',
  age: 32
}
```
{: .language-json}

Lo de arriba es un documento, este ser como un JSON, ya tiene una estructura establecida, además aquí se está encapsulando la información de una persona, la cual cuenta con diferentes tipos de datos: **cadenas|string** para los nombres y **número|number** para la edad.

> Por favor, usen camelcase para los nombres de sus propiedades, para tener todo JS style

Ahora, ¿Qué pasará cuando se quiere almacenar más datos de otras personas?, en ese caso, podríamos imaginarnos algo así:

```
{
  firstName: 'Jason',
  lastName: 'Borges',
  age: 32
},
{
  firstName: 'Freddy',
  lastName: 'Krueger',
  age: 32
}
```
{: .language-json}

Bueno... sí y no, ya que estos dos **objetos**, no pueden vivir en el aire, tal y como están escritos, es aquí donde entra una colección, la cual sería el lugar donde se almacenarán los documentos de forma organizada:

```
villains: [
  ID01: {
    firstName: 'Jason',
    lastName: 'Borges',
    age: 32
  },
  ID02: {
    firstName: 'Freddy',
    lastName: 'Krueger',
    age: 32
  }
]
```
{: .language-json}

Ahora lo particular de esto último es que:
- **villains** sería el nombre de mi colección y estoy usando los corchetes **[]** para hacer referencia de que sería como un array, un array de documentos.
- Cada documento ahora tiene algo extra, las llaves, **ID01** y **ID02**, las cuales me servirán para ubicar a un documento en específico.

Y antes de continuar, recordemos, si bien use JSON's para mostrar el cómo se vería, no es un JSON en sí, literalmente.

## ¿Cómo ubicar un documento dentro de nuestra base de datos?

Ahora veamos un poco de como se vería en JavaScript (hay algunas parte de código faltante y para hacerlo corto, no lo pondré)

```
 const dbFS = firebase.firestore() // Inicializar Firestore
 const collectionRef = dbFS.collection('villains')
 const documentRef = dbFS.collection('villains').doc('ID01')
 const pathRef = dbFS.doc('villains/ID02')
```
{: .language-js}

Primero hay que inicializar Firestore para poder empezar a usar **collection** y **doc**, los cuales me ayudarán a crear **referencias**, con una referencia, podrás ubicar un documento pero también una colección.

Al usar `dbFS.collection('villains')` estamos creando nuestra referencia a la colección **villains**, la cual es la única referencia que me permitirá realizar consultas sobre los diferentes documentos de la colección, agregar un nuevo documento a la colección con un **llave|identificador** único generado por Firebase.

Al usar `dbFS.collection('villains').doc('ID01')`, tendre acceso al documento en sí, con este mismo podré actualizar los datos y eliminarlos. Y con este `dbFS.doc('villains/ID02')`, estoy obteniendo la referencia al documento pero usando *path style*, como se hacía en versiones anteriores de Firebase.

Entonces tendremos 2 tipos básicos de referencias las cuales me permitirán realizar diferentes acciones.

## Subcolecciones

Una subcolección sería como una colección dentro de un documento pero en realidad es una colección asociada a un documento. Si tomamos nuestro ejemplo de JSON, se veria mas o menos así:

```
villains: [
  ID01: {
    firstName: 'Jason',
    lastName: 'Borges',
    age: 32,
    victims: [
      v01: {
        fullName: 'Bruce Wayne'
      },
      v02: {
        fullName: 'Clark Kent'
      }
    ]
  },
  ...
  ...
  ...
]
```
{: .language-json}

Y para poder obtener la referencia de una subcolección, deberíamos encadenar `collection` a nuestra referencia anterior: `dbFS.collection('villains').doc('ID01').collection('victims')`. Con esto podremos realizar las mismas acciones mencionadas anteriormente para una colección. Esto mismo pasaría para la referencia de un documento dentro de una subcolección.

Pero recuerden, una subcolección es una colección asociada a un documento y por eso es que, al tener una subcolección en un documento, esta subcolección no incrementara el tamaño del documento pero no se podrá realizar consultas entre subcolecciones.

Hay más temas pendientes a **¿Cómo estructurar tus datos en Cloud Firestore?**, las cuales lo seguiré en posteriores publicaciones, al menos 2 publicaciones más.




