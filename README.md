Memo Dental — Asistente Virtual con IA
Este proyecto es un asistente virtual inteligente diseñado para la Clínica Dental MemoDental. Utiliza una arquitectura de Agente IA orquestada en n8n para automatizar la atención al cliente, responder preguntas frecuentes y gestionar la agenda de citas directamente en Google Calendar.

🚀 Características
Interfaz Web Personalizada: Frontend desarrollado en HTML5, CSS3 y JavaScript con diseño responsivo y burbujas de chat tipo moderno.

Arquitectura de Agente (Agent-Stack): Uso de un nodo AI Agent en n8n que coordina múltiples herramientas y memoria.

Memoria Persistente: Implementación de localStorage y sessionId para mantener el contexto de la conversación incluso si se refresca la página.

RAG (Retrieval-Augmented Generation): Integración con Qdrant Vector Store para proporcionar respuestas precisas basadas en los servicios y precios reales de la clínica.

Automatización de Citas: Capacidad de agendar eventos en Google Calendar y enviar notificaciones vía Gmail de forma automática.

Gestión de Sesiones: Incluye una función de "Limpiar Chat" que reinicia el contexto del agente generando un nuevo identificador de sesión.

🛠️ Stack Tecnológico
Orquestador: n8n.

IA Generativa: OpenAI (GPT-4o/GPT-3.5).

Base de Datos Vectorial: Qdrant.

Frontend: JavaScript (Fetch API), HTML y CSS.

Integraciones: Google Calendar API y Gmail API.

🔧 Configuración del Workflow
Para replicar este proyecto, el flujo en n8n requiere la siguiente configuración:

Webhook Trigger: Configurado con el método POST y CORS habilitado para permitir peticiones desde el dominio local o de producción.

Simple Memory: Configurada en modo "Define below" utilizando la expresión {{ $json.body.sessionId }} para vincular el historial al usuario correcto.

AI Agent: Cargado con un System Message que define la personalidad del asistente de MemoDental.

Respond to Webhook: Configurado para responder con "All Incoming Items" para asegurar una entrega de datos robusta al frontend.

📦 Instalación
Clona este repositorio.

Importa el archivo JSON del flujo en tu instancia de n8n.

Configura tus credenciales de OpenAI, Google y Qdrant.

En el archivo index.html, actualiza la constante WEBHOOK_URL con tu URL de producción de n8n.

Abre el archivo con Live Server en VS Code o súbelo a un hosting estático.
