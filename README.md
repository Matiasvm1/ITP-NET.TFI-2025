<div align="center">

# 🏛️ IPT-NET  
### **Sistema de Gestión Institucional - .NET 8.0**

![.NET 8.0](https://img.shields.io/badge/.NET-8.0-512BD4?logo=dotnet)
![EF Core](https://img.shields.io/badge/EF%20Core-8.0-512BD4)
![SQL Server](https://img.shields.io/badge/SQL%20Server-2019+-CC2927?logo=microsoftsqlserver)
![C#](https://img.shields.io/badge/C%23-12.0-239120?logo=csharp)
![WinForms](https://img.shields.io/badge/UI-WinForms-blue)

**Sistema integral de gestión para Instituto Privado Tucuman.**

</div>

---

## 🎯 Propósito

**IVC-NET** es una aplicación de escritorio desarrollada en **WinForms sobre .NET 8**, diseñada para modernizar procesos administrativos del instituto.  
Integra dos dominios funcionales críticos:

- 🛒 **Venta de Indumentaria:** Gestión de stock, ventas, pagos y facturación.  
- 💰 **Cobro de Cuotas:** Administración de alumnos, generación de cuotas, vencimientos y recargos automáticos.

---

## 🏗️ Arquitectura y Tecnologías

El proyecto implementa una arquitectura en capas con patrón **MVP (Model–View–Presenter)**, lo que favorece el mantenimiento, la extensibilidad y la separación de responsabilidades.

### 📁 Estructura del Proyecto

```bash
IVC-NET/
├── TFI.Dominio/              # Entidades de dominio (POCOs) y reglas de negocio
│   ├── Empleado.cs
│   ├── Venta.cs, LineaDeVenta.cs, Pago.cs
│   ├── Stock.cs, Indumentaria.cs
│   └── Alumno.cs, Cuota.cs
│
├── TFI.AccesoADatos/         # Capa de persistencia (EF Core 8)
│   ├── IPTNetContext.cs      # DbContext
│   ├── Repositorio.cs        # Repository Pattern (genérico)
│   └── Migrations/           # Historial de migraciones
│
└── TFI.Vista/                # UI y lógica de presentación (MVP)
    ├── Vistas/               # Formularios WinForms
    ├── Presentadores/        # Lógica de interacción
    ├── DTOs/                 # Data Transfer Objects
    └── App.config            # ConnectionStrings y configuración
⚙️ Tecnologías Clave
Framework: .NET 8.0 (C# 12)

ORM: Entity Framework Core 8.0.11

Base de Datos: SQL Server 2019+ / LocalDB

DI Container: Unity

UI: WinForms con estilos personalizados

🚀 Instalación y Puesta en Marcha
1️⃣ Requisitos Previos
Visual Studio 2022 (17.8+)

.NET 8.0 SDK

SQL Server (LocalDB / Express / Developer)

Git

2️⃣ Clonar el Repositorio
bash
Copiar código
git clone https://github.com/tu-usuario/IVC-NET.git
cd IVC-NET
3️⃣ Configurar Cadena de Conexión
Editar TFI.Vista/App.config:

xml
Copiar código
<add name="IvcDb"
     connectionString="Data Source=.\SQLEXPRESS;Initial Catalog=IvcDb;Integrated Security=True;Encrypt=False;"
     providerName="System.Data.SqlClient" />

<add name="IvcDb"
     connectionString="Data Source=(localdb)\MSSQLLocalDB;Initial Catalog=IvcDb;Integrated Security=True;"
     providerName="System.Data.SqlClient" />
4️⃣ Crear Base de Datos (Migraciones)
En Package Manager Console, seleccionar TFI.AccesoADatos como Proyecto predeterminado:

powershell
Copiar código
Update-Database
5️⃣ Compilar y Ejecutar
bash
Copiar código
dotnet build
O simplemente ejecutar F5 en Visual Studio (proyecto de inicio: TFI.Vista).

🧭 Uso del Sistema
🔐 Inicio de Sesión
El sistema requiere un usuario registrado en Empleados.
Puede utilizarse uno creado manualmente o proveniente del Seeder (si está habilitado).

👕 Módulo de Ventas de Indumentaria
Buscador: Filtrado por código o descripción.

Carrito: Selección de talle/cantidad con validación instantánea de stock.

Check-out: Emite factura y descuenta automáticamente el inventario.

🎓 Módulo de Gestión de Cuotas
ABM de alumnos.

Generación automática de cuotas mensuales.

Recargos: Se aplica un 5% acumulativo por cada vencimiento atrasado.

Código de barras: Generación simulada para identificación de cuotas.

🧑‍💻 Créditos
Proyecto: IPT-NET
Equipo: Grupo 6 – Diseño de Sistemas
Institución: UTN – Facultad Regional Tucumán
Año: 2025

<div align="center"></div> ```


