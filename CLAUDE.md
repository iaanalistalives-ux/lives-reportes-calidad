# CLAUDE.md — Reportes digitalizados de Calidad Manufactura (lives-reportes-calidad)

Las reglas generales de trabajo están en el repo privado `lives-instrucciones` (CLAUDE.md). Este archivo solo describe esta herramienta.

## Qué hace
`index.html` es un **buscador y visor de solo lectura** del archivo histórico de papeles escaneados de Calidad Manufactura: hojas de medida, medida de corte, auditorías de proceso de costura, auditoría final, acabados y costura, medidas después de vapor y auditorías de corte (9 tipos oficiales que unifican más de 160 nombres de carpeta).
- Los papeles se copiaron del servidor a la base el 23/09/2026; no se agregan documentos nuevos. Cliente, grupo, estilo, color y tipo salen de la ruta de carpeta y archivo (nadie los digitó). No hay fecha.
- Filtros en cascada (cliente, grupo, estilo, color, tipo) con conteo, búsqueda de texto, chips y "Limpiar". Regla 500 en la lista de tarjetas.
- Visor: páginas, zoom, girar, flechas del teclado; PDF con pdf.js e imágenes; "Abrir PDF ↗" con enlace firmado.
- Excel LIVES (perfil `RDG`): Resumen por tipo y por cliente, y Detalle con una fila por documento.

## Base de datos (Supabase lives-datos)
- `escaneos_catalogo` (todo el catálogo de documentos) y `escaneos_paginas_doc` (páginas de un documento), ambas sobre la tabla `escaneos_paginas`.
- Archivos: bucket privado `escaneos`, con enlaces firmados de 1 hora.

## Quién la usa
Según las entradas por el portal de los últimos 30 días al 21/10/2026: 3 personas (Gerencia de Producción, Gerencia Textil y la digitadora de Calidad Manufactura).

## Quién puede ver
Solo lectura. Lo decide la función de permiso `escaneos_puede_ver`.

## Pendientes vistos al escribir esto (21/10/2026)
- Código sin uso: `TOPE` y `mas()` ("ver más"), reemplazados por la regla 500.
