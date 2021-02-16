> typora-copy-images-to: ../../mis_assets/img/Apache1/
>
> typora-root-url:  ../../
>
> layout: post



> # **Google Cloud**

> > En Primer lugar, nos crearemos un proyecto en Google Cloud, el cual utilizaremos mas adelante para cargar la pagina de Nodejs
> >
> > ![](../mis_assets/img/node/1.png)



> Para continuar, tendremos que añadir la App Engine, la cual nos  dara para elegir el lenguaje a utilizar, en nuestro caso utilizaremos python ya que es desde donde lanzaremos todo.

![](../mis_assets/img/node/2.png)



> A partir de aqui nos dan un SDK de google cloud, el cual tendremos que desplegarlo en el equipo, (./install.sh), al desplegarlo, nos permitira utilizar los comandos de google cloud en el equipo que veremos a continuacion

![](../mis_assets/img/node/3.png)

> Tras acabar el apartado en Google Cloud, nos pasaremos ya al equipo en si para empezar nuestro proyecto de node, para empezar lo primero que tendremos que hacer es crearnos una carpeta con el nombre del proyecto.

![](../mis_assets/img/node/4.png)



> > Como paso intermedio, para poder utilizar los comandos de nodejs tendremos que instalar nodejs y npm ( sudo apt get install nodejs, sudo apt get install npm)



> Tras instalar node y npm, inicializamos la carpeta a usar mediante el comando npm init.

![](../mis_assets/img/node/5.png)



> Instalamos el paquete express

![](../mis_assets/img/node/6.png)

> Y comprobamos en el archivo package.json que en el apartado dependencias, nos ha añadido el apartado express con su version instalada.

![](../mis_assets/img/node/7.png)



> A partir de aqui creamos un archivo llamado server.js al cual le daremos unos valores predefinidos, (puerto de escucha,constantes path, etc...)

![](../mis_assets/img/node/8.png)



> Cuando tengamos el archivo server.js acabado, podemos comprobar que al lanzarlo (npm start) al acceder al puerto 8080 de localhost, se ha cargado el archivo server.js y creado nuestra pagina web.

![](../mis_assets/img/node/9.png)



> A partir de aqui utilizaremos los comandos de google cloud para subir la pagina web a nuestro Cloud y poder lanzarlo desde alli, utilizaremos el comando (gcloud app deploy) para cargar lo que este en local de la carpeta, y subirlo a la nube.

![](../mis_assets/img/node/10.png)



> Tras subirlo a la nube lo unico que tenemos que hacer es cargarlo en el navegador y comprobar que funcione, mediante el comando (gcloud app browse)

![](../mis_assets/img/node/11.png)

> Tras ver que todo este correcto, si queremos podemos modificar la informacion del server.js y añadir lo que nosotros queramos, como por ejemplo modificar el texto de muestra de Hello from app engine, a Hello from Ciberseguridad.

![](../mis_assets/img/node/12.png)



> A partir de aqui, añadiremos un formulario html para que los usuarios puedan utilizar un submit, lo unico que tenemos que hacer es añadir una carpeta(views) en la cual creamos  un form.html con el formulario que vamos a utilizar.



![](../mis_assets/img/node/13.png)



> Tras crear y guardar el formulario, nos movemos otra vez al server.js y añadimos los valores:
>
> (bodyparser, app.get usbmit, app.use bodyparser y app.post)

![](../mis_assets/img/node/14.png)

> Si todo ha ido correcto, lo unico que nos quedara por hacer es el comando gcloud app deploy ( para resubir los archivos añadidos y modificados a cloud) y otra vez el gcloud app browse para mostrarlo.
>
> Al hacerlo podemos comprobar que al añadir el /submit a nuestra pagina, nos carga el formulario de contacto que hemos añadido

![](../mis_assets/img/node/15.png)