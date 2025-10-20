# Proceso para facturación correos 

## Diagrama de flujo
### Puntos clave:

1. Santi identifica por remitente/contenido
2. Cada color representa un tipo de proceso diferente
3. Muestra el ciclo cuando falta información (deja pendiente, solicita, retoma)
4. Termina cuando facturación completa el proceso
```mermaid
flowchart TD
    A([Inicio: Santi recibe correo]) --> B[Identificar tipo de correo<br/>por remitente y contenido]
    
    B --> C{¿Qué tipo de<br/>correo es?}
    
    C -->|Stefanie<br/>Operaciones| D[Proceso:<br/>AVALÚOS]
    C -->|Alejandro<br/>El Tiempo| E[Proceso:<br/>EL TIEMPO]
    C -->|Lina<br/>Comercialización| F[Proceso:<br/>COMERCIALIZACIÓN]
    C -->|Negociaciones<br/>Especiales| G[Proceso:<br/>NEGOCIACIONES]
    C -->|Acabados| H[Proceso:<br/>ACABADOS]
    
    D --> I[Registrar en Google Forms/Sheets<br/>correspondiente]
    E --> I
    F --> I
    G --> I
    H --> I
    
    I --> J{¿Datos completos<br/>y correctos?}
    
    J -->|Sí| K[Compartir con equipo<br/>de facturación]
    J -->|No - Falta info| L[Dejar pendiente y<br/>solicitar datos faltantes]
    
    L --> M{¿Respuesta<br/>recibida?}
    M -->|Sí| I
    M -->|No| N[Continuar con<br/>otros correos]
    
    K --> O[Facturación completa<br/>campos finales]
    O --> P([Fin: Proceso completado])
    
    N -.Retomar después.-> M
    
    style D fill:#e1f5ff
    style E fill:#fff4e1
    style F fill:#ffe1f5
    style G fill:#e1ffe1
    style H fill:#f5e1ff
