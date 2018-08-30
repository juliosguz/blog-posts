Muchas personas saben crear **páginas web** pero son muy pocas las que saben estructurar correctamente su proyecto para que sea **mantenible**.
Aquí te dejo algunos consejos, que me ayudaron a desarrollarlos de manera eficiente.

### A tener en cuenta

Este artículo formará parte de una serie de **artículos básicos** relacionados a **cómo organizar tu proyecto para la web** y si eres alguien que tiene mucha experiencia, te pido puedas compartir tus experiencias o enviarme alguna sugerencia sobre el artículo por Twitter: @juliosguz

### 1.- Git y GitHub serán siempre tus mejores amigos
Cada vez que inicies un proyecto, **DEBES (Y NO ES OPCIONAL)**, crear un repositorio usando **Git** (software de control de versiones), para luego subir este proyecto a una plataforma en la **nube**, esta plataforma se llama **GitHub**.El uso de esta plataforma es **gratuita para proyecto publicos** pero también puedes tener proyectos privados pagando 7usd mensuales.Pero, si buscas una opción **privada y gratuita** puedes usar Bitbucket.Usando un repositorio(seria mas o menos la carpeta de tu proyecto con una carpeta oculta donde se guarda el registro de todo lo que hagas) y un lugar donde guardarlo, para que no lo tengas en tu PC o portátil, podrás tener acceso a:Un historial de los cambios que hayas hecho durante todo tiempo de desarrollo. A tu proyecto desde donde sea que estés pero que tengas conexión a internet.

> Con esto nunca pasarás por los típicos
> - Se murio mi maquina y no guarde mi TESIS 
> - Mi oficina se incendió y estaba ahí mi portatil, no se que hacer con mi vida.
> - No tengo espacio en el disco duro para guardar mis proyectos antiguos
> - ¿Qué hice la semana en este archivo?

Suena bonito, pero si en este punto estas como: **”WTF @#$$!% que diablos es eso? “yo solo queria saber como nombrar mis archivos”**, calmado, te dejo algunos links al final del post para que los revises o puedes enviarme tu pregunta a **@juliosguz** 

### 2.- Las carpetas y archivos si “solo quieres crear el HTML y CSS”

Teniendo la carpeta de nuestro proyecto, dentro deberás crear lo siguiente:

![Estructura basica](https://firebasestorage.googleapis.com/v0/b/juliosguz-ee474.appspot.com/o/site%2Fposts%2F2017%2F01%2Festructura-basica.png?alt=media&token=3a2a0a95-24cf-4db6-b2da-278a8ed3a8e3 "Estructura basica")

Nada del otro mundo, ¿verdad?
Pues sí, solo si quieres seguir trabajando de una forma **“tradicional”**

> mmm y…. ¿Cual seria la forma no tradicional?

Para la web, existen dos opciones más para crear archivos HTML y CSS, esos son Jade y Stylus. Sin ser tan técnicos, ambos te permiten utilizar una especie de lenguaje de programación para escribir código que se transformara en HTML y CSS.

> Pero aquí no hablariamos solo de ¿cómo organizar tu proyecto para la web?

Sí y tomando en cuenta esto, mostraré lo que podrías llegar a hacer con Stylus específicamente.

### 3.- La carpeta CSS y que va dentro

Tomando como ejemplo este blog, la cantidad de líneas de código en estilos, es bastante pequeña con un máximo de 300 líneas de código. Imaginen que fueran más de mil o dos mil.

![Buscar archivo](https://firebasestorage.googleapis.com/v0/b/juliosguz-ee474.appspot.com/o/site%2Fposts%2F2017%2F01%2Fbuscar-archivos.png?alt=media&token=abb36bf1-815f-4263-a0b7-59c66e56f1da "Buscar Archivo")

> Quizás usando Ctrl + F para buscar dentro de un archivo de texto les podría salvar.

Ahora teniendo en cuenta que deben editar algo nuevo para un área en específica, que está dentro de la línea “que aún no se acuerdan” de un archivo con más de 3000 líneas de código, el Ctrl + F no te ayudará mucho, pero si tuvieras los estilos de cada página, sección o componente de tu sitio en archivos distintos, seria mucho mas sencillo se ubicarlo y editarlo.\n\nEs aquí donde entra Stylus.\n\nCon Stylus pueden crear un **archivo principal(main.styl)** e importar diferentes archivos de las paginas, secciones o componentes de tu sitio.

![Estructura de estilos](https://firebasestorage.googleapis.com/v0/b/juliosguz-ee474.appspot.com/o/site%2Fposts%2F2017%2F01%2Festructura-de-estilos.png?alt=media&token=b7aa73f5-07a0-4706-9206-b481b01fa8aa "Estructura de estilos")

Ademas, puedes separar por carpetas los diferentes estilos para paginas o secciones, utilizando nombres bastante descriptivos. Por ejemplo, si tienes una pagina de una categoria especial que se llame “street-style” y tienes secciones internas, puedes crear otros archivos que hagan referencia a esas secciones, asi vas separando de lo general a lo especifico.

> Algo complejo, ¿verdad?

Sí, pero debes tomar en cuenta lo siguiente:

- Tienes un proyecto más ordenado
- La forma en la que puedes ubicar el codigo sera mucho mas sencilla de hacerlo
- Y un plus de Stylus, es que escribiras mas rapido y tambien de una forma ordenada, tu codigo css.

## Lo rescatable

Si bien usar Git y Stylus podria ser para algunos el aprender algo nuevo y que “no es comun de usar”, te servira no solamente a tener una buena organización en tu proyecto, sino que podras iniciar a **“trabajar profesionalmente para la web”**

## Enlaces

- [Tutoriales y videos sobre Git](https://git-scm.com/documentation)
- [Ayuda con GitHub](https://help.github.com/)
- [Crea HTML con Jade](http://jadelang.net/)
- [Crea CSS con Stylus](http://stylus-lang.com/)

Si tienes algo mas para agregar a esto, dejalo en los comentarios o sino me puedes enviar un mensaje a **@juliosguz**