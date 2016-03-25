#Tresana

Tresana es una herramienta que permite a un equipo gestionar sus tareas siguiendo la metodología Scrum.

Cada tarea pertenece a un proyecto, y puede tener una lista de subtareas. Además, se le pueden agregar etiquetas que permitan facilicitar su organización.

Cada tarea se encuentra en un estado: Todo, In Progress, Freezer, Done.

Las tareas pueden estar asignadas a más de un usuario, aunque solo uno es el responsable de que se cumpla. Se pueden realizar comentarios sobre las tareas en una conversación interna, para poder documentar las decisiones tomadas con respecto a cada una.

#Usuario

- IdUsuario
- Nombre
- Apellido
- username
- Mail

#Equipo

- IdEquipo
- Nombre
- Url
- Miembros

#Proyecto

- IdProyecto 
- Nombre
- Fecha inicio
- Fecha fin
- Responsable
- Miembros

#Tarea

- IdTarea
- Nombre
- Prioridad
- Fecha comienzo
- Fecha Fin
- Estimación
- Responsables
- Estado
- Creador
- Fecha Creación
- Fecha de vencimiento

#Estados

- IdEstados
- Nombre

## Comienzo del desarrollo de Tresana

A lo largo del curso, utilizaremos el desarrollo de un producto como ejemplo para navegar entre las tecnologías correspondientes.
Desarrollaremos Tresana, un gestor de tareas para equipos.

Para el desarrollo de hoy deberemos contar con las siguientes herramientas:
 - Visual Studio 2015 Enterprise
 - SQL Server 2012
 - Cliente Postman

### Creando la estructura del proyecto

Para el desarrollo de la aplicación, deberá crearse una solución Tresana en Visual Studio con los siguientes proyectos:
 - Tresana.Web.Api: ASP.NET Web Application, con el formato vacío, importando Web API únicamente (como se muestra en las imágenes debajo)
 - Tresana.Web.Api.Models: Class Library
 - Tresana.Data: Class Library
 - Tresana.DataAccess: Class Library
 - Tresana.Services: Class Library
 - Tresana.Repository: Class Library

![](lib/img/Tresana/WebApplication.png)
![](lib/img/Tresana/EmptyWebApi.png)

Tresana.Data será el proyecto en el que colocaremos nuestras entidades. Tresana.DataAccess será el que contenga el contexto para EntityFramework. Tresana.Web.Api contendrá los servicios que expondremos a través de nuestra API REST, y Tresana.Web.Api.Models incluirá los modelos de las entidades. Esto último se debe a que no queremos acoplar nuestra api a nuestro modelo de dominio, por lo que generaremos lo que se conoce como DTO (DataTransferObjects). Estos objetos permitirán enviar únicamente los datos que deseo, además de moldearse mejor a las necesidades de la api rest, sin las restricciones de EntityFramework.

### Agregando nuestro dominio
En el proyecto Tresana.Data, cree las entidades reflejadas en el siguiente diagrama, dentro del namespace Tresana.Data.Entities

![](lib/img/Tresana/UMLClasses.png)

A continuación, debemos agregar EntityFramework al proyecto de DataAccess. Una vez agregado, debemos crear la clase TresanaContext en DataAccess, y agregarle una referencia al proyecto de Tresana.Data.Entities para poder utilizar las entidades.

```C#

using Tresana.Data.Entities;
using System.Data.Entity;

namespace Tresana.Data.DataAccess
{
    public class TresanaContext : DbContext
    {
        public DbSet<User> Users { get; set; }
        public DbSet<Entities.Task> Tasks { get; set; }
        public DbSet<Project> Projects { get; set; }
        public DbSet<Status> Statuses { get; set; }
        public DbSet<Priority> Priorities { get; set; }
        public DbSet<Team> Teams { get; set; }
    }
}
```

![](lib/img/Tresana/EntitiesProjectReference.png)

### Creando los Data Transfer Objects

//TODO: Definición de DTO

//TODO: Ver bien qué poner en el DTO y que no

### Creando el primer Controller - Usuario

//TODO: Explicacion de ApiController
//TODO: Explicacion de ruteo automático
//TODO: Explicación de IHttpActionResult

### Probando la aplicación con POSTMAN

### Moviendo la lógica a servicios

### 

##Preguntas para Fornaro:

- Damos IoC? Ninject o Autofac
- Patrón Repository? Para poder probar bien Base de datos.
- AutoMapper para Dtos? O que lo hagan a mano para no complicarla con herramientas?
