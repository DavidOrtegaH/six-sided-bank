# Arquitectura

Six Sided Bank es una aplicación web bancaria desarrollada siguiendo los principios de la Arquitectura Hexagonal (Ports & Adapters).

La aplicación está formada por dos componentes principales:

- Un frontend desarrollado con React, encargado de la interfaz de usuario.
- Un backend desarrollado con Spring Boot, que expone una API REST consumida exclusivamente por el frontend.

La lógica de negocio permanece aislada de los detalles de infraestructura, permitiendo sustituir tecnologías como la base de datos o la interfaz de usuario sin afectar al dominio de la aplicación.