---
layout: post
title: "Crear un proyecto con dotnet new CLI"
author: "Samuel Arellano"
categories: .NET
tags: [dotnet, cli, vscode]
image: Dotnet-new.png
---

Hola que tal mi gente:

Por medio del siguiente artículo vamos a ver como podemos crear proyectos de .NET utilizando las herramientas de línea de comandos denominado **CLI**.

Los pasos a realizar son los siguientes:

1. Abrir la consola de su preferencia. Puede ser cmd, powershell o alguna que haya descargado de la web. Igual se puede utilizar la terminal que se encuentra dentro de **VSCODE**

<div class="info-box">
    <i class="fa fa-commenting"></i> <strong>Comentario Personal</strong>
        <div>
            Yo utilizo Windows PowerShell
        </div>
</div>

2. Introduzca el comando `dotnet --version` para verificar que se encuentre instalado el **CLI de .NET** en su equipo de cómputo.

<img src="{{ site.github.url }}/assets/img/dotnet-version.PNG" alt="Dotnet CLI version">

3. Posteriormente introduzca el comando `dotnet new ` el cual le mostrará todas las plantillas que sencuentran disponibles para crear proyectos.

<img src="{{ site.github.url }}/assets/img/proyectos-dotnet-new.PNG" alt="Dotnet CLI version">

<div class="info-box orange">
    <i class="fa fa-info"></i> <strong>Nota</strong>
    <div>Como puede observar se encuentran diversas plantillas (templates) las cuales le permiten crear proyectos de consola, Blazor, WebApi, Class Library, Windows Forms y WPF.
    </div>
</div>

4. En este caso, vamos a realizar a manera de ejemplo un proyecto de Consola. Si usted coloca el comando `dotnet new console -h ` podrá visualizar las diversas opciones para poder crear el proyecto, como pueden ser la versión del Framework, el langVersion y si se desea la restauración o no del proyecto o bien referencias que se contengan en el mismo.

<img src="{{ site.github.url }}/assets/img/opciones-consola.PNG" alt="Dotnet CLI version">

Para crear nuestro proyecto es recomendable crear un directorio con el nombre del proyecto, en este caso: **cli-console**

<div class="info-box orange">
    <i class="fa fa-info"></i> <strong>Nota</strong>
    <div>
    Recuerda que para crear un directorio utilizamos el comando <code>mkdir cli-console</code> y para movernos al directorio utilizamos <code> cd cli-console </code>
    </div>
</div>

5. Posteriormente ejecutamos el comando `dotnet new console -f net6.0 ` para crear nuestro proyecto

<img src="{{ site.github.url }}/assets/img/proyecto-consola.PNG" alt="Dotnet CLI version">

Podrá visualizar como la herramienta de CLI empieza a generar los archivos.

6. Es necesio utilizar el comando `dotnet build` para poder construir nuestra aplicación (compilar) y para poder ejecutarla `dotnet run`.

<img src="{{ site.github.url }}/assets/img/proyecto-consola-dotnet-build.PNG" alt="Dotnet CLI version">

<img src="{{ site.github.url }}/assets/img/proyecto-consola-dotnet-run.PNG" alt="Dotnet CLI version">

Con este artílo podemos concluir que hemos creado nuestra primera aplicación utilizando CLI de .NET.
