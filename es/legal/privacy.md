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
updated: 2026-05-26
---

# Política de Privacidad — Khazen

**Fecha de vigencia**: 2026-05-26
**App**: Khazen ([App Store](https://apps.apple.com/app/khazen/id6761610239))
**Desarrollador**: KhassinX LLC
**Contacto**: hello@khassinx.com

---

## Resumen

Khazen es una app de finanzas personales. Para funcionar, se conecta a tus cuentas bancarias y guarda tus transacciones en tus dispositivos y en tu iCloud personal. No vendemos, compartimos ni monetizamos tus datos financieros. No usamos publicidad, analytics ni tracking. Nuestro backend existe solo para retransmitir las conexiones bancarias — nunca alimenta un perfil publicitario sobre ti.

Puedes desconectar cualquier banco cuando quieras. Puedes borrar tu cuenta con un solo toque y eliminamos todo lo que tenemos de ti.

---

## Mapa rápido de lo que se recopila

| Categoría | ¿Se recopila? | Para qué |
|---|---|---|
| Datos de cuentas bancarias (saldos, transacciones, nombres de cuenta) | ✅ Sí | Para que la app muestre tu dinero |
| Identificador de Apple ID (opaco, para sync) | ✅ Sí | Sincronizar entre tus dispositivos vía iCloud |
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

Para mostrar tus transacciones, Khazen se conecta a tus bancos a través de una **red regulada de datos financieros** ampliamente usada por bancos y fintech en EE. UU. Esta red:

- Se autentica **directamente con tu banco** usando los estándares de tu banco (OAuth donde tu banco lo soporte, o el flujo seguro de la red en caso contrario). Khazen nunca ve tus credenciales bancarias.
- Devuelve tokens de acceso de corta duración, cifrados en tránsito y en reposo.
- Honra las desconexiones de inmediato — cuando quitas un banco en Khazen, el token de acceso se revoca.

Actuamos como un **conducto**. Tus datos bancarios fluyen desde tu banco hacia la red, luego a nuestro backend, y luego a tu dispositivo. Nuestro backend no enriquece tus datos con conjuntos de datos de terceros, no construye un perfil publicitario, no comparte tus datos con nadie.

Las propias prácticas de privacidad de la red están regidas por sus políticas publicadas, disponibles para ti cuando conectas cada institución.

## Dónde viven tus datos

| Qué | Dónde |
|---|---|
| Transacciones, cuentas, presupuestos, metas, detección de recurrencias | Almacén local SwiftData en tu dispositivo + **tu iCloud personal** (cifrado, tu Apple ID) |
| Tokens de acceso a la red financiera | Cifrados en reposo en nuestro backend + en el Llavero (Keychain) del dispositivo |
| Estado de suscripción | Verificado localmente vía Apple StoreKit 2 + cruce contra servidor |
| Tokens de push | Tabla del backend indexada por tu identificador opaco de Apple ID |
| Preferencias de la app (categorías, moneda, tema) | Local + iCloud Key-Value Store |

La sincronización de iCloud usa **tu** Apple ID. Nosotros nunca vemos, accedemos ni tenemos forma de recuperar los datos sincronizados por iCloud. Apple los cifra en tránsito y en reposo. Si borras la app y eliminas los datos de iCloud, esa copia desaparece — y no hay otra copia en ningún servidor que controlemos, salvo los tokens de acceso bancario (que solo sirven para volver a traer transacciones nuevas y se revocan en el momento en que desconectas un banco).

## Apple Intelligence (IA en el dispositivo)

Cuando tu dispositivo lo soporta, Khazen usa **Apple Intelligence (FoundationModels)** para generar perspectivas financieras, categorizar transacciones y escribir resúmenes.

Este modelo corre **completamente en tu dispositivo**. Tus transacciones, saldos y contexto personal nunca salen de tu iPhone, iPad o Mac para el procesamiento de IA. No enviamos tus datos a OpenAI, Anthropic, Google ni a ningún servicio de IA de terceros. Tampoco tenemos un servidor de IA propio.

Apple Intelligence requiere iOS 26+ y un dispositivo reciente. En dispositivos sin Apple Intelligence, las funciones de IA de Khazen se ocultan silenciosamente y el resto de la app funciona normal.

## Suscripción y compras

Las suscripciones se procesan vía **Apple StoreKit 2**. Recibimos solo:

- Un booleano: este Apple ID tiene una suscripción activa (vía `Transaction.currentEntitlements`)
- El producto actual (plan mensual o anual)
- Las fechas de renovación y revocación (para honrar cancelaciones y reembolsos rápidamente)

**No** vemos tu nombre, método de pago, dirección de facturación ni ningún otro metadato de compra. Apple maneja todo eso. Los reembolsos y la gestión de la suscripción pasan directamente por Apple (Ajustes → Apple ID → Suscripciones).

Prueba gratuita: siete días, sin cargos automáticos durante la prueba. Te enviamos notificaciones locales antes de que termine la prueba para que no haya renovaciones sorpresa.

## Notificaciones y correo

- **Notificaciones push**: opt-in. Si las habilitas, tu dispositivo recibe un token de Apple Push Notification que guardamos asociado a tu identificador opaco de Apple ID. Las notificaciones se limitan estrictamente a lo que actives en la app (alertas de presupuesto, saldo bajo, etc.). No enviamos pushes de marketing.
- **Correo**: si nos escribes a cualquier dirección `@khassinx.com`, recibimos tu mensaje y tu dirección de respuesta vía nuestro proveedor de correo. Conservamos esa correspondencia para manejar la conversación y los seguimientos. No te agregamos a ninguna lista. Khazen no tiene lista de correo.

## Privacidad de menores

Khazen está dirigida a usuarios **de 13 años o más** (clasificación del App Store en consecuencia). No recopilamos a sabiendas datos de menores de 13 años. Si crees que un menor de 13 ha usado Khazen, escríbenos a hello@khassinx.com y eliminaremos sin demora cualquier dato asociado.

## Tus derechos

Tienes derecho a:

- **Acceder** a tus datos — visibles en la app en todo momento. Exportación disponible desde Ajustes en la app.
- **Borrar** tu cuenta — un solo toque desde Ajustes → Cuenta → Borrar cuenta en la app. Esto elimina tus datos de nuestro backend (tokens de banco, tokens de push, cruce de suscripción) en minutos y es verificable. Los datos sincronizados por iCloud se eliminan automáticamente cuando borras la app y limpias sus datos de iCloud en tu Apple ID.
- **Desconectar** conexiones bancarias individuales cuando quieras, sin borrar tu cuenta.
- **Oponerte** a cualquier procesamiento — escríbenos a hello@khassinx.com.
- **Portabilidad** — exporta tus transacciones y cuentas desde Ajustes en la app (formato CSV).

Para usuarios en la **Unión Europea (RGPD)** y **California (CCPA)**: tienes los derechos adicionales que esas regulaciones confieren. Escríbenos a hello@khassinx.com para ejercerlos.

## Etiquetas de Privacidad de Apple

En la ficha del App Store, Khazen declara las categorías alineadas con esta política:

- **Información financiera**: recopilada — vinculada a ti, usada para la funcionalidad de la app
- **Identificadores (User ID)**: recopilados — vinculados a ti, usados para la funcionalidad de la app
- **Otro contenido del usuario**: recopilado — vinculado a ti, usado para la funcionalidad de la app (notas que agregas a transacciones)
- Las demás categorías: no recopiladas

Esto se verifica contra el manifiesto `PrivacyInfo.xcprivacy` y contra el código real (sin SDKs de analytics, sin trackers de terceros, sin frameworks publicitarios).

## Seguridad

- Todo el tráfico usa **TLS 1.2+**.
- Los tokens de acceso bancario están cifrados en reposo en nuestro backend.
- El acceso al backend está limitado al mínimo de permisos necesarios y protegido por Apple App Attest — las peticiones que no provengan de la app legítima de Khazen son rechazadas.
- La sincronización de iCloud usa el cifrado de extremo a extremo de Apple cuando tienes activada la Protección de Datos Avanzada.

Para reportar una vulnerabilidad, mira nuestra política de [Seguridad y divulgación responsable](/es/security/).

## Transferencias internacionales

El backend de Khazen opera en Estados Unidos. Si usas Khazen fuera de EE. UU., tus tokens de acceso bancario y otros registros del backend pueden procesarse en Estados Unidos. No transferimos tus datos a ningún otro país para su procesamiento.

## Cambios a esta política

Podemos actualizar esta política cuando:

- Se agregan funciones que cambian materialmente el manejo de datos
- Cambian las políticas del App Store de Apple
- Se corrigen errores legales o de hecho

Los cambios materiales se reflejarán con una nueva "Fecha de vigencia" arriba y se mostrará un aviso en la app al siguiente arranque.

## Notificación de incidentes

Ante una vulneración de datos confirmada que afecte tus datos personales:

- Notificaremos a la autoridad de protección de datos correspondiente dentro de las **72 horas** de confirmar el incidente, cuando lo exija la legislación aplicable (incluyendo el Art. 33 del RGPD para residentes en la UE).
- Notificaremos a los usuarios afectados **sin demora injustificada** mediante una alerta en la app al siguiente arranque y, si tenemos un correo registrado, por correo electrónico.
- Publicaremos un post-mortem público en este sitio en `/security/incidents/` una vez completada la mitigación.

Hasta la fecha no hemos sufrido ninguna vulneración. Este compromiso establece el proceso por si ocurre.

## Jurisdicción

Esta política se rige por las leyes del lugar de registro del operador en los Estados Unidos. Las disputas se resuelven bajo esas leyes.

## Contacto

Si tienes alguna duda o inquietud sobre privacidad:

- **Correo**: hello@khassinx.com
- **Postal**: Disponible por escrito a través del correo electrónico

Buscamos responder en siete días hábiles.

---

*Última actualización: 2026-05-26 · Versión 1.0*
