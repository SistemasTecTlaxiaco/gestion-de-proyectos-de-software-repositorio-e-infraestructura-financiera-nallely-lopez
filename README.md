# 📊 Gestión de Proyectos de Software: Repositorio e Infraestructura Financiera

> Repositorio académico y técnico estructurado para el seguimiento de entregables mediante GitHub Milestones, la integración de mecanismos de financiamiento continuo con Drips Protocol y la postulación a fondos descentralizados en el Stellar Community Fund (SCF).

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![GitHub Milestones](https://img.shields.io/badge/Milestones-Estructurados-blueviolet?logo=github)](https://github.com/SistemasTecTlaxiaco/gestion-de-proyectos-de-software-repositorio-e-infraestructura-financiera-nallely-lopez/milestones)
[![Drips Protocol](https://img.shields.io/badge/Financial_Infra-Drips_Network-00D395?logo=ethereum)](https://docs.drips.network/)
[![Stellar Community Fund](https://img.shields.io/badge/Grant_Track-SCF-08B5E5?logo=stellar)](https://communityfund.stellar.org/)

---

## 📋 Tabla de Contenidos

1. [Estructura y Organización del Repositorio](#-estructura-y-organización-del-repositorio)
2. [Backlog por Fases Ligado a Financiamiento](#-backlog-por-fases-ligado-a-financiamiento)
3. [Requisitos de Stellar Community Fund (SCF)](#-requisitos-de-stellar-community-fund-scf)
4. [Mecanismo Técnico de Drips Protocol](#-mecanismo-técnico-de-drips-protocol)
5. [Análisis de Brecha ("El Hueco Honesto")](#-análisis-de-brecha-el-hueco-honesto)
6. [Flujo de Trabajo y Guía de Contribución](#-flujo-de-trabajo-y-guía-de-contribución)
7. [Bibliografía y Fuentes Primarias](#-bibliografía-y-fuentes-primarias)
8. [Autora y Licencia](#-autora-y-licencia)

---

## 📂 Estructura y Organización del Repositorio

El repositorio está diseñado de manera modular y autosuficiente:

```text
├── .github/
│   ├── ISSUE_TEMPLATE/       # Plantillas estandarizadas para issues y tareas
│   └── workflows/            # Automatización de validaciones e integración continua
├── docs/
│   ├── FINANCIAMIENTO.md     # Desglose de presupuestos y mecanismos on-chain
│   ├── ARQUITECTURA.md       # Diagramas técnicos y flujo de datos
│   └── METRICAS.md           # KPIs y seguimiento de hitos
├── src/                      # Código fuente y componentes de integración
├── scripts/                  # Scripts de despliegue y herramientas auxiliares
├── .gitignore                # Reglas de exclusión de git
├── LICENSE                   # Licencia de código abierto MIT
└── README.md                 # Documentación principal del repositorio
```

---

## ⏱️ Backlog por Fases Ligado a Financiamiento

La planificación del proyecto vincula cada hito de desarrollo (GitHub Milestones) con un esquema de financiamiento on-chain específico:

| Fase / Milestone | Alcance y Entregables Técnicos | Mecanismo de Financiamiento | Justificación Financiera |
|---|---|---|---|
| **Fase 1: Configuración Base y Arquitectura** | Repositorio estructurado, definición de pipelines, documentación base y vinculación de identidades GitHub/Web3. | Recursos Propios (Bootstrapping) | Costos operativos iniciales mínimos que establecen la base técnica para auditorías previas. |
| **Fase 2: Prototipado y Gestión de Issues** | Integración del backlog, automatización de trazabilidad y configuración del streaming en testnet. | Drips Protocol (Dependency Stream) | Cobertura recurrente de licencias de desarrollo e incentivo continuo a contribuidores activos. |
| **Fase 3: Implementación y Testing** | Contratos/módulos de integración completados, validación de transacciones y suite de pruebas unitarias. | Stellar Community Fund (SCF - Tranche Inicial) | Desbloqueo de capital tras validar el hito verificable del prototipo funcional frente al comité evaluador. |
| **Fase 4: Despliegue, Auditoría y Cierre** | Despliegue en red principal, auditoría de código, métricas finales de impacto y documentación de cierre. | Stellar Community Fund (SCF - Tranche Final) | Liquidación final condicionada a la entrega del producto documentado y en producción. |

---

## 🏛️ Requisitos de Stellar Community Fund (SCF)

**Fecha de consulta oficial:** Agosto 2026
**Fuente oficial:** [Stellar Community Fund Handbook](https://communityfund.stellar.org/)

### Criterios y Requisitos Vigentes de Postulación

- **Alineación con el Ecosistema:** Construir directamente sobre la red Stellar o Soroban (smart contracts), aportando utilidad medible a la comunidad o a la infraestructura abierta.
- **Entregables Verificables por Hitos (Milestone-Based Funding):** Los fondos no se otorgan en una sola exhibición inicial; se liberan en tramos (tranches) tras la verificación de hitos públicos en GitHub.
- **Código Abierto y Documentación Pública:** El proyecto debe contar con repositorios accesibles, licencia permisiva y documentación clara sobre arquitectura y uso.
- **Equipo y Capacidad de Ejecución:** Demostración de experiencia técnica suficiente para completar la hoja de ruta descrita en los plazos estipulados.

---

## 💧 Mecanismo Técnico de Drips Protocol

**Fuente oficial:** [Drips Network Documentation](https://docs.drips.network/)

### ¿Qué es el streaming de fondos on-chain?

El streaming de fondos es un mecanismo descentralizado donde los tokens ERC-20 (o equivalentes) se transfieren de forma continua segundo a segundo a lo largo de un período determinado, en lugar de transferirse en transacciones discretas tradicionales. Esto permite un flujo constante de capital programable entre emisores y receptores.

### Requisitos para recibir fondos

1. **Identidad Vinculada:** Una dirección de billetera compatible (EVM/Ethereum) vinculada mediante verificación criptográfica a una cuenta u organización de GitHub.
2. **Registro del Proyecto:** Generación del registro en el contrato inteligente del protocolo mediante la interfaz o SDK de Drips.
3. **Configuración de Divisiones (Splits):** Definición de la matriz de porcentajes para redireccionar automáticamente una fracción de los fondos a contribuidores o dependencias de software upstream.

### Límites y Consideraciones del Protocolo

- **Costo de Gas en Liquidación:** Aunque el cálculo del flujo es continuo mediante fórmulas matemáticas en el contrato, el retiro efectivo (squeezing/withdrawing) requiere ejecutar una transacción on-chain que consume gas.
- **Volatilidad de Activos:** El valor real del flujo depende de la estabilidad del token utilizado; se recomiendan activos vinculados como USDC.
- **Dependencia de Red:** Las interrupciones o congestiones en la red base pueden elevar temporalmente los costos de cobro o actualización de la configuración de divisiones.

---

## 🔍 Análisis de Brecha ("El Hueco Honesto")

| Requisito Faltante | Estado Actual | Plan de Cierre Técnico | Fecha Estimada de Cumplimiento |
|---|---|---|---|
| **Suite de Pruebas Automatizadas (CI/CD)** | No existen tests unitarios ni integración de GitHub Actions para el flujo financiero. | Escribir pruebas unitarias de integración de balances y configurar el workflow de validación en `.github/workflows/test.yml`. | 15 de Septiembre de 2026 |
| **Verificación de Identidad on-chain en SCF** | La cuenta de la organización aún no ha completado el formulario KYC/KYB y la vinculación formal en el portal de SCF. | Completar la verificación de identidad del equipo y registrar el ID del proyecto en el portal oficial de SCF. | 30 de Septiembre de 2026 |

---

## 🛠️ Flujo de Trabajo y Guía de Contribución

**Clonación del Entorno:**

```bash
git clone https://github.com/SistemasTecTlaxiaco/gestion-de-proyectos-de-software-repositorio-e-infraestructura-financiera-nallely-lopez.git
cd gestion-de-proyectos-de-software-repositorio-e-infraestructura-financiera-nallely-lopez
```

**Creación de Rama:**

```bash
git checkout -b feature/nombre-de-la-tarea
```

**Estandarización de Commits:** Utilizar mensajes descriptivos siguiendo la convención de Conventional Commits:

```bash
git commit -m "feat(milestones): agrega backlog detallado en documentacion"
```

**Envío de Pull Request:** Vincular el PR directamente al Issue y Milestone correspondiente.

---

## 📚 Bibliografía y Fuentes Primarias

- Drips Protocol Development Team. *Drips Network Technical Documentation and Architecture Specification*. Radicle Foundation, 2024-2026. Disponible en: https://docs.drips.network/
- GitHub Documentation. *About milestones and tracking issues*. GitHub Docs, 2026. Disponible en: https://docs.github.com/en/issues/using-labels-and-milestones-to-track-work/about-milestones
- Stellar Development Foundation. *Stellar Community Fund (SCF) Program Guidelines, Governance, and Milestone Verification*. SDF, 2025-2026. Disponible en: https://communityfund.stellar.org/
- Soroban Documentation. *Smart Contracts on Stellar*. Stellar Development Foundation, 2026. Disponible en: https://soroban.stellar.org/docs

---

## ✍️ Autora y Licencia

Este proyecto se distribuye bajo licencia MIT. Consulta el archivo `LICENSE` para más detalles.
