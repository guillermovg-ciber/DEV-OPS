---

typora-copy-images-to: ../../mis_assets/img/Hardening/

typora-root-url:  ../../

layout: post

---

|| Reglas OWASP



1. En primer lugar para poder instalar las reglas por defecto que nos trae owasp nos tendremos que descargar el repositorio de github.

   ```bash
   git clone https://github.com/SpiderLabs/owasp-modsecurity-crs.git
   ```

   

![1](/DEV-OPS/mis_assets/img/OWASP/1.png)



2. Como segundo punto, instalamos el modulo mod-security2 para poder usarlas.

```bash
sudo apt-get install libapache2-mod-security2 -y
```

![1](/DEV-OPS/mis_assets/img/OWASP/2.png)



3. Movemos el archivo por defecto a nuestra carpeta creada para las reglas.

![1](/DEV-OPS/mis_assets/img/OWASP/3.png)

4. Y despues movemos las reglas que vienen ya por defecto

![1](/DEV-OPS/mis_assets/img/OWASP/4.png)



5.Comprobamos que no haya ningun error y el archivo de  security2.conf este cargando las rutas de nuestras reglas comprobando que estan las lineas siguientes:

```bash
IncludeOptional /etc/modsecurity/*.conf
Include /etc/modsecurity/rules/*.conf
```

![1](/DEV-OPS/mis_assets/img/OWASP/5.png)



6.Añadimos tambien las reglas siguientes:

```bash
SecRuleEngine On
SecRule ARGS:testparam "@contains test" "id:1234,deny,status:403,msg:"mensaje"
```

![1](/DEV-OPS/mis_assets/img/OWASP/6.png)



7. al comprobar mediante el siguiente comando , vemos que las reglas estan en pleno funcionamiento ya queno nos da acceso al recurso en cuestion.

   ```bash
   curl localhost/index.html?testparam=test
   ```

   

![1](/DEV-OPS/mis_assets/img/OWASP/7.png)

