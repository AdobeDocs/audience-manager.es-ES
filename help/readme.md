---
source-git-commit: dfb0191e3ea6f6c360991a2012a15570b5cab771
workflow-type: tm+mt
translation-type: tm+mt
source-wordcount: '329'
ht-degree: 2%

---
# Instrucciones

**Nota: Esta página (o cualquier página readme.md) no se publicará en la documentación de cara al cliente**

## TDC

+ `TOC.md` en la raíz de la guía del usuario se proporciona la organización de los temas que se incluyen en la guía de esta solución.
+ Cada guía del usuario tendrá su propia `TOC.md` única, en la que podrá ordenar todas las páginas/temas según sea necesario.
+ La primera página de todas las guías del usuario es `overview.md`.

## Guía de usuario

+ La introducción a la guía del usuario se denomina `overview.md`
+ Cada tema de la guía del usuario tiene su propio directorio distinto.
   + Si hay un tema en la guía llamado *Implementación*, el directorio correspondiente es `/implementation`
+ Todos los recursos de imagen se almacenan en `/assets` en la raíz de la guía del usuario.
   + Todas las imágenes del directorio `/assets` se localizarán.
   + Las imágenes del directorio `/no-localize` no se localizarán (¡hay una sorpresa!). Esto se puede utilizar para garantizar en las versiones de loc que los recursos específicos no se reproducen innecesariamente.

## Metadatos de nivel de guía del usuario

+ Los metadatos que describen la guía del usuario se almacenan en `TOC.md`. Esto incluye:
   + producto: nombre del producto/capacidad.
   + cloud: nube a la que pertenece este producto.
   + audiencia: audiencia o arquetipo al que está dirigida la guía.
   + guía del usuario: nombre de la guía del usuario.

## Metadatos de nivel de página

+ Los metadatos necesarios para describir un documento se almacenan como parte de cada página individual. Esto incluye:
   + title - título de la página.
   + description: descripción de la página.
   + seo-title - seo título alternativo.
   + seo-description - título alternativo para fines SEO.
   + short-title: (campo opcional).
   + index - yes / no - la página será indexada por la plataforma de búsqueda de Adobe.
   + traducir - sí / no - se localizará esta página.
   + versión: se utiliza principalmente para AEM y Campaña, para denotar la versión del producto.
   + private-feature-pack: se utiliza principalmente para AEM.
   + beta - ¿Este producto está en versión beta?
   + redireccionamiento: se puede utilizar para crear una referencia a una nueva página si es necesario.
   + doc-type: referencia (predeterminado) / solución de problemas / desarrollador / tutorial / kb / documento técnico.

## Más información

Para obtener más instrucciones de publicación, guías de estilo, ejemplos y otros recursos, visite [Repo de documentación de colaboración](https://git.corp.adobe.com/AdobeDocs/collaborative-doc-instructions)
