# 🛠️ Práctica: Recuperación de sistema Debian usando CHROOT desde Kali Live

En esta práctica instalaremos Debian e utilizaremos un Live de Kali Linux para acceder al sistema mediante `chroot`, con el fin de recuperar o reparar el sistema operativo instalado.

---

## 🧱 Instalación de Debian

1. **Seleccionamos el idioma del sistema.**

   ![Selección de idioma](.jpg)

2. **Introducimos la contraseña de superusuario.**

   ![Contraseña root](ruta/a/la/imagen2.jpg)

3. **Creamos el usuario del sistema.**

   ![Usuario](ruta/a/la/imagen3.jpg)

4. **Configuramos los discos y particiones.**

   ![Particionado](ruta/a/la/imagen4.jpg)

---

## 💿 Arranque de Kali Live

1. **Insertamos el Live USB o ISO de Kali Linux.**

   ![Live de Kali](ruta/a/la/imagen5.jpg)

2. **Iniciamos desde el entorno Live de Kali.**

   ![Inicio Kali](ruta/a/la/imagen6.jpg)

---

## ⚙️ Preparación del entorno en Kali Live

1. **Abrimos una terminal y configuramos el teclado en español:**

   ```bash
   setxkbmap es
