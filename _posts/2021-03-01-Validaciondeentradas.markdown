> 
>
> typora-copy-images-to: ../../mis_assets/img/Apache1/
>
> typora-root-url:  ../../
>
> layout: post



> Validacion de Entradas



Creamos una pagina Web mediante un servidor en docker, la cual nos permitira subir post, en principio con el codigo puesto ,estaria correcto pero nos podria colocar scripts por dentro que harian que los datos estuvieran comprometidos.

![](/DEV-OPS/mis_assets/img/Validacion/1.png)

La forma de solucionar este problema es sencilla : 

Si añadimos el siguiente texto conseguiremos que todo lo que entre dentro del  post para enviar no pueda ejecutarse.





```bash
	echo htmlspecialchars($_POST["textarea"]) ?? "";
```

![](/DEV-OPS/mis_assets/img/Validacion/2.png)



> > Robo de sesiones en autenticación

Al acceder a nuestra sesion , estamos logeandonos mediante una cookie la cual nos da acceso a la pagina o paginas que queramos acceder, esa cookie  es la encargada de permitir el acceso, si en nuestro caso alguien pudiera obtenerla, podria hacerse pasar por nosotros y acceder a nuestra sesion durante el tiempo que la tengamos abierta.



![](/DEV-OPS/mis_assets/img/Validacion/3.png)



En el caso de que nos la robaran mediante XSS, lo que consiguen es tener acceso como se ve a continuación a nuestra sesion ya, que la cookie lo que hace es logearnos como si fuera nuestro mismo usuario y contraseña.



![](/DEV-OPS/mis_assets/img/Validacion/4.png)



![](/DEV-OPS/mis_assets/img/Validacion/5.png)





> > Fijación de sesión o Session Fixation

En este caso, lo que trata es que el usuario al logearse en una pagina web(no fiable)  se esta logeando con una cookie fijada por el mismo atacante, el cual mediante esa cookie podra suplantarnos despues ya que no cambia.

![](/DEV-OPS/mis_assets/img/Validacion/6.png)



En el momento que nos hemos logeado, el mismo usuario marcando la cadena 

```bash
PHPSESSID=HOLA
```

obtiene acceso a nuestra sesion cuando el decida.

![](/DEV-OPS/mis_assets/img/Validacion/7.png)

> > Control de acceso por autorizacion

En este caso utilizaremos el principio de autenticacion por autorizacion, consiguiendo que solo el usuario autorizado sea la persona que pueda acceder a la pagina habilitada para su grupo.

​	Asignamos al usuario mario al grupo ADMIN

​	Asignamos al usuario juan al grupo USER

![](/DEV-OPS/mis_assets/img/Validacion/8.png)



Al logearnos mediante el usuario mario, comprobamos que el mismo tiene acceso a la pagina de administracion de su sitio, en cambio no tiene acceso a la pagina web del grupo USER, redirigiendole a la pagina de no-autorizado. 



![](/DEV-OPS/mis_assets/img/Validacion/9.png)





![](/DEV-OPS/mis_assets/img/Validacion/10.png)



> > CSRF 

En este ejemplo mostraremos como un usuario mediante un ataque por XSS consigue hacer que el otro ingrese una cantidad de dinero en la cuenta del otro



Mediante el ingreso del codigo 

```bash
<img src='http://dominiodeguro.local/transfer.php?quantity=1000&user=juan'>


```

en la pagina donde a accedido el usuario mario pensando que era la pagina de su banco legitimo, el atacante ha añadido  que desde la misma pagina se le envie una cantidad de dinero a su misma cuenta.

![](/DEV-OPS/mis_assets/img/Validacion/11.png)



> > Redireciones en pagina web

Por ultimo , cuando nosoros entramos en una pagina web que pueda no ser segura, tenemos la posibilidad que nos reenvien a una pagina que pueda parecer segura pero no lo es mediante un script:

```bash
<script>document.location = 'http://evil.local/clon-de-mi-banco.html'</script>
```

El mismo script, lo que hace es redirigirme a otra pagina con la apariencia de segura la cual al logearme, me puede robar los datos, o instalarme malware en el ordenador etc...



![](/DEV-OPS/mis_assets/img/Validacion/12.png)

