# GrapeTrace-zkSYS: Trazabilidad Blockchain para la Uva de Exportación (Ica-Perú)

## 1. Descripción del Proyecto
**GrapeTrace-zkSYS** es una solución de software basada en tecnología **Web3** diseñada para garantizar la transparencia, calidad y origen de la uva producida en la región de Ica, Perú, con destino a mercados internacionales. 

El proyecto utiliza la red **zkSYS (Rollux PoB Devnet)** de Syscoin para crear un registro inmutable y auditable de cada etapa de la cadena de suministro, desde la cosecha hasta el consumidor final. El sistema permite a los exportadores peruanos cumplir con los estándares internacionales más exigentes, proporcionando un **"pasaporte digital"** que certifica la fitosanidad, la cadena de frío y el cumplimiento normativo.

---

## 2. Arquitectura de Trazabilidad
El sistema registra datos críticos en cada eslabón de la cadena, asegurando que la información sea veraz y no manipulable:

* **Origen y Cosecha:** Registro de geolocalización de la parcela, variedad de uva y fecha de recolección.
* **Procesamiento (Packing):** Documentación del pesaje, selección y estándares de calidad.
* **Certificaciones:** Almacenamiento de hashes de certificados fitosanitarios (**SENASA**) y normativas (**GlobalG.A.P.**).
* **Logística y Frío:** Monitoreo de marcas de tiempo (*timestamps*) y estados de temperatura en el transporte hacia el puerto.

---

## 3. Implementación Técnica

### Smart Contracts (Capa de Confianza)
El proyecto utiliza contratos inteligentes desarrollados en **Solidity** desplegados en la red zkSYS. Estos contratos gestionan:
* **Control de Acceso (Role-Based Access Control):** Solo billeteras autorizadas (productores, inspectores, transportistas) pueden emitir transacciones para registrar datos.
* **Inmutabilidad:** Una vez firmada la transacción, el historial del lote de uva no puede ser alterado.

### Modelo Híbrido de Datos
Para optimizar costos y rendimiento, el sistema emplea una arquitectura mixta:
* **On-Chain (zkSYS):** Almacenamiento de metadatos críticos, IDs de lotes y firmas digitales.
* **Off-Chain (Base de Datos / IPFS):** Almacenamiento de imágenes de alta resolución, descripciones extensas y documentos PDF, vinculados a la blockchain mediante identificadores únicos (hashes).

### Interfaz y Experiencia de Usuario (UX)
* **Registradores:** Operan mediante una DApp desarrollada en **Vue.js + Tailwind CSS**, integrada con **PaliWallet** para la firma de cada evento de la cadena.
* **Usuarios Finales:** Consultan la información mediante el escaneo de un **Código QR** impreso en el empaque (Clamshell) o palé. No requieren de una billetera digital para acceder a la visualización de los datos.

---

## 4. Flujo de Roles
El sistema está diseñado bajo un esquema de permisos estricto para proteger la integridad de la red:

| Rol | Acción | Herramienta |
| :--- | :--- | :--- |
| **Administrador** | Gestión de permisos y Whitelist (Lista blanca) | PaliWallet / Multisig |
| **Productor / Packing** | Registro de eventos de producción y empaque | DApp + PaliWallet |
| **Inspector** | Validación de certificados y calidad fitosanitaria | DApp + PaliWallet |
| **Consumidor** | Consulta de trazabilidad e historia del producto | Navegador Web (Escaneo QR) |

---

## 5. Beneficios Estratégicos
* **Garantía de Calidad:** Facilita la auditoría de mercados internacionales (EE.UU., UE, Asia).
* **Eficiencia en zkSYS:** Aprovecha los bajos costos de gas y la alta escalabilidad de la Capa 2 de Syscoin.
* **Transparencia:** Reduce el riesgo de fraude alimentario y fortalece la reputación de la agroexportación peruana en el mundo.
