---
layout: prose
title: Política de Privacidad
permalink: /es/legal/privacy/
lang: es
canonical_en: /legal/privacy/
canonical_es: /es/legal/privacy/
redirect_from:
  - /es/privacidad
  - /es/privacidad/
updated: 2026-07-11
---

# Política de Privacidad — Khazen

**Fecha de vigencia**: 2026-06-09
**App**: Khazen ([App Store](https://apps.apple.com/app/khazen/id6761610239))
**Responsable del tratamiento**: KHASSINX LLC, una sociedad de responsabilidad limitada de Florida (Estados Unidos)
**Contacto**: legal@khassinx.com

---

## Resumen

Khazen es una app de finanzas personales. Para funcionar, se conecta a tus cuentas bancarias y guarda tus transacciones en tus dispositivos y en tu iCloud personal. No vendemos, compartimos ni monetizamos tus datos financieros. No usamos publicidad, analytics ni tracking. Nuestro backend existe solo para retransmitir las conexiones bancarias — nunca alimenta un perfil publicitario sobre ti.

Puedes desconectar cualquier banco cuando quieras. Puedes borrar tu cuenta con un solo toque y eliminamos todo lo que tenemos de ti.

---

## Mapa rápido de lo que se recopila

| Categoría | ¿Se recopila? | Para qué |
|---|---|---|
| Datos de cuentas bancarias (saldos, transacciones, nombres de cuenta) | ✅ Sí | Para que la app muestre tu dinero |
| Identificador de Cuenta de Apple (opaco, para sync) | ✅ Sí | Sincronizar entre tus dispositivos vía iCloud |
| Correo electrónico | Solo si nos escribes | Responderte el mensaje |
| Estado de suscripción | ✅ Sí (vía Apple) | Verificar acceso a funciones pagas |
| Token de notificaciones push del dispositivo | ✅ Sí | Enviarte solo las notificaciones que activas |
| Informes de fallos | ❌ No | No recopilamos crash reports |
| Analytics de uso | ❌ No | Cero SDKs de analytics |
| Identificadores publicitarios (IDFA) | ❌ No | No los usamos |
| Ubicación | ❌ No | No la pedimos ni la usamos |
| Contactos / Fotos / Micrófono / Cámara | ❌ No | Khazen no accede a esto |

El manifiesto `PrivacyInfo.xcprivacy` de la app declara las mismas categorías. Apple lo verifica durante la revisión.

## Conexiones bancarias

Para mostrar tus transacciones, Khazen se conecta a tus bancos a través de **Plaid Inc.** ("Plaid"), una red regulada de datos financieros ampliamente usada por bancos y fintech en EE. UU. Cuando conectas una cuenta:

- Ingresas tus credenciales bancarias **directamente en la interfaz segura de Plaid**. **Khazen nunca ve ni guarda tu acceso bancario.** Plaid se autentica con tu banco usando los estándares de tu banco (OAuth donde tu banco lo soporte).
- Plaid devuelve los datos de cuenta y transacciones que eliges compartir, en modo **solo lectura**. Los tokens de acceso que permiten a Khazen actualizar tus datos están cifrados en tránsito y en reposo, y los revocamos cuando desconectas un banco o borras tu cuenta.
- **Khazen no es un banco, transmisor de dinero, corredor, prestamista ni institución financiera.** No retiene ni mueve tu dinero. Lee la información que eliges conectar y te ayuda a organizarla — nada más.

Actuamos como un **conducto**. Tus datos bancarios fluyen desde tu banco, a través de Plaid, hacia nuestro backend, y luego a tu dispositivo. Nuestro backend no enriquece tus datos con conjuntos de datos de terceros, no construye un perfil publicitario y no comparte tus datos con nadie.

Plaid es un servicio independiente; el tratamiento de tu información se rige por la **[Política de Privacidad para Usuarios Finales de Plaid](https://plaid.com/legal/#end-user-privacy-policy)**, que también aceptas dentro del flujo de conexión de Plaid. El uso del nombre de Plaid por parte de Khazen es únicamente para identificar a Plaid como el servicio que habilita las conexiones bancarias, y no implica ninguna sociedad, patrocinio ni respaldo por parte de Plaid Inc.

## Dónde viven tus datos

| Qué | Dónde |
|---|---|
| Transacciones, cuentas, presupuestos, metas, detección de recurrencias | Almacén local SwiftData en tu dispositivo + **tu iCloud personal** (cifrado, tu Cuenta de Apple) |
| Tokens de conexión bancaria (tokens de acceso de Plaid) | Cifrados en reposo en nuestro backend + en el Llavero (Keychain) del dispositivo |
| Estado de suscripción | Verificado localmente vía Apple StoreKit 2 + cruce contra servidor |
| Tokens de push | Tabla del backend indexada por tu identificador opaco de Cuenta de Apple |
| Preferencias de la app (categorías, moneda, tema) | Local + iCloud Key-Value Store |

La sincronización de iCloud usa **tu** Cuenta de Apple. Nosotros nunca vemos, accedemos ni tenemos forma de recuperar los datos sincronizados por iCloud. Apple los cifra en tránsito y en reposo. Si borras la app y eliminas los datos de iCloud, esa copia desaparece. Lo único que conservamos en nuestros propios servidores es el token de conexión bancaria necesario para actualizar tus transacciones — acotado a ese fin, y lo revocamos cuando desconectas el banco o borras tu cuenta.

## Proveedores de servicios

No vendemos ni compartimos tu información personal. Para operar Khazen nos apoyamos en unos pocos proveedores que procesan datos solo en nuestro nombre, únicamente para los fines de abajo y bajo contrato para protegerlos:

- **Conectividad bancaria — Plaid Inc.** conecta tus cuentas financieras en modo solo lectura (mira [Conexiones bancarias](#conexiones-bancarias) arriba).
- **Pagos — Apple Inc.** procesa todas las compras y suscripciones a través del App Store; nunca recibimos los datos de tu tarjeta.
- **Proveedores de infraestructura en la nube (Estados Unidos)** alojan nuestro backend y guardan los tokens de conexión necesarios para actualizar tus datos. Tus datos se almacenan y procesan en Estados Unidos.
- **Proveedores de entrega de contenido, DNS y seguridad** sirven nuestro sitio web y lo protegen del abuso; al enrutar y proteger el tráfico, algunos datos técnicos de conexión (como la dirección IP) pueden procesarse de forma transitoria en infraestructura de borde distribuida globalmente.

Estos proveedores solo pueden usar tu información para prestarnos servicios, y no pueden venderla ni compartirla.

## Retención de datos

Conservamos tus datos solo el tiempo que sirve al propósito para el que los diste:

- **Tokens de conexión bancaria** — hasta que desconectas el banco o borras tu cuenta.
- **Token de notificaciones push** — mientras tengas las notificaciones activadas.
- **Estado de suscripción** — mientras exista tu cuenta.
- **El correo que nos envías** — solo el tiempo necesario para atender tu mensaje.
- **Tus transacciones, saldos, presupuestos y metas** — viven en tu dispositivo y en tu propio iCloud, nunca en nuestros servidores.

Cuando borras tu cuenta, eliminamos tus registros y cerramos las conexiones bancarias que vinculaste.

## Apple Intelligence (IA en el dispositivo)

Cuando tu dispositivo lo soporta, Khazen usa **Apple Intelligence (FoundationModels)** para generar perspectivas financieras, categorizar transacciones y escribir resúmenes.

Este modelo corre **completamente en tu dispositivo**. Tus transacciones, saldos y contexto personal nunca salen de tu iPhone, iPad o Mac para el procesamiento de IA. No enviamos tus datos a OpenAI, Anthropic, Google ni a ningún servicio de IA de terceros. Tampoco tenemos un servidor de IA propio.

Apple Intelligence requiere iOS 26+ y un dispositivo reciente. En dispositivos sin Apple Intelligence, las funciones de IA de Khazen se ocultan silenciosamente y el resto de la app funciona normal.

## Suscripción y compras

Las suscripciones se procesan vía **Apple StoreKit 2**. Recibimos solo:

- Un booleano: esta Cuenta de Apple tiene una suscripción activa (vía `Transaction.currentEntitlements`)
- El producto actual (plan mensual o anual)
- Las fechas de renovación y revocación (para honrar cancelaciones y reembolsos rápidamente)

**No** vemos tu nombre, método de pago, dirección de facturación ni ningún otro metadato de compra. Apple maneja todo eso. Los reembolsos y la gestión de la suscripción pasan directamente por Apple (Ajustes → tu nombre → Suscripciones).

Prueba gratuita: siete días, sin cargos automáticos durante la prueba. Te enviamos notificaciones locales antes de que termine la prueba para que no haya renovaciones sorpresa.

**Si tu suscripción vence:** tus conexiones bancarias se pausan en vez de desconectarse, para que si te vuelves a suscribir pronto, tus cuentas se reconecten sin costo extra. Si no, las conexiones se cierran automáticamente. Puedes desconectar manualmente cuando quieras.

## Notificaciones y correo

- **Notificaciones push**: opt-in. Si las habilitas, tu dispositivo recibe un token de Apple Push Notification que guardamos asociado a tu identificador opaco de Cuenta de Apple. Las notificaciones se limitan estrictamente a lo que actives en la app (alertas de presupuesto, saldo bajo, etc.). No enviamos pushes de marketing.
- **Correo**: si nos escribes a cualquier dirección `@khassinx.com`, recibimos tu mensaje y tu dirección de respuesta vía nuestro proveedor de correo. Conservamos esa correspondencia para manejar la conversación y los seguimientos. No te agregamos a ninguna lista. Khazen no tiene lista de correo.

## Privacidad de menores

Khazen está dirigida a usuarios **de 13 años o más** (clasificación del App Store en consecuencia). No recopilamos a sabiendas datos de menores de 13 años. Si crees que un menor de 13 ha usado Khazen, escríbenos a legal@khassinx.com y eliminaremos sin demora cualquier dato asociado.

## Tus derechos

Tienes derecho a:

- **Acceder** a tus datos — visibles en la app en todo momento.
- **Borrar** tu cuenta — un solo toque desde Ajustes → Cuenta → Borrar cuenta en la app. Esto elimina tus registros de nuestro backend y cierra las conexiones bancarias que vinculaste. Los datos sincronizados por iCloud se eliminan cuando borras la app y limpias sus datos de iCloud en tu Cuenta de Apple.
- **Desconectar** conexiones bancarias individuales cuando quieras, sin borrar tu cuenta.
- **Oponerte** a cualquier procesamiento — escríbenos a legal@khassinx.com.
- **Portabilidad** — tus datos son tuyos; para pedir una copia, escribe a [`legal@khassinx.com`](mailto:legal@khassinx.com).

**Residentes de California:** **no vendemos ni compartimos** tu información personal (según la definen la CCPA/CPRA), y no lo hemos hecho en los últimos 12 meses. Para ejercer los derechos de privacidad de California, escribe a [`legal@khassinx.com`](mailto:legal@khassinx.com).

Para conocer el conjunto completo de derechos según tu región — la UE/EEE (RGPD), el Reino Unido, España (LOPDGDD), California (CCPA/CPRA), otros estados de EE. UU. y el resto del mundo — y cómo se aplican, consulta los [Derechos de Privacidad](https://khassinx.com/es/legal/your-rights/) de KhassinX. Para ejercer cualquiera de ellos en Khazen, usa los controles dentro de la app o escribe a [`legal@khassinx.com`](mailto:legal@khassinx.com).

## Etiquetas de Privacidad de Apple

En la ficha del App Store, Khazen declara las categorías de datos que realmente toca — actualmente Información financiera, Identificadores (User ID), Dirección de correo, Nombre, ID de dispositivo, Historial de compras y las notas que agregas a transacciones (Otro contenido del usuario) — cada una vinculada a ti y usada solo para la funcionalidad de la app, nunca para tracking ni publicidad. Las demás categorías no se recopilan.

La lista autoritativa es la que se declara en la ficha del App Store y en el manifiesto `PrivacyInfo.xcprivacy` de la app; esta política se remite a ellos, y se verifican contra el código real (sin SDKs de analytics, sin trackers de terceros, sin frameworks publicitarios).

## Seguridad

- Todo el tráfico usa **TLS 1.2+**.
- Los tokens de acceso bancario están cifrados en reposo en nuestro backend.
- El acceso al backend está limitado al mínimo de permisos necesarios, y los endpoints sensibles están protegidos por Apple App Attest junto con Sign in with Apple — las peticiones que no provengan de la app legítima de Khazen son rechazadas.
- La sincronización de iCloud usa el cifrado de extremo a extremo de Apple cuando tienes activada la Protección de Datos Avanzada.

Para reportar una vulnerabilidad, mira nuestra política de [Seguridad y divulgación responsable](/es/security/).

## Transferencias internacionales

El backend de Khazen opera en Estados Unidos. Si usas Khazen fuera de EE. UU., tus tokens de acceso bancario y otros registros del backend pueden procesarse en Estados Unidos. No transferimos tus datos a ningún otro país para su procesamiento.

## Cambios a esta política

Podemos actualizar esta política cuando:

- Se agregan funciones que cambian materialmente el manejo de datos
- Cambian las políticas del App Store
- Se corrigen errores legales o de hecho

Los cambios materiales se reflejarán con una nueva "Fecha de vigencia" arriba y se mostrará un aviso en la app al siguiente arranque.

## Notificación de incidentes

Ante una vulneración de datos confirmada que afecte tus datos personales:

- Notificaremos a las autoridades correspondientes en el plazo que exija la legislación aplicable, cuando dicha notificación sea requerida.
- Notificaremos a los usuarios afectados **sin demora injustificada** mediante una alerta en la app al siguiente arranque y, si tenemos un correo registrado, por correo electrónico.
- Publicaremos un post-mortem público en este sitio en `/security/incidents/` una vez completada la mitigación.

Hasta la fecha no hemos sufrido ninguna vulneración. Este compromiso establece el proceso por si ocurre.

## Jurisdicción

Esta política se rige por las leyes del **Estado de Florida, Estados Unidos** — la jurisdicción en la que KHASSINX LLC está constituida. Las disputas se resuelven bajo esas leyes.

## Marcas registradas

Apple, el logo de Apple, iPhone, iPad, Apple Watch, Mac y StoreKit son marcas comerciales de Apple Inc., registradas en EE. UU. y en otros países y regiones. App Store e iCloud son marcas de servicio de Apple Inc. Apple Intelligence es una marca comercial de Apple Inc. El uso del nombre "Sign in with Apple" está sujeto a las directrices de Apple. Plaid es una marca comercial de Plaid Inc. Las demás marcas pertenecen a sus respectivos dueños. Khazen es un producto de KHASSINX LLC y no está afiliado, respaldado ni patrocinado por estas empresas más allá de los servicios descritos en esta política.

## Este sitio web

Este sitio es estático. No usa cookies propias, no corre ningún tipo de analytics ni tracking, no incrusta scripts ni píxeles de terceros, y no tiene formularios. No rastreamos a nadie, así que no hay nada que una señal "Do Not Track" pueda apagar, y ningún tercero está autorizado a recolectar información sobre tu actividad en otros sitios a través de este sitio web. El sitio lo sirve GitHub Pages, con DNS y entrega a cargo de Cloudflare; como cualquier host web, esos proveedores procesan datos técnicos estándar de las solicitudes (como tu dirección IP) para servir y proteger el sitio, como empresas independientes bajo sus propias políticas de privacidad. Nosotros no recibimos, guardamos ni usamos esos datos.

## Contacto

Si tienes alguna duda o inquietud sobre privacidad:

- **Correo**: legal@khassinx.com
- **Postal**: Disponible por escrito a través del correo electrónico

Buscamos responder en siete días hábiles.

---

*Última actualización: 2026-06-09 · Versión 1.1*
