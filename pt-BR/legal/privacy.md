---
layout: prose
title: Política de Privacidade
permalink: /pt-BR/legal/privacy/
lang: pt-BR
canonical_en: /legal/privacy/
canonical_es: /es/legal/privacy/
canonical_pt-BR: /pt-BR/legal/privacy/
redirect_from:
  - /pt-BR/privacidade
  - /pt-BR/privacidade/
updated: 2026-05-26
---

# Política de Privacidade — Khazen

**Data de vigência**: 2026-05-26
**App**: Khazen ([App Store](https://apps.apple.com/app/khazen/id6761610239))
**Desenvolvedor**: KhassinX
**Contato**: hello@khassinx.com

---

## Resumo

O Khazen é um app de finanças pessoais. Para funcionar, ele se conecta às suas contas bancárias e armazena transações nos seus dispositivos e no seu iCloud pessoal. Não vendemos, compartilhamos nem monetizamos seus dados financeiros. Não rodamos publicidade, analytics nem rastreamento. Nosso backend existe apenas para retransmitir as conexões bancárias — ele nunca alimenta um perfil publicitário sobre você.

Você pode desconectar qualquer banco a qualquer momento. Pode excluir sua conta com um toque e tudo o que temos sobre você é removido.

---

## Mapa rápido do que é coletado

| Categoria | Coletado? | Para quê |
|---|---|---|
| Dados de conta bancária (saldos, transações, nomes das contas) | ✅ Sim | Para o app mostrar seu dinheiro |
| Identificador de Apple ID (opaco, para sincronização) | ✅ Sim | Sincronizar entre seus dispositivos via iCloud |
| E-mail | Apenas se você nos escrever | Responder sua mensagem |
| Status da assinatura | ✅ Sim (via Apple) | Verificar acesso aos recursos pagos |
| Token de notificações push do dispositivo | ✅ Sim | Enviar apenas as notificações que você habilita |
| Relatórios de falhas | ❌ Não | Não coletamos crash reports |
| Analytics de uso | ❌ Não | Zero SDKs de analytics |
| Identificadores de publicidade (IDFA) | ❌ Não | Não usamos |
| Localização | ❌ Não | Não pedimos nem usamos |
| Contatos / Fotos / Microfone / Câmera | ❌ Não | O Khazen não acessa isso |

O manifesto `PrivacyInfo.xcprivacy` do app declara as mesmas categorias. A Apple verifica isso durante a revisão.

## Conexões bancárias

Para mostrar suas transações, o Khazen se conecta às suas instituições financeiras por uma **rede regulada de dados financeiros** amplamente usada por bancos e fintechs nos EUA. Essa rede:

- Autentica **diretamente com seu banco** usando os padrões do seu banco (OAuth quando o banco suporta, ou o fluxo seguro da rede caso contrário). O Khazen nunca vê suas credenciais bancárias.
- Devolve tokens de acesso de curta duração, criptografados em trânsito e em repouso.
- Respeita as desconexões imediatamente — quando você remove um banco no Khazen, o token de acesso é revogado.

Atuamos como um **canal de passagem**. Seus dados bancários fluem do seu banco para a rede, depois para nosso backend e depois para seu dispositivo. Nosso backend não enriquece seus dados com conjuntos de terceiros, não constrói perfil publicitário, não compartilha seus dados com ninguém.

As práticas de privacidade da própria rede são regidas pelas políticas publicadas por ela, disponíveis quando você conecta cada instituição.

## Onde seus dados ficam

| O quê | Onde |
|---|---|
| Transações, contas, orçamentos, metas, detecção de recorrências | Armazenamento local SwiftData no dispositivo + **seu iCloud pessoal** (criptografado, seu Apple ID) |
| Tokens de acesso à rede financeira | Criptografados em repouso no nosso backend + no Chaveiro (Keychain) do dispositivo |
| Status da assinatura | Verificado localmente via Apple StoreKit 2 + checagem cruzada no servidor |
| Tokens de push | Tabela do backend indexada pelo seu identificador opaco de Apple ID |
| Preferências do app (categorias, moeda, tema) | Local + iCloud Key-Value Store |

A sincronização do iCloud usa o **seu** Apple ID. Nunca vemos, acessamos nem temos como recuperar os dados sincronizados pelo iCloud. A Apple os criptografa em trânsito e em repouso. Se você apaga o app e remove os dados do iCloud, essa cópia desaparece — e não há outra cópia em nenhum servidor que controlemos, exceto os tokens de acesso bancário (que servem apenas para buscar novas transações e são revogados no instante em que você desconecta um banco).

## Apple Intelligence (IA no dispositivo)

Quando seu dispositivo suporta, o Khazen usa **Apple Intelligence (FoundationModels)** para gerar análises financeiras, categorizar transações e escrever resumos.

Esse modelo roda **inteiramente no seu dispositivo**. Suas transações, saldos e contexto pessoal nunca saem do iPhone, iPad ou Mac para inferência de IA. Não enviamos seus dados para OpenAI, Anthropic, Google nem nenhum serviço de IA de terceiros. Também não temos um servidor de IA próprio.

A Apple Intelligence exige iOS 26+ e um dispositivo recente. Em dispositivos sem Apple Intelligence, os recursos de IA do Khazen ficam ocultos silenciosamente e o resto do app funciona normal.

## Assistentes externos de IA com sua própria chave (opcional)

O Khazen permite conectar opcionalmente assistentes externos — Claude, ChatGPT ou Gemini — usando **suas próprias chaves de API**.

Quando você ativa isso:

- Sua chave de API fica salva apenas no Chaveiro (Keychain) do iOS no seu dispositivo. Nós nunca recebemos.
- As requisições vão **direto do seu dispositivo para o provedor escolhido** (Anthropic, OpenAI ou Google). Elas não passam pelo nosso backend.
- Os dados que você envia para esses provedores são regidos pelas **políticas de privacidade deles** e por quaisquer termos vinculados à sua conta de API.
- Você pode desativar os assistentes externos quando quiser. A desativação interrompe as requisições e remove a chave do Chaveiro.

Você decide qual provedor — se algum — vê seus dados fora do modelo da Apple no dispositivo.

## Assinatura e compras

As assinaturas são processadas via **Apple StoreKit 2**. Recebemos apenas:

- Um booleano: este Apple ID tem assinatura ativa (via `Transaction.currentEntitlements`)
- O produto atual (plano mensal ou anual)
- As datas de renovação e revogação (para honrar cancelamentos e reembolsos rapidamente)

**Não** vemos seu nome, método de pagamento, endereço de cobrança nem qualquer outro metadado de compra. A Apple cuida disso tudo. Os reembolsos e o gerenciamento da assinatura passam diretamente pela Apple (Ajustes → Apple ID → Assinaturas).

Período de teste grátis: sete dias, sem cobrança automática durante o teste. Enviamos notificações locais antes de o teste terminar para não haver renovações surpresa.

## Notificações e e-mail

- **Notificações push**: opt-in. Se você habilitar, seu dispositivo recebe um token do Apple Push Notification que armazenamos vinculado ao seu identificador opaco de Apple ID. As notificações ficam estritamente no que você ativa no app (alertas de orçamento, saldo baixo etc.). Não enviamos push de marketing.
- **E-mail**: se você nos escrever em qualquer endereço `@khassinx.com`, recebemos sua mensagem e o endereço de resposta pelo nosso provedor de e-mail. Mantemos essa correspondência para conduzir a conversa e os próximos passos. Não adicionamos você a nenhuma lista. O Khazen não tem lista de e-mail.

## Privacidade de menores

O Khazen é destinado a usuários **com 13 anos ou mais** (classificação da App Store de acordo). Não coletamos conscientemente dados de menores de 13 anos. Se você acredita que um menor de 13 usou o Khazen, escreva para hello@khassinx.com e removeremos sem demora qualquer dado associado.

## Seus direitos

Você tem direito a:

- **Acessar** seus dados — visíveis no app o tempo todo. Exportação disponível pelos Ajustes no app.
- **Excluir** sua conta — um toque pelos Ajustes → Conta → Excluir conta no app. Isso remove seus dados do nosso backend (tokens bancários, tokens de push, checagem cruzada de assinatura) em minutos e é verificável. Os dados sincronizados pelo iCloud são removidos automaticamente quando você apaga o app e limpa os dados do iCloud no seu Apple ID.
- **Desconectar** conexões bancárias individuais quando quiser, sem excluir sua conta.
- **Opor-se** a qualquer processamento — escreva para hello@khassinx.com.
- **Portabilidade** — exporte suas transações e contas pelos Ajustes no app (formato CSV).

Para usuários no **Brasil (LGPD)**, na **União Europeia (RGPD)** e na **Califórnia (CCPA)**: você tem os direitos adicionais conferidos por essas regulamentações. Escreva para hello@khassinx.com para exercê-los.

## Etiquetas de Privacidade da Apple

Na ficha da App Store, o Khazen declara as categorias alinhadas com esta política:

- **Informação financeira**: coletada — vinculada a você, usada para a funcionalidade do app
- **Identificadores (User ID)**: coletados — vinculados a você, usados para a funcionalidade do app
- **Outro conteúdo do usuário**: coletado — vinculado a você, usado para a funcionalidade do app (notas que você adiciona às transações)
- Demais categorias: não coletadas

Isso é verificado contra o manifesto `PrivacyInfo.xcprivacy` no app e contra o código real (sem SDKs de analytics, sem rastreadores de terceiros, sem frameworks publicitários).

## Segurança

- Todo o tráfego usa **TLS 1.2+**.
- Os tokens de acesso bancário ficam criptografados em repouso no nosso backend.
- O acesso ao backend está limitado ao mínimo de permissões necessárias e protegido pelo Apple App Attest — requisições que não venham do app Khazen legítimo são rejeitadas.
- A sincronização do iCloud usa a criptografia de ponta a ponta da Apple quando você tem a Proteção de Dados Avançada ativada.

Para reportar uma vulnerabilidade, veja nossa política de [Segurança e divulgação responsável](/pt-BR/security/).

## Transferências internacionais

O backend do Khazen opera nos Estados Unidos. Se você usa o Khazen fora dos EUA, seus tokens de acesso bancário e outros registros do backend podem ser processados nos Estados Unidos. Não transferimos seus dados para nenhum outro país para processamento.

## Mudanças nesta política

Podemos atualizar esta política quando:

- Adicionarmos recursos que mudem materialmente o tratamento de dados
- Houver mudanças nas políticas da App Store da Apple
- Corrigirmos erros jurídicos ou de fato

Mudanças materiais serão refletidas com uma nova "Data de vigência" no topo e um aviso aparecerá no app no próximo abrir.

## Notificação de incidentes

Diante de uma violação de dados confirmada que afete seus dados pessoais, vamos:

- Notificar a autoridade de proteção de dados competente em até **72 horas** após confirmar o incidente, quando exigido pela legislação aplicável (incluindo o Art. 33 do RGPD para residentes na UE e a LGPD no Brasil).
- Notificar os usuários afetados **sem atraso indevido** por meio de um alerta no app no próximo abrir e, se tivermos um e-mail registrado, por e-mail.
- Publicar um post-mortem público neste site em `/security/incidents/` assim que a mitigação for concluída.

Até a data, não sofremos nenhuma violação. Este compromisso estabelece o processo caso aconteça.

## Jurisdição

Esta política é regida pelas leis do **Estado da Flórida, EUA**. As disputas são resolvidas nos tribunais do Estado da Flórida.

## Contato

Se você tem dúvidas ou preocupações sobre privacidade:

- **E-mail**: hello@khassinx.com
- **Postal**: Disponível por escrito por e-mail

Buscamos responder em sete dias úteis.

---

*Última atualização: 2026-05-26 · Versão 1.0*
