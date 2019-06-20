---
source-git-commit: dee392312d8e0381c714a99b5d537c767107c9bc
translation-type: tm+mt

---
# Instrucciones

**Nota: Esta página (o cualquier página léame. md) no se publicará en la documentación de cliente**

## TDC

+ `TOC.md` en la raíz de la guía del usuario proporciona la organización de los temas contenidos en la guía para esta solución.
+ Each user guide will have its own unique `TOC.md`, in which you can order all the pages/topics as necessary.
+ The first page of all user guides is `overview.md`.

## Guía de usuario

+ The introduction to the user guide is called `overview.md`
+ Cada tema de la guía del usuario tiene su propio directorio diferente.
   + If there is a topic in the guide called *Implementation*, the corresponding directory is `/implementation`
+ All image assets are stored in `/assets` at the root of the user guide.
   + All images in the `/assets` directory will be localized.
   + Any images in the `/no-localize` directory will not be localized (there&#39;s a surprise!). Esto se puede utilizar para asegurar en versiones loc que los recursos específicos no se reproducen de forma innecesaria.

## Metadatos del nivel de guía del usuario

+ Meta data which describes the user guide is stored in the `TOC.md`. Esto incluye:
   + product - nombre de producto/capacidad.
   + cloud - cloud a la que pertenece este producto.
   + audiencia: audiencia o arquetipo a la que se dirige la guía.
   + user-guide - nombre de la guía del usuario.

## Metadatos de nivel de página

+ Los metadatos requeridos para describir un documento se almacenan como parte de cada página individual. Esto incluye:
   + title: título de la página.
   + description: descripción de la página.
   + seo-title: título alternativo.
   + seo-description: título alternativo para SEO.
   + short-title - (campo opcional).
   + index (sí/no); la página de búsqueda de Adobe indexará la página.
   + translate - yes/no - will this page be localized.
   + versión que se utiliza principalmente para AEM y Campaign, para denotar la versión del producto.
   + private-feature-pack: se usa principalmente para AEM.
   + beta -¿este producto está en beta?
   + redirigir: se puede utilizar para crear una ref a una página nueva que sea necesaria.
   + doc-type: reference (predeterminado)/troubleshooting/developer/tutorial/kb/whitepaper.

## Más información

For more publishing instructions, style guides, samples and other resources, please visit the [Collaborative Documentation Repo](https://git.corp.adobe.com/AdobeDocs/collaborative-doc-instructions)
