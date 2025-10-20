```mermaid
flowchart TD
    A([Inicio: Correo de Stefanie]) --> B[Revisar datos en el correo]
    
    B --> C{¿Correo contiene<br/>todos los datos<br/>requeridos?}
    
    C -->|No| D[Responder correo<br/>solicitando datos faltantes]
    D --> E[Marcar como pendiente<br/>y continuar con otros]
    E --> F{¿Respuesta<br/>recibida?}
    F -->|No| E
    F -->|Sí| B
    
    C -->|Sí| G[Extraer datos del correo:<br/>• Código gestionador<br/>• Nombre gestionador<br/>• Producto a facturar<br/>• Valor antes IVA<br/>• Valor post IVA<br/>• Total factura<br/>• N° publicaciones]
    
    G --> H{¿Es uno de los<br/>3 clientes<br/>frecuentes?}
    
    H -->|Sí| I[Completar manualmente<br/>desde notas copy/paste:<br/>• Nombre<br/>• Correo<br/>• Documento<br/>• Dirección<br/>• Ciudad<br/>• Teléfono]
    
    H -->|No - Cliente nuevo| J[Verificar si incluye RUT]
    J --> K{¿Tiene RUT?}
    K -->|No| D
    K -->|Sí| I
    
    I --> L[Llenar Google Forms<br/>con toda la información]
    
    L --> M[Forms registra automáticamente<br/>en Google Sheets]
    
    M --> N[Validar integridad y<br/>consistencia de datos]
    
    N --> O{¿Datos correctos?}
    O -->|No| P[Corregir en Forms/Sheets]
    P --> N
    
    O -->|Sí| Q[Dejar campos vacíos para<br/>equipo de facturación:<br/>• N° de factura]
    
    Q --> R[Compartir/Notificar a<br/>equipo de facturación]
    
    R --> S([Fin: Avalúo registrado<br/>Pendiente de facturación])
    
    style A fill:#e1f5ff
    style S fill:#e1f5ff
    style D fill:#ffe1e1
    style P fill:#fff4e1
