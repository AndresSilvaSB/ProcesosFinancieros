```mermaid
flowchart TD
    A([Inicio: Correo de Lina]) --> B[Identificar tipo de correo]
    
    B --> C{¿Tipo de<br/>correo?}
    
    C -->|Seguimiento| D[Revisar estado en Sheets<br/>y responder a Lina]
    D --> E([Fin: Seguimiento respondido])
    
    C -->|Solicitud nueva| F{¿Qué tipo de<br/>comisión?}
    
    F -->|BRPs<br/>Inmuebles de banco| G[Revisar datos del correo:<br/>Comisión de venta BRP]
    F -->|Constructoras<br/>Vivienda nueva| H[Revisar datos del correo:<br/>Comisión constructora]
    
    G --> I{¿Correo contiene<br/>todos los datos?}
    H --> I
    
    I -->|No| J[Responder correo<br/>solicitando datos faltantes]
    J --> K[Marcar como pendiente]
    K --> L{¿Respuesta<br/>recibida?}
    L -->|No| K
    L -->|Sí| I
    
    I -->|Sí| M[Llenar Google Forms<br/>de Comercialización]
    
    M --> N[Completar información<br/>del cliente desde notas<br/>copy/paste si es necesario]
    
    N --> O[Forms registra automáticamente<br/>en Google Sheets]
    
    O --> P[Validar integridad y<br/>consistencia de datos]
    
    P --> Q{¿Datos correctos?}
    
    Q -->|No| R[Corregir en Forms/Sheets]
    R --> P
    
    Q -->|Sí| S[Dejar campos vacíos para<br/>equipo de facturación]
    
    S --> T[Compartir/Notificar a<br/>equipo de facturación]
    
    T --> U([Fin: Comercialización registrada<br/>Pendiente de facturación])
    
    style A fill:#ffe1f5
    style E fill:#ffe1f5
    style U fill:#ffe1f5
    style J fill:#ffe1e1
    style R fill:#fff4e1
    style G fill:#e1f0ff
    style H fill:#f0e1ff
