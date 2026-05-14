# Wiki de Documentación de Software

Este proyecto consiste en una plataforma Wiki centralizada para la gestión de documentación técnica, desarrollada bajo una arquitectura cliente-servidor.

## Diagrama de Arquitectura del Sistema
Este diagrama se basa íntegramente en la propuesta técnica desarrollada para nuestro proyecto de pasantías.(Desarrollo Web)
El siguiente diagrama describe el flujo de datos entre la interfaz de usuario, la lógica de negocio en Flask y el repositorio de persistencia:

```mermaid
graph TD
    User((Usuario / Cliente)) -->|Petición HTTP| Web[Capa de Presentación - HTML/CSS]
    Web -->|Solicitud de Datos| App[Lógica de Negocio - Python/Flask]
    
    subgraph Servidor de Aplicaciones
        App -->|Consulta de Archivos| DB[(Repositorio de Documentación)]
        DB -->|Retorno de Datos| App
    end
    
    App -->|Renderizado de Plantilla| Web
    Web -->|Respuesta de Interfaz| User
    
    %% Estilos de Ingeniería
    style Web fill:#e3f2fd,stroke:#1565c0,stroke-width:2px
    style App fill:#fffde7,stroke:#fbc02d,stroke-width:2px
    style DB fill:#ffebee,stroke:#c62828,stroke-width:2px
