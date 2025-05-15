# 🛠️ Práctica: Recuperación de sistema Debian usando CHROOT desde Kali Live

En esta práctica instalaremos Debian e utilizaremos un Live de Kali Linux para acceder al sistema mediante `chroot`, con el fin de recuperar o reparar el sistema operativo instalado.

---

## 🧱 Instalación de Debian

1. **Seleccionamos el idioma del sistema.**

   ![Selección de idioma](imagenes/instalacion3.png)

2. **Introducimos la contraseña de superusuario.**

   ![Selección de idioma](imagenes/instalacion4.png)

3. **Creamos el usuario del sistema.**

   ![Selección de idioma](imagenes/instalacion5.png)
   ![Selección de idioma](imagenes/instalacion6.png)
   

5. **Configuramos los discos y particiones.**

   ![Selección de idioma](imagenes/instalacion7.png)
   ![Selección de idioma](imagenes/instalacion8.png)
   ![Selección de idioma](imagenes/instalacion9.png)
   ![Selección de idioma](imagenes/instalacion10.png)
   ![Selección de idioma](imagenes/instalacion11.png)
   ![Selección de idioma](imagenes/instalacion12.png)
   ![Selección de idioma](imagenes/instalacion13.png)
   ![Selección de idioma](imagenes/instalacion14.png)
   ![Selección de idioma](imagenes/instalacion15.png)
   ![Selección de idioma](imagenes/instalacion16.png)
   ![Selección de idioma](imagenes/instalacion17.png)
   ![Selección de idioma](imagenes/instalacion18.png)
   ![Selección de idioma](imagenes/instalacion19.png)

---

## 💿 Arranque de Kali Live

1. **Insertamos el Live USB o ISO de Kali Linux.**

   ![Live de Kali](imagenes/kali1.png)

2. **Iniciamos desde el entorno Live de Kali.**

---

## ⚙️ Preparación del entorno en Kali Live

1. **Abrimos una terminal y configuramos el teclado en español:**

   ```bash
   setxkbmap es

2. **Iniciamos sesión como root con "sudo su" y confirmamos en /dev que estea el sda1:**

   ![Live de Kali](imagenes/kali2.png)
   ![Live de Kali](imagenes/kali3.png)

3. **Ahora usamos el "chroot" para modificar el live de Kali para poder entrar en Debian:**

   ![Live de Kali](imagenes/kali4.png)

4. **Montamos el disco "/dev/sda1" en "/mnt/recuperar":**

   ![Live de Kali](imagenes/kali5.png)
   
   ![Live de Kali](imagenes/kali6.png)
   
   ![Live de Kali](imagenes/kali7.png)

---

## ✅ Verificación

**Creamos un archivo de prueba dentro del entorno Debian montado y luego entramos en el Debian y confirmamos que se creara:**

![Live de Kali](imagenes/kali8.png)

![Live de Kali](imagenes/kali9.png)
