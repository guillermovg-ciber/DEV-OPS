---

typora-copy-images-to: ../../mis_assets/img/Wordpress/

typora-root-url:  ../../

layout: post

---

> > En primer lugar crearemos el archivo docker-compose, donde le daremos todas las directrices a crear, en nuestro caso la base de datos y la app Wordpress, con sus contraseñas etc.

![](/DEV-OPS/mis_assets/img/Wordpress/1.png)



> > Cuando tengamos creado el archivo docker-compse.yml lo unico que tendremos que hacer es ejecutarlo,mediante comando docker-compose up -d

![](/../Wordpress/2.png)

[^]:                                                                                         la orden se tiene que ejecutar mediante sudo



> > Si todo ha ido correcto, al acceder al servicio de Wordpress (localhost:8000) nos aparecera la configuracion de el mismo, selecionamos español y damos a continuar

![](/DEV-OPS/mis_assets/img/Wordpress/3.png)



> > Añadimos la informacion que nos pide y damos a Instalar Wordpress.

![](/DEV-OPS/mis_assets/img/Wordpress/4.png)



> > Tras esos dos sencillos pasos, ya tendremos nuestra pagina web en Wordpress lista, lo unico que tendremos que hacer es acceder desde el menu wp-admin para adminsitrarla.

![](/DEV-OPS/mis_assets/img/Wordpress/5.png)



![](/DEV-OPS/mis_assets/img/Wordpress/6.png)



> Al cargar de nuevo nuestra pagina(localhost:8000) ya no nos aparecera la instalacion, sino en nuestro caso el sitio personalizado.

![](/DEV-OPS/mis_assets/img/Wordpress/7.png)