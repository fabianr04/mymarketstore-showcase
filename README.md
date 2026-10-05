<div align="center">

  <h1>MY Market Store</h1>
  <h3>Sistema de Planificación de Recursos Empresariales (ERP)</h3>
  
  <p align="center">
    <img src="https://img.shields.io/badge/Estado-Pre--Producción-00A2ED?style=flat-square&logoColor=white" alt="Estado" />
    <img src="https://img.shields.io/badge/Arquitectura-KMP_|_MVI-0A192F?style=flat-square&logoColor=white" alt="Arquitectura" />
    <img src="https://img.shields.io/badge/Despliegue-Contabo_VPS-E3E9F0?style=flat-square&logoColor=0A192F&labelColor=E3E9F0&color=E3E9F0" alt="Deploy" />
  </p>

  <br>
  
  <blockquote>
    <b>Nota de Confidencialidad:</b> Por protección de la propiedad intelectual y la lógica de negocio de la empresa, el código fuente se mantiene privado. Este documento exhibe la arquitectura, los retos resueltos y el despliegue funcional con datos de prueba.
  </blockquote>

</div>

<br>

<h2>VISIÓN GENERAL</h2>

Sistema de Planificación de Recursos Empresariales (ERP) desarrollado a medida para resolver la descentralización de la información. El sistema consolida todos los procesos operativos en una **única fuente de la verdad**, permitiendo a la organización gestionar su flujo comercial desde los inventarios hasta el registro de los pagos de manera fluida y segura.

<br>

<h2>ARQUITECTURA Y STACK</h2>

Para este desarrollo, se seleccionó un ecosistema robusto basado en **Kotlin**, garantizando seguridad, escalabilidad y un rendimiento óptimo tanto en el cliente como en el servidor.

<table width="100%">
  <tr>
    <td width="33%" align="center">
      <b>Cliente & Multiplataforma</b><br><br>
      <img src="https://img.shields.io/badge/Kotlin-005BB5?style=flat-square&logo=kotlin&logoColor=white" /> <br>
      <img src="https://img.shields.io/badge/Kotlin_Multiplatform-005BB5?style=flat-square&logo=kotlin&logoColor=white" /> <br>
      <img src="https://img.shields.io/badge/Koin_(DI)-005BB5?style=flat-square&logo=kotlin&logoColor=white" />
    </td>
    <td width="33%" align="center">
      <b>Backend & APIs</b><br><br>
      <img src="https://img.shields.io/badge/Spring_Boot-0A192F?style=flat-square&logo=springboot&logoColor=white" /> <br>
      <img src="https://img.shields.io/badge/Ktor-0A192F?style=flat-square&logo=ktor&logoColor=white" /> <br>
      <img src="https://img.shields.io/badge/MySQL-0A192F?style=flat-square&logo=mysql&logoColor=white" />
    </td>
    <td width="33%" align="center">
      <b>Infraestructura & Seguridad</b><br><br>
      <img src="https://img.shields.io/badge/JWT_&_OAuth_2.0-808080?style=flat-square&logo=jsonwebtokens&logoColor=white" /> <br>
      <img src="https://img.shields.io/badge/Contabo_VPS-808080?style=flat-square&logo=linux&logoColor=white" /> <br>
      <img src="https://img.shields.io/badge/Supabase_Storage-808080?style=flat-square&logo=supabase&logoColor=white" />
    </td>
  </tr>
</table>

<br>

<h2>MÓDULOS DEL SISTEMA</h2>

El ERP está segmentado en módulos interconectados para cubrir todo el ciclo de negocio, incluyendo soporte para geolocalización a través de mapas[cite: 1] y seguimiento detallado a través del historial operativo[cite: 1]:

<table width="100%">
  <tr>
    <td width="50%">
      <b>Ventas y Catálogo</b><br>
      Gestión estructurada de perfiles de clientes[cite: 1] y productos[cite: 1], un motor integral para la creación de órdenes[cite: 1] y la aplicación dinámica de promociones[cite: 1].
    </td>
    <td width="50%">
      <b>Finanzas y Tesorería</b><br>
      Módulo integral para la gestión de cuentas en bancos[cite: 1], registro y procesamiento de pagos[cite: 1], manejo de tasas actualizadas[cite: 1] y control del flujo de cobranzas[cite: 1].
    </td>
  </tr>
  <tr>
    <td width="50%">
      <b>Almacén y Logística</b><br>
      Control estricto de inventario en almacén[cite: 1], incluyendo dominio de productos almacenados[cite: 1], y una sección especializada para la gestión de devoluciones[cite: 1].
    </td>
    <td width="50%">
      <b>Administración y Analítica</b><br>
      Seguridad basada en flujos de login[cite: 1] y administración de usuarios[cite: 1], complementado con un panel de presentación de estadísticas[cite: 1] para la toma de decisiones.
    </td>
  </tr>
</table>

<br>

<h2>RETOS TÉCNICOS SUPERADOS</h2>

<p>Durante el ciclo de desarrollo, se resolvieron problemas arquitectónicos complejos para asegurar la estabilidad del sistema:</p>

<details>
  <summary><kbd>Ver detalle</kbd> <b>Manejo de Sesiones Simultáneas</b></summary>
  <blockquote>
    Se implementó una lógica de control de concurrencia combinando <b>JWT</b> y el manejo de estado en el backend, permitiendo que un mismo usuario pueda operar en dos dispositivos diferentes de forma simultánea sin corromper la sesión ni causar conflictos de datos.
  </blockquote>
</details>

<details>
  <summary><kbd>Ver detalle</kbd> <b>Integridad Transaccional en Cálculos</b></summary>
  <blockquote>
    Se diseñó un motor de cálculo robusto en el backend para asegurar que, al modificar un pedido existente o aplicar promociones y descuentos superpuestos, la integridad matemática se mantuviera intacta, evitando fugas financieras o errores en el total a cobrar.
  </blockquote>
</details>

<details>
  <summary><kbd>Ver detalle</kbd> <b>Migración de Infraestructura de Almacenamiento</b></summary>
  <blockquote>
    Se reestructuró la capa de persistencia de archivos migrando hacia <b>Supabase Storage buckets</b> desplegado de forma centralizada en un VPS de Contabo, garantizando mayor velocidad de respuesta en la carga de imágenes de catálogo y optimizando costos operativos.
  </blockquote>
</details>

<br>

<h2>IMPACTO EN EL NEGOCIO</h2>

* <kbd>Centralización</kbd> **Única Fuente de la Verdad:** Eliminación de hojas de cálculo dispersas, centralizando todos los datos operativos y el catálogo visual.
* <kbd>Optimización</kbd> **Mejora de Flujos Operativos:** Reducción de tiempos de gestión manual mediante automatización y un backend autónomo.
* <kbd>Relación</kbd> **Excelencia en Atención al Cliente:** Información certera al tomar pedidos, mejorando el servicio ofrecido y permitiendo devoluciones rápidas.

<br>

<h2>DEMOSTRACIÓN VISUAL</h2>

<div align="center">
  <i>A continuación se muestra el funcionamiento de la interfaz.</i>
  <br><br>
  <img src="https://youtu.be/AGz-Q6Aq3pw" width="85%" alt="Demostración de la Interfaz" />
</div>
