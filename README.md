# Azure CSP Labs

Repositorio de laboratorios prácticos del curso **CSP (Cloud Service Provider)** usando **Microsoft Azure**. Cada laboratorio incluye topologías de referencia, credenciales de prueba, comandos paso a paso y capturas de verificación.

---

## 📂 Contenido

| # | Laboratorio | Descripción breve |
|---|-------------|-------------------|
| 01 | Despliegue de VMs y SQL Server | Creación de VNET, subnets, VM Windows y VM Ubuntu con SQL Server, conexión RDP + SSH y consultas desde SSMS |

---

## 🏗️ Arquitectura General

Cada laboratorio sigue una arquitectura base en Azure:

- **Virtual Network (VNET)** con subnets segmentadas por rol
- **Network Security Groups (NSG)** para control de acceso por puerto
- **VM pública** (cliente) accesible por RDP o SSH desde el exterior
- **VM privada** (servidor) sin IP pública, accesible solo desde dentro de la VNET
```
LAPTOP ──RDP/SSH──► VM pública (subnet1) ──SSH/Query──► VM privada (subnet2)
```

---

## 🛠️ Herramientas

- **Microsoft Azure Portal** — aprovisionamiento de recursos
- **Remote Desktop (RDP)** — acceso a VMs Windows
- **SSH** — acceso a VMs Linux
- **SQL Server 2022** — motor de base de datos en Ubuntu
- **SQL Server Management Studio (SSMS)** — cliente de consultas

---

## 🚀 Cómo usar este repositorio

Cada laboratorio contiene un PDF con el diagrama de red, las credenciales de prueba y los comandos necesarios. Para replicarlo:

1. Iniciá sesión en [portal.azure.com](https://portal.azure.com)
2. Creá un grupo de recursos siguiendo el nombre indicado en el laboratorio
3. Seguí los pasos del PDF en orden
4. Verificá el resultado con los comandos o capturas al final de cada sección

> ⚠️ Las credenciales incluidas en los PDFs son de entorno de laboratorio. No uses estas contraseñas en entornos de producción.

---

**Autor:** Emerson Espinoza
**Curso:** CSP — Microsoft Azure