# ¿Qué es Cloud Firestore?

Es una base de datos NoSQL que se encuentra en la nube, la cual mantiene sincronizados los datos en las aplicaciones, ya sea moviles o web las cuales accedan a ella, esto me permite tener los datos en tiempo real. Ademas esta hecha para poder escalar horizontalmente, lo cual hace que el costo de uso sea mucho bajo en comparación de otros servicios.

## Características principales

### Documentos y colecciones
Los datos se almacenan en documentos y estos de organizan usando colecciones. Un documento puede contener diferentes tipos de datos, desde `cadenas|string` hasta `geopuntos` pero tambien otras colecciones (estas serian llamadas `subcolecciones`).

### Consultas poderosas
A diferencia de la base de tiempo real, Firestore cuenta con una API mas expresiva y poderosa, la cual te permitiria realizar `preguntar` por valores entre diferentes campos, con una cierta cantidad de restricciones.

```
const events = db.collection('eventos')
const query = events
 .where('city', '==', 'cochabamba')
 .where('type', '==', 'hackaton')
```
{: .language-javascript}

### Actualizaciones en tiempo real y modo offline
Los datos se sincronizan entre todos los dispositivos conectados ante cualquier creación, actualización o eliminación, ademas, almacena en cache los datos mas utilizados por tu aplicación para que en el caso tu dispositivo se deconecte de internet, pueda seguir realizando las acción necesarias hasta que se conecte nuevamente y sea actualizada los datos en la nube.

## Soporte de lenguajes y plataformas
Firestore puede conectarse con tu aplicación desde iOS, Android, Web, NodeJS, Java, Python y Go, ademas de contar con la posibilidad de conectarte desde otras plataformas del lado del servidor usando `firebase-admin` con soporte para NodeJS, Java, Python y Go. Tambien puedes administrar los datos desde `Cloud Functions for Firebase`.

## Integración con Angular
Además de usar el SDK Web para Firebase, puedes usar [AngularFire2](https://github.com/angular/angularfire2). AngularFire2 es la libreria oficial para trabajar con Firebase y cuenta con soporte para [Firestore](https://github.com/angular/angularfire2#cloud-firestore).

## Integración con NativeScript
Si estas pensando crear aplicaciones bridge para móviles, puedes usar NativeScript y para este framework, existe su [NativeScript Firebase plugin](https://github.com/EddyVerbruggen/nativescript-plugin-firebase), el cual no es oficial pero es el unico actualmente. NativeScript tiene soporte para usar Angular para la creación de aplicaciones móviles.

## Diferencias entre Cloud Firestore y Firebase Realtime Database
- Ambas son bases de datos en tiempo real pero Firestore es basado en documentos y Realtime Database es un gran JSON.
- Firestore contará con escalamiento horizontal automático luego de que salga del beta y Realtime Database para poder escalar fragmenta tus datos entre múltiples bases de datos (esto ocurre en el [plan Blaze](https://firebase.google.com/pricing/)).
- El precio en Firestore se calcula de acuerdo a las acciones que realizamos (junto al ancho de banda y almacenamiento), mientras que en Realtime Database es solo por el ancho de banda y cantidad de datos.
- La consultas y reglas de seguridad, en Firestore son más poderosas y con más opciones.
- El modo offline para web solo está disponible para Firestore.

> Obviamente, hay mucho mas para hablar sobre sus caracteristicas pero se tocara los puntos por separado en posteriores publicaciones.

## Preguntas y respuestas sobre algunos menciones dentro del artículo
Sobre la mayoria de estos puntos, ire creando publicaciones extra para ahondar sobre ellos.

### 1.- ¿Qué es una base de datos NoSQL?

> Una base de datos NoSQL
> - No cuenta con un lenguaje para realizar consultas, a diferencias de las base de datos relacionales con soporte SQL (Structured Query Language).
> - No utiliza tablas para almacenar los datos y al existir diferentes tipos de base de datos NoSQL, puedes encontrar los que son del tipo llave/valor, base de datos orientado a documentos, etc.
> - No usa un esquema o receta para definir la estructura de donde guardarás tus datos, con esto, cuentas con flexibilidad para guardar los datos.
> - Al tener flexibilidad, no existe el concepto de normalización y es por eso que podrias encontrar datos duplicados.
> - En el caso de de Cloud Firestore, al usar colecciones, no existe una relación fuerte entre colecciones como existiria entre tablas de una base de datos SQL. (Este punto lo tocare en publicaciones posteriores)

### 2.- ¿Qué significa tener una base de datos en la nube?

Tu base de datos se encuentra en internet y por eso necesitarás conexión a internet para poder acceder a ella. Aunque Cloud Firestore cuenta con la opción offline, la cual me permite poder realizar acciones a la base de datos si mi dispositivo no tiene internet, no existe por ahora una opción de pruebas hacia una copia de tu base de datos en tu computadora. Actualmente, se sabe que el equipo de Firebase está trabajando en un emulador, al igual que existe para su base de datos en tiempo real.

### 3.- ¿Qué significa tener los datos en tiempo real?
Cloud Firestore mantiene los datos sincronizados entre todos los dispositivos desde los cuales se conecten, por ejemplo, si existen 5 smartphones y 1 pc conectadas a tu aplicación, y alguien desde alguno de los smartphones actualiza el titulo de una publicación, se actualizaran los cambios en los demas lugares conectados, sin necesidad de actualizar la pagina donde estes o cerrar y abrir la aplicación. Podrias usarlo para un chat, feed de noticias, marcadores para juegos en linea, etc.

### 4.- ¿Qué es escalamiento horizontal?
Si hablamos de escalamiento, debemos tener en mente que **Tu aplicación será utilizada por muchas personas y esto se traducirá en mucho uso de hardware**.
Para ejemplificar, ten en mente esto:

> Tenemos un edificio con capacidad para 100 personas, el cual tiene una puerta, por la cual cada día entra una persona por minuto.

El **edificio** y la **puerta** son el hardware, ahora vamos a lo siguiente:

> Nuestro edificio es tan popular que ahora mas de una persona entra por minuto, algunas veces llega a 50 personas queriendo entrar al mismo tiempo por la misma puerta y ademas de eso, la capacidad de 100 personas del edificio, sobrepasa facilmente ¿Te imaginas eso?

Una solución a eso sería el **agrandar la puerta** y **ponerle más pisos al edificio**, lo cual podria ser viable, pero ¿Qué pasa si seguimos creciendo en personas que entran al edificio? ¿Hacemos mas pisos? ¿Hacemos mas grande la puerta?

Quizas una solución pueda ser comprar otro edificio con lo mismo de mi anterior edificio para repartir a las personas entre edificios, pero obviamente eso seria realmente caro en la vida real, pero, a nivel de desarrollo de software seria lo mas factible y con menor costo.

#### ¿Por qué?
Es más caro mejorar una sola computadora para que pueda ser usada por muchas personas al mismo tiempo (escalamiento vertical), a que se tengan diferentes computadoras para que se repartan entre todas las personas que necesiten usarla (escalamiento horizontal).

#### Entonces para poder escalar horizontalmente solo bastaria con tener mas computadoras y ya?
NO, existen diferentes procesos como instalación de software, mantenimiento de hardware, etc.

#### ¿Yo tendría que hacer esto para que mi base de datos en Cloud Firestore escale horizontalmente?
NO, tu solo debes usarla, el equipo de Firebase ya se encarga de eso.
