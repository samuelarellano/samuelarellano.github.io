---
layout: post
title: "Introducción a DotNet CLI"
author: "Samuel Arellano"
categories: .NET
tags: [dotnet, cli, vscode]
image: introDotNetCLI.png
---
ESTA MODIFICADO

Hola que tal mi gente:

Mediante este artículo y posteriores vamos a aprender que es la **Interfaz de Línea de Comandos (en sus siglas en inglés, CLI)**, y como podemos emplearla para crear, construir, compilar y ejecutar aplicaciones .NET, las cuales pueden ser desplegadas en múltiples plataformas como Windows, MacOS y Linux. CLI es una herramienta relativamente nueva, ya que salió con .NET Core y actualmente la podemos emplear para realizar diversos tipos de aplicaciones debido a sus plantillas, tal cual las tenemos disponibles en Visual Studio 2022.

Cabe mencionar que podemos nosotros utilizar diversos medios para realizar nuestras aplicaciones en .NET como son:

- _La interfaz de línea de comandos de .NET (CLI)_
- _Utilizando Visual Studio (Windows / Mac)_
- _Utilizando Visual Studio Code_

Es importante señalar que para poder hacer uso de la CLI, necesitamos realizar la instalación deL SDK de [.NET](https://dotnet.microsoft.com/en-us/download/visual-studio-sdks), hay que recordar que la última versión actualente es la .NET 6, así que no necesitamos instalarla por separado en nuestro equipo de desarrollo.

Para comprobar si la CLI está instalada correctamente abriendo el símbolo del sistema en Windows y escribiendo dotnet y pulsando Enter. Si muestra el uso y la ayuda como se observa en la imagen, esto significa que está instalado correctamente.

<img src="{{ site.github.url }}/assets/img/CLI.PNG" alt="DotNet CLI">

<div class="info-box">
    <i class="fa fa-commenting"></i> <strong>Comentario Personal</strong>
        <div>
            En lo personal siempre utilizo Visual Studio o VS Code, es por eso que me he dado a la tarea de estudiar y compartir lo que estoy aprendiendo en el tema de CLI.
        </div>
</div>

Sin duda alguna, CLI contiene diversos comandos los cuales podemos clasificarlos como **comandos básicos, comandos de modificación de proyecto y el conjunto de comandos avanzados**. Estos comandos son utilizados de manera gráfica cuando utilizamos alguna plantilla como aplicaciones de consola, Web API, Proyectos ASP.NET MVC, etc. Pero con CLI los haremos en una interfaz de comandos.

El comando principal o bien conocida como estructura básica de comandos es la siguiente:

`dotnet <comando> <argumento> <opción>`

Debes de tener presente que todos los comandos comienzan con la palabra **dotnet**, sin ello no podrás ejecutar el CLI en tu consola. Una vez que hayas colocado la palabra **dotnet**, podremos utilizar un comando o verbo para realizar la acción que estemos solicitando.

<div class="info-box orange">
    <i class="fa fa-info"></i> <strong>Nota</strong>
    <div>Cada comando puede contener argumentos y opciones.
    </div>
</div>

En la siguiente tabla puedes observar los comandos que poco a poco iremos viendo a través de los siguientes artículos para entender su funcionamiento.

**Comando Generales**

| Comando             | Funcionalidad                                                                    |
| ------------------- | -------------------------------------------------------------------------------- |
| dotnet build        | Permite hacer build de aplicaciones .NET                                         |
| dotnet build-server | Interactúa con los servidores iniciados por una compilación.                     |
| dotnet clean        | Clean build outputs.                                                             |
| dotnet help         | Muestra una documentación más detallada en línea para el comando.                |
| dotnet migrate      | Permite realizar migraciones de proyectos de .NET a versiones posteriores.       |
| dotnet msbuild      | Proporciona acceso a la línea de comandos de MSBuild.                            |
| dotnet new          | Inicializa un proyecto de C# o F# mediante plantillas.                           |
| dotnet pack         | Permite crear paquetes Nuget.                                                    |
| dotnet publish      | Publica una aplicación dependiente del marco de trabajo .NET o autónoma.         |
| dotnet restore      | Restores the dependencies for a given application.                               |
| dotnet run          | Ejecuta la aplicación desde el origen.                                           |
| dotnet sdk check    | Muestra el estado actualizado de las versiones instaladas del SDK y del Runtime. |
| dotnet sln          | Opciones para añadir, eliminar y listar proyectos en un archivo de solución.     |
| dotnet store        | Almacena los conjuntos en el almacén de paquetes en tiempo de ejecución.         |
| dotnet test         | Ejecuta las pruebas utilizando un corredor de pruebas.                           |

**Referencias de Proyecto**

| Comando                 | Funcionalidad                       |
| ----------------------- | ----------------------------------- |
| dotnet add reference    | Añade una referencia de proyecto.   |
| dotnet list reference   | Lista las referencias del proyecto. |
| dotnet remove reference | Elimina una referencia de proyecto. |

**Paquetes NuGet**

| Comando               | Funcionalidad                    |
| --------------------- | -------------------------------- |
| dotnet add package    | Permite agregar un paquete NuGet |
| dotnet remove package | Remover un paquete NuGet         |

**Comandos NuGet**

| Comando                     | Funcionalidad                                                                                                                                               |
| --------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------- |
| dotnet nuget delete         | Elimina o quita de la lista un paquete del servidor.                                                                                                        |
| dotnet nuget push           | Hace push un paquete al servidor y lo publica.                                                                                                              |
| dotnet nuget locals         | Borra o lista los recursos locales de NuGet, como la caché de solicitudes http, la caché temporal o la carpeta de paquetes globales de toda la computadora. |
| dotnet nuget add source     | Añade una fuente NuGet.                                                                                                                                     |
| dotnet nuget disable source | Desactiva una fuente NuGet.                                                                                                                                 |
| dotnet nuget enable source  | Activa una fuente NuGet.                                                                                                                                    |
| dotnet nuget list source    | Lista todos los orígenes NuGet                                                                                                                              |
| dotnet nuget remove source  | Elimina un origen NuGet.                                                                                                                                    |
| dotnet nuget update source  | Actualiza un orgine NuGet                                                                                                                                   |

En posteriores artículos veremos a fondo cada uno de estos comando y como podemos ir creando proyectos con .NET mediante **CLI**

Saludos.
Samuel Arellano
