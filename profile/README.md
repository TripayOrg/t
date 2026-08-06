# Welcome to Byko

Welcome to the official repository of **Byko**! This is your starting point to explore and contribute.

<img width="320" height="132" alt="Google workspace" src="https://github.com/user-attachments/assets/3f7186b0-61a2-4ff9-87e5-45cd2e3e349e" />

## Our Stack

**App**:
<a href="https://flutter.dev/" title="Flutter"><img src="https://github.com/get-icon/geticon/raw/master/icons/flutter.svg" alt="Flutter" width="21px" height="21px"></a>

**Backend**:
<a href="https://go.dev/" title="Go"><img src="https://github.com/get-icon/geticon/raw/master/icons/go.svg" alt="Go" width="21px" height="21px"></a>
<a href="https://www.python.org/" title="Python"><img src="https://github.com/get-icon/geticon/raw/master/icons/python.svg" alt="Python" width="21px" height="21px"></a>

**Site institucional**:
<a href="https://nodejs.org/" title="Node.js"><img src="https://github.com/get-icon/geticon/raw/master/icons/nodejs-icon.svg" alt="Node.js" width="21px" height="21px"></a>
<a href="https://www.typescriptlang.org/" title="Typescript"><img src="https://github.com/get-icon/geticon/raw/master/icons/typescript-icon.svg" alt="Typescript" width="21px" height="21px"></a>
<a href="https://reactjs.org/" title="React"><img src="https://github.com/get-icon/geticon/raw/master/icons/react.svg" alt="React" width="21px" height="21px"></a>
<a href="https://tailwindcss.com/" title="Tailwind CSS"><img src="https://github.com/get-icon/geticon/raw/master/icons/tailwindcss-icon.svg" alt="Tailwind CSS" width="21px" height="21px"></a>


## 💡 What is Byko?

Byko é uma plataforma que conecta, de forma simples e segura, quem precisa de um serviço a profissionais qualificados.

Cliente descreve o que precisa, um chat com IA ajuda a refinar o escopo do pedido, prestadores da categoria enviam propostas, e o cliente escolhe. Toda a negociação, o combinado e o pagamento (com repasse ao prestador) acontecem dentro da plataforma, substituindo o fluxo informal de indicação e contato direto por um processo digital, seguro e centralizado.

## 🧭 System design

```mermaid
flowchart LR
  App[biko-app] -->|GraphQL + JWT| API[biko-api]
  Site[landing-page] --> App
  API --> DB[(MongoDB)]
  API --> Cache[(Redis)]
  API --> Auth[Firebase Auth / FCM]
  API --> Files[Google Cloud Storage]
  API --> Pay[Asaas]
  API --> Mail[Resend + templates-email]
  API --> AI[ai-api FastAPI]
  AI --> Model[Vertex AI / Gemini]
  AI --> Trace[Langfuse]
```

- **biko-app** oferece as jornadas mobile de cliente e prestador.
- **biko-api** é o núcleo autoritativo: autenticação, domínio, persistência e integrações.
- **ai-api** refina solicitações de forma stateless; o histórico pertence à API.
- **landing-page** cuida da aquisição; **templates-email** compõe as comunicações transacionais.

A documentação detalhada, as fronteiras de cada serviço e o catálogo de recursos estão em [biko-co/documentation](https://github.com/biko-co/documentation).
