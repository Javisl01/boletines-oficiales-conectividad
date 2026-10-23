# Prueba pública de acceso a boletines oficiales

Repositorio: `Javisl01/boletines-oficiales-conectividad`.

Contiene únicamente este documento y `.github/workflows/probe.yml`. No copia código de EncuentraMúsico, secretos, configuración del servidor, documentos descargados ni datos de usuarios.

La prueba se ejecuta manualmente una sola vez en un runner estándar `ubuntu-24.04`, gratuito para repositorios públicos. No usa almacenamiento de artifacts, caché, acciones externas, cron, token de aplicación ni servicios de pago. No modifica las webs oficiales ni producción.

Realiza cuatro GET cerrados a documentos públicos de Málaga, Cuenca y Burgos. Guarda en el log público sólo estado HTTP, tamaño, huella SHA-256 y marcadores de formato; nunca cuerpos o cabeceras completas. Presupuesto máximo: cuatro minutos, cuatro solicitudes y 12 MiB por documento. No sigue redirecciones y respeta un 429/Retry-After evitando otras consultas al mismo host.

Su resultado sólo demuestra conectividad. Haría falta comprobar índices, documentos íntegros, sesiones y recuperación automática desde el servidor antes de integrar cualquier colector.

Esta es una prueba puntual de desarrollo para diagnosticar una integración HTTP. No es un colector de producción ni un respaldo automático de la ingesta. No tiene programación periódica y no envía documentos a otro sistema.

Referencia: https://docs.github.com/en/site-policy/github-terms/github-terms-for-additional-products-and-features#actions
