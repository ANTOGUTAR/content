---
title: Tablas de compatibilidad y repositorio de datos de compatibilidad del navegador (BCD)
slug: MDN/Writing_guidelines/Page_structures/Compatibility_tables
page-type: mdn-writing-guide
browser-compat: api.AbortController
---

{{MDNSidebar}}

MDN tiene un formato estándar para tablas que ilustran la compatibilidad de tecnologías compartidas en todos los navegadores, como son DOM, HTML, CSS, JavaScript, SVG, etc.
Para que estos datos estén disponibles en varios proyectos mediante programación, se crea un paquete Node.js a partir del [`browser-compat-data` repository](https://github.com/mdn/browser-compat-data) y publicado en npm.

Para modificar los datos dentro de estas tablas, la documentación completa junto con los detalles más recientes de las convenciones y los esquemas JSON utilizados para representar los datos se pueden encontrar en el repositorio. [contributing guide](https://github.com/mdn/browser-compat-data/blob/main/docs/contributing.md) así como el [data guidelines guide](https://github.com/mdn/browser-compat-data/blob/main/docs/data-guidelines/index.md).
Si tiene preguntas o descubre problemas, le invitamos a [pedir ayuda](/en-US/docs/MDN/Community/Communication_channels).

## Uso de datos BCD en páginas MDN

Una vez incluidos los datos en el [`browser-compat-data`](https://github.com/mdn/browser-compat-data) repo, puede comenzar a incluir dinámicamente la compatibilidad del navegador y las tablas de especificaciones basadas en esos datos dentro de las páginas de MDN.

Para comenzar con datos BCD en páginas MDN, use la cadena de consulta especificada en el archivo fuente BCD para los datos relevantes que desea incluir.
Por ejemplo:

- {{domxref("AbortController")}} los datos de compatibilidad se definen en [api/AbortController.json](https://github.com/mdn/browser-compat-data/blob/main/api/AbortController.json) y se puede consultar usando `api.AbortController`.
- {{HTTPHeader("Content-Type")}} Los datos de compatibilidad del encabezado HTTP se definen en [http/headers/content-type.json](https://github.com/mdn/browser-compat-data/blob/main/http/headers/content-type.json) y la consulta es `http.headers.Content-Type`.
- {{domxref("VRDisplay.capabilities")}} los datos de compatibilidad de propiedades se definen en [api/VRDisplay.json](https://github.com/mdn/browser-compat-data/blob/main/api/VRDisplay.json) y su consulta es `api.VRDisplay.capabilities`.

La consulta de datos de compatibilidad debe especificarse en el frente de la página en la clave `browser-compat`.
Por ejemplo, {{domxref("AbortController")}} se agregaría como se muestra a continuación:

```md
---
title: AbortController
slug: Web/API/AbortController
page-type: web-api-interface
browser-compat: api.AbortController
---
```

Las tablas de compatibilidad y especificación correspondientes a la clave se representan automáticamente en lugar de la `\{{Compat}}` y `\{{Specifications}}` macros en la fuente.

Si se requieren varias tablas de compatibilidad/especificaciones en la misma página, puede especificar el valor de `browser-compat` como una matriz. Por ejemplo, para el [Channel Messaging API](/en-US/docs/Web/API/Channel_Messaging_API) esto se agregaría como se muestra a continuación:

```md
---
title: Channel Messaging API
slug: Web/API/Channel_Messaging_API
page-type: web-api-overview
browser-compat:
  - api.MessageChannel
  - api.MessagePort
---
```

Las llamadas a macro generan las siguientes tablas (y el correspondiente conjunto de notas):

### Ejemplo de tabla de compatibilidad

{{Compat}}

### Ejemplos de tablas de especificaciones

{{Specifications}}
