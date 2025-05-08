# Práctica: Configuración de Red Interna en VirtualBox con Netplan y NetworkManager

## Objetivo

Configurar una red interna entre dos máquinas virtuales utilizando IPs estáticas. Se usará Netplan en la Máquina A y NetworkManager en la Máquina B para que la configuración sea persistente.

---

## Paso 1: Crear las máquinas virtuales

Clona una máquina base utilizando **clonación enlazada** para crear dos nuevas máquinas virtuales.

![Primera](imagenes/maquinaA.png)
![Segunda](imagenes/clonacionenlazada.png)
![Tercera](imagenes/maquinaB.png)

---


## Paso 2: Configurar los adaptadores de red

- Activa el **Adaptador 2** en ambas máquinas.
- Establece el modo de red como **Red Interna**.
- Asigna un nombre, por ejemplo: `Netplan`.

![Cuarta](imagenes/adaptador2A.png)

![Quinta](imagenes/adaptador2B.png)

---

## Paso 3: Configurar las interfaces de red `enp0s8`

### En la Máquina A

![Sexta](imagenes/sshA.png)

```bash
sudo ip addr add 192.168.100.2/24 dev enp0s8
sudo ip link set enp0s8 up
```
![Séptima](imagenes/IPsA.png)

### En la Máquina B

![Octava](imagenes/sshB.png)

```bash
sudo ip addr add 192.168.100.3/24 dev enp0s8
sudo ip link set enp0s8 up
```
![Octava](imagenes/IPsB.png)

---

## Paso 4: Comprobar conectividad

### Desde Máquina A hacia Máquina B

```bash
ping 192.168.100.3
```
![Novena](imagenes/pingA.png)


### Desde Máquina B hacia Máquina A

```bash
ping 192.168.100.2
```
![Décima](imagenes/pingB.png)

---

## Paso 5: Hacer la configuración persistente

### Máquina A: Usando Netplan

1. Edita el archivo de configuración:

```bash
sudo nano /etc/netplan/01-netcfg.yaml
```
![Once](imagenes/NetplanA.png)

2. Añade el siguiente contenido:

```yaml
network:
  version: 2
  renderer: networkd
  ethernets:
    enp0s8:
      dhcp4: no
      addresses: [192.168.100.2/24]
```
![Doce](imagenes/infoNetplan.png)

3. Ajusta los permisos:

```bash
sudo chmod 600 /etc/netplan/01-netcfg.yaml
```
  Y aplicamos los cambios
```bash
sudo sudo netplan apply
```

![Trece](imagenes/confNetplan.png)

---

### Máquina B: Usando NetworkManager

1. Crea la conexión:

```bash
sudo nmcli con add type ethernet ifname enp0s8 con-name intnet-b ip4 192.168.100.3/24
```

![Catorce](imagenes/B1.png)

2. Activa la conexión:

```bash
sudo nmcli con up intnet-b
```
![Quince](imagenes/B2.png)

---

## Paso 6: Verificación final

Reinicia ambas máquinas y verifica que:

- La IP se mantiene tras el reinicio.
- La conectividad entre ambas máquinas sigue funcionando mediante `ping`.

![Dieciseis](imagenes/pingB.png)


---
