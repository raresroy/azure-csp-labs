# Azure CSP Labs

Repositorio de laboratorios prácticos del curso **CSP (Cloud Service Provider)** usando **Microsoft Azure**. Cada laboratorio incluye topologías de referencia, credenciales de prueba, comandos paso a paso y capturas de verificación.

---

## 📂 Contenido

| # | Laboratorio | Descripción breve |
|---|-------------|-------------------|
| 01 | Despliegue de VMs y SQL Server | Creación de VNET, subnets, VM Windows y VM Ubuntu con SQL Server, conexión RDP + SSH y consultas desde SSMS |
| 02 | VNet Peering, CRUD en SQL Server y Azure SQL (PaaS) | Emparejamiento de VNets, operaciones CRUD en AdventureWorks desde SSMS y conexión a Azure SQL mediante Private Endpoint |
| 03 | WAF, Microsoft Entra ID y App Services | Protección de una aplicación web con Application Gateway (WAF), autenticación de usuarios con Entra ID y despliegue en Azure App Services |

---

## 🏗️ Arquitectura General

Cada laboratorio sigue una arquitectura base en Azure:

- **Virtual Network (VNET)** con subnets segmentadas por rol
- **Network Security Groups (NSG)** para control de acceso por puerto
- **VM pública** (jump server) accesible por RDP desde el exterior
- **VMs privadas** sin IP pública, accesibles solo desde dentro de la VNET
- **VNet Peering** para comunicación entre redes virtuales distintas
- **Private Endpoint** para acceso seguro a servicios PaaS como Azure SQL
- **Application Gateway (WAF)** para protección de aplicaciones web
- **Microsoft Entra ID** para autenticación de identidades (SaaS)
```
LAPTOP ──RDP──► PC1 jump (snet-jump)
                    ├──RDP──► PC2 cliente SSMS (snet-clients) ──Query──► PC3 SQL Server (snet-data)
                    └──RDP──► PC2 cliente SSMS (snet-clients) ──Query──► Azure SQL PaaS (Private Endpoint)

Browser (Cucho) ──HTTPS/TLS──► Application Gateway (WAF) ──HTTPS──► App Service ──OAuth 2.0──► Entra ID
```

---

## 🛠️ Herramientas

- **Microsoft Azure Portal** — aprovisionamiento de recursos
- **Remote Desktop (RDP)** — acceso a VMs Windows
- **SSH** — acceso a VMs Linux
- **SQL Server 2022** — motor de base de datos en Ubuntu
- **SQL Server Management Studio (SSMS)** — cliente de consultas
- **Azure SQL** — servicio de base de datos administrado (PaaS)
- **VNet Peering** — interconexión de redes virtuales
- **Private Endpoint + DNS privado** — acceso seguro a servicios PaaS
- **Azure App Services** — hospedaje de aplicaciones web (PaaS)
- **Azure Application Gateway** — balanceador con WAF integrado
- **Microsoft Entra ID** — directorio de identidades y autenticación SaaS

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