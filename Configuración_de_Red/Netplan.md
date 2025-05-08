# Práctica: Configuración de Red Interna en VirtualBox con Netplan y NetworkManager

## Objetivo

Configurar una red interna entre dos máquinas virtuales utilizando IPs estáticas. Se usará Netplan en la Máquina A y NetworkManager en la Máquina B para que la configuración sea persistente.

---

## Paso 1: Crear las máquinas virtuales

Clona una máquina base utilizando **clonación enlazada** para crear dos nuevas máquinas virtuales.

---

## Paso 2: Configurar los adaptadores de red

- Activa el **Adaptador 2** en ambas máquinas.
- Establece el modo de red como **Red Interna**.
- Asigna un nombre, por ejemplo: `Netplan`.

---

## Paso 3: Configurar las interfaces de red `enp0s8`

### En la Máquina A

```bash
sudo ip addr add 192.168.100.2/24 dev enp0s8
sudo ip link set enp0s8 up
