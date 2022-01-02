---
layout: post
title: "Introducción a DotNet CLI"
author: "Samuel Arellano"
categories: .NET
tags: [dotnet, cli, vscode]
image: introDotNetCLI.png
---

Hola que tal mi gente:

Mediante este artículo y posteriores vamos a aprender que es la **Interfaz de Línea de Comandos (en sus siglas en inglés, CLI)**, y como podemos emplearla para crear, construir, compilar y ejecutar aplicaciones .NET, las cuales pueden ser desplegadas en múltiples plataformas como Windows, MacOS y Linux. CLI es una herramienta relativamente nueva, ya que salió con .NET Core y actualmente la podemos emplear para realizar diversos tipos de aplicaciones debido a sus plantillas, tal cual las tenemos disponibles en Visual Studio 2022.

Cabe mencionar que podemos nosotros utilizar diversos medios para realizar nuestras aplicaciones en .NET como son:

- _La interfaz de línea de comandos de .NET (CLI)_
- _Utilizando Visual Studio (Windows / Mac)_
- _Utilizando Visual Studio Code_

Es importante señalar que para poder hacer uso de la CLI, necesitamos realizar la instalación deL SDK de [.NET](https://dotnet.microsoft.com/en-us/download/visual-studio-sdks), hay que recordar que la última versión actualente es la .NET 6, así que no necesitamos instalarla por separado en nuestro equipo de desarrollo.

Para comprobar si la CLI está instalada correctamente abriendo el símbolo del sistema en Windows y escribiendo dotnet y pulsando Enter. Si muestra el uso y la ayuda como se observa en la imagen, esto significa que está instalado correctamente.

<img src="{{ site.github.url }}/assets/img/CLI.PNG" alt="DotNet CLI">

<div class="info-box orange">
    <i class="fa fa-commenting"></i> <strong>Nota</strong>
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
