```mermaid
flowchart TD
    A([Inicio: Correo de Alejandro<br/>fin de mes]) --> B[Descargar PDF adjunto<br/>con conciliación]
    
    B --> C[Revisar documento:<br/>• Conciliación El Tiempo → Cien Cuadras<br/>• Conciliación Cien Cuadras → El Tiempo]
    
    C --> D{¿PDF contiene<br/>toda la información?}
    
    D -->|No| E[Responder correo<br/>solicitando aclaración]
    E --> F[Marcar como pendiente]
    F --> G{¿Respuesta<br/>recibida?}
    G -->|No| F
    G -->|Sí| B
    
    D -->|Sí| H[Abrir Google Sheets<br/>de El Tiempo directamente]
    
    H --> I[Copiar/pegar datos del PDF:<br/>• Cantidad publicaciones Web<br/>• Cantidad publicaciones Impresas<br/>• Valor Unitario<br/>• Valor Total Neto<br/>• IVA si aplica<br/>• Valor Total]
    
    I --> J[Escribir descripción:<br/>N° de cobros que se están<br/>haciendo del mes]
    
    J --> K[Completar información<br/>del cliente El Tiempo<br/>desde notas copy/paste]
    
    K --> L[Validar integridad y<br/>consistencia de datos]
    
    L --> M{¿Datos correctos<br/>y sin IVA?}
    
    M -->|No| N[Corregir en Sheets]
    N --> L
    
    M -->|Sí| O[Dejar campo vacío para<br/>equipo de facturación:<br/>• N° de factura]
    
    O --> P[Compartir/Notificar a<br/>equipo de facturación]
    
    P --> Q([Fin: El Tiempo registrado<br/>Pendiente de facturación])
    
    style A fill:#fff4e1
    style Q fill:#fff4e1
    style E fill:#ffe1e1
    style N fill:#fff4e1
    style M fill:#e1ffe1
