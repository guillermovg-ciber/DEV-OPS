---

typora-copy-images-to: ../../mis_assets/img/Hardening/

typora-root-url:  ../../

layout: post

---

> Hardening del Servidor

Como queremos cumplir los requisitos de minima exposición vamos a eliminar modulos que no vayamos a utilizar.

En nuestro caso el modulo que queremos quitar es el autoindex, ya que no queremos que de un indexado de todo lo que hay en el caso de no tener el archivo index.html



Para ellos tendremos que retirar el modulo mod_autoindex de nuestro archivo Dockerfile



![](/DEV-OPS/mis_assets/img/Hardening/1.1.png)



![](/DEV-OPS/mis_assets/img/Hardening/1.png)



Tras eliminar el mod_autoindex, tambien evitamos que el servidor al preguntarle, nos devuelva la version que tiene, modificando la configuracion del apache que estamos utilizando evitaremos este problema.



![](./DEV-OPS/mis_assets/img/Hardening/1.1.png)

![](/DEV-OPS/mis_assets/img/Hardening/2.png)

