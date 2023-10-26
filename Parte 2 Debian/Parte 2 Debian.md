Proyecto 1: Bastionado del arranque del sistema – Iván Sales Cisneros

**Parte 2. Arranque seguro en Linux**

Para proteger el arranque con contraseña, primeramente debemos editar el archivo de configuración “/etc/grub.d/40\_custom”. Y añadimos al usuario root y su correspondiente contraseña como en la imagen de abajo. Guardaremos el archivo y salimos.

![](Aspose.Words.b2be1191-ed95-4940-8e87-64f7c5813b6b.001.png)

Una vez que accedamos dicho archivo, será necesario regenerar fichero para guardar cambios.

![](Aspose.Words.b2be1191-ed95-4940-8e87-64f7c5813b6b.002.png)

También será recomendable cifrar la contraseña, para ellos ejecutamos el comando “sudo grub-mkpasswd-pbkdf2”.

![](Aspose.Words.b2be1191-ed95-4940-8e87-64f7c5813b6b.003.png)

Una vez dentro, añadimos la contraseña generada anteriormente en el archivo 40\_custom, poniendo password\_pbkdf2 en lugar de password. Guardaremos el archivo y salimos.

![](Aspose.Words.b2be1191-ed95-4940-8e87-64f7c5813b6b.004.png)

Ademas, podemos editar los permisos del archivo de configuración de GRUB 2 para que solo pueda ser editado por el root, para ellos ejecutamos el comando “sudo chmod 700 /etc/grub.d/40\_custom”.

![](Aspose.Words.b2be1191-ed95-4940-8e87-64f7c5813b6b.005.png)

Por último, para ocultar el menú de GRUB 2 al arrancar debemos abrir el fichero “etc/default/grub” ejecutando el comando “sudo nano etc/default/grub”. Una vez ahí, cambiamos GRUB\_TIMEOUT=5 por GRUB\_TIMEOUT=0. Guardaremos el archivo y salimos.

![](Aspose.Words.b2be1191-ed95-4940-8e87-64f7c5813b6b.006.png)

Para finalizar, ejecutaremos el comando “update-grub” para que se guarden los cambios correctamente.

![](Aspose.Words.b2be1191-ed95-4940-8e87-64f7c5813b6b.007.png)

Otras opciones de seguridad que se pueden configurar para conseguir un arranque lo mas seguro posible en Linux son:

1. **Verificación de Firmas de UEFI/BIOS:** En los sistemas modernos UEFI, se puede configurar un parámetro el cual solo permite que el sistema arranque con sistemas operativos con una firma digital válida, de lo contrario no podrá ejecutarse ese sistema operativo en el equipo. Esto garantiza la seguridad ya que solo permite que se ejecuten sistemas operativos confiables.
1. **Verificación de Integridad del Kernel:** Si se habilita la verificación de integridad del kernel durante el arranque, permite una seguridad adicional, ya que esto asegura que el kernel no haya sufrido en su integridad.
1. **Configurar Secure Boot:** En un sistema UEFI, podemos configurar también el Secure Boot, al habilitarlo permite garantizar que solo puedan ser instalados controladore de arranque con firmas digitales válidas.

Página 1 | 1
