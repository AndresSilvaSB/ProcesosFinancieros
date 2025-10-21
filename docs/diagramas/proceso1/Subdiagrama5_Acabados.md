## sub-diagrama de ACABADOS 

### 📋 Características:

1. Correos esporádicos (~1 por mes)
2. SIN formulario - acceso directo a Google Sheets

### Puntos pendientes de confirmar:

⚠️ Confirmar: Si los campos son similares a otros procesos
⚠️ Confirmar: Quiénes son los remitentes típicos
```mermaid
flowchart TD
    A([Inicio: Correo de<br/>diferentes personas]) --> B[Revisar datos del correo]
    
    B --> C{¿Correo contiene<br/>todos los datos?}
    
    C -->|No| D[Responder correo<br/>solicitando datos faltantes]
    D --> E[Marcar como pendiente]
    E --> F{¿Respuesta<br/>recibida?}
    F -->|No| E
    F -->|Sí| B
    
    C -->|Sí| G[Extraer datos del correo:<br/>• Proyecto<br/>• Agrupación<br/>• Ciudad<br/>• Total Proyecto<br/>• Link Carpeta<br/>• Tipo de Combo<br/>• Factura<br/>• Fecha Factura<br/>• Observaciones]
    
    G --> H[Abrir Google Sheets<br/>de Acabados directamente<br/>sin formulario]
    
    H --> I[Registrar manualmente<br/>datos en el Sheets]
    
    I --> J[Completar información<br/>adicional si es necesaria]
    
    J --> K[Validar integridad y<br/>consistencia de datos]
    
    K --> L{¿Datos correctos?}
    
    L -->|No| M[Corregir en Sheets]
    M --> K
    
    L -->|Sí| N[Dejar campos vacíos para<br/>equipo de facturación]
    
    N --> O[Compartir/Notificar a<br/>equipo de facturación]
    
    O --> P([Fin: Acabado registrado<br/>Pendiente de facturación])
    
    style A fill:#f5e1ff
    style P fill:#f5e1ff
    style D fill:#ffe1e1
    style M fill:#fff4e1
    style A fill:#f5e1ff,stroke:#9d4edd,stroke-width:3px,stroke-dasharray: 5 5
    style P fill:#f5e1ff,stroke:#9d4edd,stroke-width:3px,stroke-dasharray: 5 5
    
    note1[Nota: Negocio en proceso<br/>de terminación<br/>~1 solicitud/mes]
    note1 -.-> A
