# 🏛️ Asistente Virtual RAG de Normativa Fiscal y Legal - Auren Spain

Solución enterprise de **Generación Aumentada por Recuperación (RAG)** basada en el ecosistema **Microsoft 365 y Azure AI**, diseñada para optimizar las consultas de normativa fiscal y legal interna para los consultores de Auren Spain.

---

## 🎯 Objetivo del Proyecto

Proporcionar a los consultores y asesores de Auren un punto de acceso centralizado, inteligente y seguro en **Microsoft Teams** para consultar leyes, circulares internas, deducciones y normativas actualizadas, garantizando respuestas deterministas, con citación obligatoria de fuentes oficiales en SharePoint y cero alucinaciones.

---

## 🏗️ Arquitectura Técnica End-to-End

```text
 [ Documentos PDF/Word ]       [ Ingesta / Eventos ]         [ Indexación Vectorial ]
┌──────────────────────┐      ┌─────────────────────┐       ┌────────────────────────┐
│  SharePoint Online   │ ───> │   Microsoft Graph   │ ────> │    Azure AI Search     │
│ (Biblioteca Auren)   │      │ (Webhooks / Events) │       │ (Vector Search Index)  │
└──────────────────────┘      └─────────────────────┘       └────────────────────────┘
                                                                        │
                                                                        │ Búsqueda Semántica JIT
                                                                        ▼
 [ Canal de Usuario ]          [ Agente Conversacional ]     [ Modelo de Razonamiento ]
┌──────────────────────┐      ┌─────────────────────┐       ┌────────────────────────┐
│   Microsoft Teams    │ <─── │   Copilot Studio    │ <───> │      Azure OpenAI      │
│  (App Corporativa)   │      │ (Orquestador RAG)   │       │ (GPT-4o / Temp = 0.0)  │
└──────────────────────┘      └─────────────────────┘       └────────────────────────┘