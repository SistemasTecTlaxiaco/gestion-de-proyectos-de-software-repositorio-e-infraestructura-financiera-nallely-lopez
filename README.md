#  Reporte de Investigación: Arquitectura y Viabilidad de Financiamiento Web3

> **StellarStream / OpenGrant Flow** — Infraestructura modular de streaming de fondos on-chain y gestión de grants en Soroban. Este reporte analiza los fundamentos técnicos y estratégicos necesarios para postular ante el Stellar Community Fund (SCF), integrando mecánicas de dispersión continua de fondos basadas en Drips Protocol.

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Soroban](https://img.shields.io/badge/Smart_Contracts-Soroban-7D00FF?logo=rust)](https://soroban.stellar.org/docs)
[![Drips Protocol](https://img.shields.io/badge/Financial_Infra-Drips_Network-00D395?logo=ethereum)](https://docs.drips.network/)
[![Stellar Community Fund](https://img.shields.io/badge/Grant_Track-SCF-08B5E5?logo=stellar)](https://communityfund.stellar.org/)

---

##  Tabla de Contenidos

1. [Resumen Ejecutivo y Alcance](#-resumen-ejecutivo-y-alcance)
2. [Requisitos y Mecánica de Postulación al SCF](#-requisitos-y-mecánica-de-postulación-al-stellar-community-fund-scf)
3. [Funcionamiento e Integración de Drips Protocol](#-funcionamiento-e-integración-de-drips-protocol)
4. [Estructura y Navegabilidad del Repositorio](#-estructura-y-navegabilidad-del-repositorio)
5. [Backlog por Fases Ligado a Tramos de Financiamiento](#-backlog-por-fases-ligado-a-tramos-de-financiamiento)
6. [Análisis de Brecha ("El Hueco Honesto")](#-análisis-de-brecha-el-hueco-honesto)
7. [Fuentes Primarias Oficiales](#-fuentes-primarias-oficiales-bibliografía-técnica)

---

##  Resumen Ejecutivo y Alcance

Este reporte analiza los fundamentos técnicos y estratégicos necesarios para postular un proyecto de bienes públicos / herramientas para desarrolladores ante el **Stellar Community Fund (SCF)**, integrando mecánicas de dispersión continua de fondos basadas en **Drips Protocol**. El objetivo es documentar los requisitos de postulación, la mecánica del streaming on-chain, la arquitectura del repositorio y el desglose de fases financieras para el archivo `FINANCIAMIENTO.md`.

---

##  Requisitos y Mecánica de Postulación al Stellar Community Fund (SCF)

- **Alineación con el Ecosistema:** El proyecto debe ejecutarse directamente sobre la red Stellar o implementar contratos inteligentes en **Soroban** (Rust / WASM).
- **Esquema de Desembolsos por Hitos (*Milestone-based Funding*):** SCF no otorga financiamiento total por adelantado; exige definir hitos medibles (*milestones*) con entregables técnicos verificables antes de liberar cada tramo de presupuesto.
- **Criterios Clave de Evaluación:**
  - **Utilidad y tracción:** Resolución de una fricción concreta en la infraestructura o adopción de Stellar.
  - **Viabilidad técnica y código abierto:** Preferencia estricta por licencias abiertas (MIT/Apache 2.0) y documentación clara de arquitectura.
  - **Capacidad del equipo:** Historial técnico comprobable en repositorios públicos.

---

##  Funcionamiento e Integración de Drips Protocol
### ¿Qué es el streaming de fondos on-chain?
 
A diferencia de transferencias atómicas puntuales, Drips permite transferencias deterministas continuas de saldo calculadas segundo a segundo ($Monto / Tiempo$). Los balances acumulados se actualizan matemáticamente en el estado del contrato sin necesidad de ejecutar transacciones intermedias por cada segundo transcurrido.
 
### Requisitos Técnicos para Recepción.
 
1. Dirección de wallet receptora válida en la red compatible.
2. Inicialización de una cuenta/registro en los contratos del protocolo (o vinculación mediante identificadores de repositorio como GitHub IDs en implementaciones compatibles).
3. Aceptación de los parámetros del stream (tasa de flujo por segundo y token ERC-20 / token Soroban equivalente).
### Límites Técnicos y Restricciones.
 
- **Dependencia de balance del emisor:** El flujo cesa inmediatamente si la cuenta emisora no mantiene reservas suficientes.
- **Coste de gas en recolección (*Squeeze/Collect*):** Aunque la acumulación es pasiva, la materialización de los fondos hacia el balance disponible de la wallet receptora requiere una transacción on-chain.
- **Compatibilidad de tokens:** Restringido a tokens estándar que cumplan con la interfaz requerida por el contrato de streaming
---

##  Estructura y Navegabilidad del Repositorio

Para garantizar la auditoría técnica independiente sin explicación oral, el repositorio debe organizarse bajo la siguiente convención:

```text
├── contracts/             # Smart contracts en Soroban (Rust)
│   ├── src/
│   └── tests/
├── frontend/              # DApp e interfaces de interacción (Next.js / TS)
├── docs/                  # Diagramas de arquitectura y flujos
├── FINANCIAMIENTO.md      # Documento técnico de postulación y backlog
├── README.md              # Guía de instalación, tests y comandos
└── LICENSE                # Licencia de código abierto (MIT / Apache 2.0)
```

**Política de Git:** Commits semánticos (*Conventional Commits*) distribuidos equitativamente entre los desarrolladores del equipo.

---

##  Backlog por Fases Ligado a Tramos de Financiamiento
 
| Fase | Entregable Técnico | Desembolso Asociado | Justificación |
|---|---|---|---|
| **Fase 1: Core Contracts** | Smart contracts de streaming en Soroban + suite de tests unitarios (>85% cobertura). | 35% del presupuesto | Horas de desarrollo de arquitectura e ingeniería de contratos en Rust. |
| **Fase 2: Testnet & SDK** | Despliegue en Stellar Testnet, SDK en TypeScript y conexión con wallets (Freighter). | 40% del presupuesto | Integración cliente-contrato y validación funcional en entorno de pruebas. |
| **Fase 3: Mainnet & Auditoría** | Despliegue en producción, documentación final y panel de control web operativo. | 25% del presupuesto | Verificación de seguridad, despliegue final y puesta en marcha pública. |
 
---
 
##  Análisis de Brecha ("El Hueco Honesto")
 
- **Requisito no cumplido actualmente:** El proyecto carece de un indexador descentralizado dedicado para consultar históricos de transacciones complejas en tiempo real; actualmente se depende únicamente de llamadas RPC directas al nodo de Stellar/Soroban.
- **Estrategia de resolución:** Implementación de un consumidor de eventos basado en Mercury o un subgrafo ligero específico para los eventos emitidos por el contrato.
- **Fecha estimada de cierre:** 3 semanas posteriores al despliegue en Testnet (previo al corte de entrega de la Fase 2).
---

##  Fuentes Primarias Oficiales (Bibliografía Técnica)

1. **Stellar Development Foundation.** (2026). *Stellar Community Fund (SCF) Handbook & Guidelines*. Official SCF Governance and Application Documentation. Disponible en: https://communityfund.stellar.org
2. **Drips Protocol.** (2025). *Drips Technical Overview & Smart Contract Specifications*. Drips Network Documentation. Disponible en: https://docs.drips.network
3. **Radicle / Drips Team.** (2025). *Drips Monorepo: Solidity & Core Streaming Protocol Architecture*. GitHub Repository. Disponible en: https://github.com/radicle-dev/drips-contracts
4. **Stellar Development Foundation.** (2026). *Soroban Smart Contracts Documentation: Environment Setup, Testing, and Deployment*. Stellar Developers Portal. Disponible en: https://soroban.stellar.org/docs

---
