# 📘 Manual Operativo y Guía de Procesos: Copilot Studio RAG Auren

## 🛠️ 1. Flujo de Trabajo Operativo
Este manual detalla los procedimientos para la administración, actualización y gobierno del Asistente Virtual de Normativa Fiscal y Legal.

### Ingesta de Documentos
1. Acceder a la biblioteca de documentos en **SharePoint Online**: `Auren-Normativa-Fiscal`.
2. Guardar los archivos en formato PDF o Word con texto seleccionable.
3. El servicio de **Microsoft Graph** detecta la subida mediante un webhook de evento `OnNewDocument`.
4. El pipeline procesa el texto en **Azure AI Search**, generando los nuevos vectores sin requerir reiniciar o reentrenar el agente en **Copilot Studio**.

---

## 🎯 2. Estrategia de Gobernanza
- **Temperatura = 0.0**: Asegura respuestas deterministas basadas en evidencia.
- **System Prompt de Anclaje**: Prohíbe la generación de información no respaldada en las fuentes citadas.
- **Autenticación RBAC**: Control de acceso granular vía **Microsoft Entra ID** según el perfil del consultor.

---

## 💼 3. Respuestas a Preguntas Clave de Entrevista

### A. Gestión del Cambio (*Change Management*)
> "Centramos la adopción en la recuperación de tiempo útil para el consultor. Pasamos de búsquedas manuales de 40 minutos en documentos legales a respuestas inmediatas citadas en 5 segundos."

### B. Conectores Personalizados (*Custom Connectors*)
> "Para conectar ERPs externos como Sage o Salesforce, exponemos conectores mediante especificaciones OpenAPI (Swagger) intermediados de forma segura por **Azure Functions** y **Azure Key Vault**."