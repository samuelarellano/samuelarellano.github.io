---
layout: post
title: "Introducción a StyleCop y Configuración (VS2019)"
author: "Samuel Arellano"
categories: .NET
tags: [dotnet, styleco, visualstudio, tools]
image: IntroStyleCop.png
---

Que tal amigos,

Sin duda alguna cuando trabajamos en un equipo de desarrollo de softare o bien en alguna consultoría, nos encontramos con que cada desarrollador tiene una forma o estilo de codificar. Cabe mencionar que será complicado encontrar a 2 programadores escribiendo de la misma manera uno que el otro. Eso se debe más a metodologías o bien a patrones de diseño que empleen cada uno de ellos. Esta es una de las razones por las cuales **StyleCop** cumple con su función principal, la cual es estandarizar la forma de codificar y facilitar los **Code Review (revisión de código)** al Sr o bien al Tech Lead.

Bien, StyleCop tiene la facultad de analizar nuestro código aplicando una serie de reglas de estilo. Cabe mencionar que existen 2 versiones de StyleCop (una es StyleCop y otra StyleCop Analyzer)

<div class="info-box orange">
    <i class="fa fa-info"></i> <strong>Nota</strong>
    <div>Actualmente se utiliza StyleCop Analyzer, ya que esta versión contiene nuevas funcionalidades y reglas. No se puede utilizar en VS2022, ni tampoco con C# 9.0 en adelante debido a que no cuenta con soporte actualmente.
    </div>
    <img src="{{ site.github.url }}/assets/img/versiones-stylecop.PNG" alt="StyleCop">
</div>

Referencia: [StyleCop](https://github.com/DotNetAnalyzers/StyleCopAnalyzers)

Lo interesante es que se puede ejecutar dentro de Visual Studio y es bastante funcional cuando debes de contar con una buena arquitectura de solución, te permite que respetes los principios SOLID

Algo a tomar en cuenta, es que **StyleCop** tiene activadas todas las reglas por defecto, estas reglas son aquellas que nos brindarán sugerencias para mejorar la codificación que estamos realizando. Entre esas reglas podemos ver que requieres agregar tags de comentarios a las clases, secciones de copyright, headers, documentación de constructores, etc.

Lo interesante de **StyleCop** es que es una herramienta de código abierto por parte de Microsoft y en caso de que requieras modificar alguna regla o bien algo del tool, puedes bajar su código y realizar esos cambios.

Para tener claro el tipo de reglas que posee StyleCop, estas se pueden se clasificar en las siguientes categorías:

Documentación
Diseño
Mantenibilidad
Nomenclatura
Ordenación
Legibilidad
Espaciado

Pero bueno, vamos a ver como podemos realizar la configuración de **StyleCop** en nuestros proyectos.

Para este caso utilizaremos un proyecto en Consola en VS2019

<img src="{{ site.github.url }}/assets/img/vs2019.PNG" alt="StyleCop">

Paso 1: Abrimos VS2019 y presionamos el botón de **Create Project**

<img src="{{ site.github.url }}/assets/img/console-application.PNG" alt="StyleCop">

Paso 2: Colocamos el nombre del demo `stylecopDemo`

<img src="{{ site.github.url }}/assets/img/stylecop-demo.PNG" alt="StyleCop">

Paso 3: Instalamos el paquete NuGet para StyleCop.Analyzer

<img src="{{ site.github.url }}/assets/img/stylecop-analyzer.PNG" alt="StyleCop">

<br>

Paso 4: Vamos a descargar las reglas de StyleCop que recomiendo para desarrollos de aplicaciones con C# del buen Mike Parker [StyleCop.RuleSet](https://gist.github.com/mikeparker/c24e56172f548d66e9c2379896b8b563)

Paso 5: Les recomiendo hacer una carpeta con el nombre **\_stylecop** donde colocaremos las reglas y vamos a crear un archivo **stylecop.json**. El archivo contendrá el siguiente código.

<img src="{{ site.github.url }}/assets/img/folder-stylecop.PNG" alt="StyleCop">

<br>

<img src="{{ site.github.url }}/assets/img/stylecop-json.PNG" alt="StyleCop">

<br>

```json
{
  "$schema": "https://raw.githubusercontent.com/DotNetAnalyzers/StyleCopAnalyzers/master/StyleCop.Analyzers/StyleCop.Analyzers/Settings/stylecop.schema.json",
  "settings": {
    "documentationRules": {
      "companyName": "Samuel Arellano Dev",
      "copyrightText": "This source code is Copyright © {companyName} and MAY NOT be copied, reproduced,\npublished, distributed or transmitted to or stored in any manner without prior\nwritten consent from {companyName} (samuelarellano.dev)."
    },
    "orderingRules": {
      "usingDirectivesPlacement": "outsideNamespace"
    }
  }
}
```

Paso 6: Vamos a configurar nuestro archivo de proyecto **\*.csproj** y agregaremos las siguientes líneas.

<img src="{{ site.github.url }}/assets/img/config-stylecop.PNG" alt="StyleCop">

```
<Project Sdk="Microsoft.NET.Sdk">

<PropertyGroup>
  <OutputType>Exe</OutputType>
  <TargetFramework>netcoreapp3.1</TargetFramework>
</PropertyGroup>

<ItemGroup>
  <PackageReference Include="StyleCop.Analyzers" Version="1.1.118">
    <PrivateAssets>all</PrivateAssets>
    <IncludeAssets>runtime; build; native; contentfiles; analyzers; buildtransitive</IncludeAssets>
  </PackageReference>
</ItemGroup>

	<PropertyGroup>
		<CodeAnalysisRuleSet>..\..\_stylecop\StyleCopRules.ruleset</CodeAnalysisRuleSet>
	</PropertyGroup>

	<PropertyGroup>
		<GenerateDocumentationFile>true</GenerateDocumentationFile>
	</PropertyGroup>

	<PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Debug|AnyCPU'">
		<DocumentationFile>$(MSBuildThisFileDirectory)\bin\$(Configuration)\$(TargetFramework)\stylecopDemo.xml</DocumentationFile>
	</PropertyGroup>

	<ItemGroup>
		<PackageReference Include="StyleCop.Analyzers" Version="1.1.118">
			<PrivateAssets>all</PrivateAssets>
			<IncludeAssets>runtime; build; native; contentfiles; analyzers; buildtransitive</IncludeAssets>
		</PackageReference>
	</ItemGroup>

	<ItemGroup>
		<AdditionalFiles Include="..\..\_stylecop\stylecop.json" Link="stylecop.json" />
	</ItemGroup>

</Project>
```

Con esto hemos configurado las reglas y podemos comenzar a visualizar como **StyleCop** nos comienza a mostrar las sugerencias o convenciones a mejorar en nuestra aplicación dentro del listado de _Warnings_ y _Errors_.

<img src="{{ site.github.url }}/assets/img/lista-warnings-stylecop.PNG" alt="StyleCop">

<a href="{{ site.github.url }}/assets/stylecopDemo.zip">Puedes Descargar el código aquí

Si quieres aprender más respecto a como realizar análisis de código tienes el siguiente artículo de Microsoft como referencia.
https://docs.microsoft.com/en-us/dotnet/fundamentals/productivity/code-analysis
