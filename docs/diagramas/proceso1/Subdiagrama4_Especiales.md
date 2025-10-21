## sub-diagrama de NEGOCIACIONES ESPECIALES.
## 📋 Características:

1. Correos de diferentes personas (no estandarizado)
2. Incluye todos los campos de la imagen que compartiste
3. Flujo similar a los demás pero con datos específicos de negociaciones
4. Registro en Forms → Sheets/Drive

## Puntos pendientes de confirmar:

⚠️ Confirmar: Todos los datos vienen en el correo
⚠️ Confirmar: Validaciones especiales que hace Santi
```mermaid
flowchart TD
    A([Inicio: Correo de<br/>diferentes personas]) --> B[Revisar datos del correo]
    
    B --> C{¿Correo contiene<br/>todos los datos?}
    
    C -->|No| D[Responder correo<br/>solicitando datos faltantes]
    D --> E[Marcar como pendiente]
    E --> F{¿Respuesta<br/>recibida?}
    F -->|No| E
    F -->|Sí| B
    
    C -->|Sí| G[Extraer datos del correo:<br/>• N° Negocio<br/>• Fecha de Venta<br/>• Nombre Inmueble<br/>• Valor Inmueble<br/>• % Comisión Servicios Bolívar<br/>• Valor Comisión<br/>• IVA<br/>• Valor Separación<br/>• Soporte I<br/>• Valor Separación II]
    
    G --> H[Llenar Google Forms<br/>de Negociaciones Especiales]
    
    H --> I[Forms registra automáticamente<br/>en Google Sheets/Drive]
    
    I --> J[Validar integridad y<br/>consistencia de datos]
    
    J --> K{¿Datos correctos?}
    
    K -->|No| L[Corregir en Forms/Sheets]
    L --> J
    
    K -->|Sí| M[Dejar campos vacíos para<br/>equipo de facturación]
    
    M --> N[Compartir/Notificar a<br/>equipo de facturación]
    
    N --> O([Fin: Negociación registrada<br/>Pendiente de facturación])
    
    style A fill:#e1ffe1
    style O fill:#e1ffe1
    style D fill:#ffe1e1
    style L fill:#fff4e1
