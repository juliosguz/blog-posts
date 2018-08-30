# ¿Qué es Cloud Firestore?

Es una base de datos NoSQL que se encuentra en la nube, la cual mantiene sincronizados los datos en las aplicaciones, ya sea moviles o web las cuales accedan a ella, esto me permite tener los datos en tiempo real. Ademas esta hecha para poder escalar horizontalmente, lo cual hace que el costo de uso sea mucho bajo en comparación de otros servicios.

> Una base de datos NoSQL
> - No cuenta con un lenguaje para realizar consultas, a diferencias de las base de datos relacionales con soporte SQL (Structured Query Language).
> - No utiliza tablas para almacenar los datos y al existir diferentes tipos de base de datos NoSQL, puedes encontrar los que son del tipo llave/valor, base de datos orientado a documentos, etc.
> - No usa un esquema o receta para definir la estructura de donde guardaras tus datos, con esto, cuentas con flexibilidad para guardar los datos.
> - Al tener flexibilidad, no existe el concepto de normalización y es por eso que podrias encontrar datos duplicados.
> - En el caso de de Cloud Firestore, al usar colecciones, no existe una relación fuerte entre colecciones como existiria entre tablas de una base de datos SQL. (Este punto lo tocare en publicaciones posteriores)

## 1.- ¿Qué significa tener una base de datos en la nube?

Tu base de datos se encuentra en internet y por eso necesitaras conexión a internet para poder acceder a ella. Aunque Cloud Firestore cuenta con la opción offline, la cual me permite poder realizar acciones a la base de datos si mi dispositivo no tiene internet, no existe por ahora una opción de pruebas hacia una copia de tu base de datos en tu computadora. Actualmente, se sabe que el equipo de Firebase esta trabajando en un emulador, al igual que existe para su base de datos en tiempo real.

## 2.- ¿Qué significa tener los datos en tiempo real?
Cloud Firestore mantiene los datos sincronizados entre todos los dispositivos desde los cuales se conecten, por ejemplo, si existen 5 smartphones y 1 pc conectadas a tu aplicación, y alguien desde alguno de los smartphones actualiza el titulo de una publicación, se actualizaran los cambios en los demas lugares conectados, sin necesidad de actualizar la pagina donde estes o cerrar y abrir la aplicación. Podrias usarlo para un chat, feed de noticias, marcadores para juegos en linea, etc.

## 3.- ¿Qué es escalamiento horizontal?
Si hablamos de escalamiento, debemos tener en mente que **Tu aplicación sera utilizada por muchas personas y esto se traducira en mucho uso de harware**.
Para ejemplificarlo, ten en mente esto:

> Tenemos un edificio con capacidad para 100 personas, el cual tiene una puerta, por la cual cada día entra una persona por minuto.

El **edificio** y la **puerta** son el hardware, ahora vamos a lo siguiente:

> Nuestro edificio es tan popular que ahora mas de una persona entra por minuto, algunas veces llega a 50 personas queriendo entrar al mismo tiempo por la misma puerta y ademas de eso, la capacidad de 100 personas del edificio, sobrepasa facilmente ¿Te imaginas eso?

Una solución a eso seria el **agrandar la puerta** y **ponerle mas pisos al edificio**, lo cual podria ser viable, pero ¿Qué pasa si seguimos creciendo en personas que entran al edificio? ¿Hacemos mas pisos? ¿Hacemos mas grande la puerta?

Quizas una solución pueda ser comprar otro edificio con lo mismo de mi anterior edificio para repartir a las personas entre edificios, pero obviamente eso seria realmente caro en la vida real, pero, a nivel de desarrollo de software seria lo mas factible y con menor costo.

### ¿Por qué?
Es mas caro mejorar una sola computadora para que pueda ser usada por muchas personas al mismo tiempo (escalamiento vertical), a que se tengan diferentes computadoras para que se repartan entre todas las personas que necesiten usarla (escalamiento horizontal).

### Entonces para poder escalar horizontalmente solo bastaria con tener mas computadoras y ya?
NO, existen diferentes procesos como instalación de software, mantenimiento de hardware, etc.

### ¿Yo tendria que hacer esto para que mi base de datos en Cloud Firestore escale horizontalmente?
NO, tu solo debes usarla, el equipo de Firebase ya se encarga de eso.

---

Si quieres saber un poco mas sobre Cloud Firestore, te recomiendo seguir la serie publicaciones que iran haciendo.







