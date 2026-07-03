# DMVPN (1 Hub y 2 Spokes) - Documentación Técnica

## Información del Proyecto
---

| Campo | Detalle |
| :--- | :--- |
| **Estudiante** | Juan Javier |
| **Matrícula** | Tu Matrícula Aquí |
| **Institución** | Instituto Tecnológico de Las Américas (ITLA) |
| **Asignatura** | Seguridad de Redes |
| **Profesor** | Nombre del Profesor |

## Índice
---

1. [DMVPN Fase 2 con IKEv1](#1-dmvpn-fase-2-con-ikev1)
2. [DMVPN Fase 3 con IKEv2](#2-dmvpn-fase-3-con-ikev2)

## Introducción a DMVPN
---

**DMVPN (Dynamic Multipoint VPN)** no es un protocolo único, sino una combinación de tres tecnologías:

| Tecnología | Función |
| :--- | :--- |
| **mGRE** (Multipoint GRE) | Permite múltiples túneles desde una sola interfaz |
| **NHRP** (Next Hop Resolution Protocol) | Resuelve direcciones IP públicas de los peers |
| **IPSec** | Proporciona encriptación y autenticación |

### Comparativa de Fases DMVPN

| Aspecto | Fase 1 | Fase 2 | Fase 3 |
| :--- | :--- | :--- | :--- |
| **Comunicación Spoke-Spoke** | Solo vía Hub | Directa | Directa |
| **Resolución NHRP** | N/A | Spoke solicita al Hub | Automática con redirect |
| **Escalabilidad** | Baja | Media | Alta |
| **Configuración** | Simple | Moderada | Compleja |

## 1. DMVPN Fase 2 con IKEv1
---

### Descripción

En DMVPN Fase 2, los Spokes pueden comunicarse **directamente entre ellos** sin que el tráfico tenga que pasar constantemente por el Hub. Es como si el Hub fuera una operadora que conecta la llamada y luego se retira para que los Spokes hablen en privado.

**Características de Fase 2:**

* Comunicación Spoke-to-Spoke directa después de resolución NHRP
* El Hub actúa como NHS (Next Hop Server) para resolución inicial
* Reduce la latencia en comunicaciones entre sucursales
* Menor carga de tráfico en el Hub

### Topología
---
