🧠 QuickStudy AI - Microaprendizagem Inteligente
O QuickStudy AI é uma plataforma Fullstack de aprendizado acelerado. O sistema permite que os usuários gerem aulas estruturadas e narrações em áudio sobre qualquer tema, utilizando o poder de orquestração de IA do Dify.ai.

🚀 Tecnologias Utilizadas
Essencial
Front-end: Next.js 14(Roteador de Aplicativos), React, TailwindCSS.

Backend: Node.jscomFastify(Foco em desempenho).

Motor IA: Dify.ai(Orquestração de LLMs e Workflows).

Banco de Dados: PostgreSQLviaPrisma ORM.

Segurança e Qualidade
Autenticação: JWT (JSON Web Tokens) e Bcrypt para hash de senhas.

Validação: Zod(Validação de esquema em tempo de execução).

Dica: TypeScript (modo estrito).



quickstudy-ai/
├── backend/                 # API Server (Fastify + Prisma)
│   ├── prisma/              # Configuração do Banco de Dados
│   │   └── schema.prisma    # Modelagem de dados (Users, Studies)
│   ├── src/
│   │   ├── @types/          # Tipagens globais do TypeScript
│   │   ├── controllers/     # Orquestradores de requisições (req/res)
│   │   ├── lib/             # Instâncias de serviços (Prisma, Dify Client)
│   │   ├── routes/          # Definição dos endpoints (URLs)
│   │   ├── schemas/         # Validações de entrada (Zod Schemas)
│   │   ├── services/        # Regras de negócio e integração com Dify
│   │   ├── app.ts           # Configuração de plugins e middlewares
│   │   └── server.ts        # Ponto de entrada do servidor
│   ├── .env                 # Variáveis de ambiente (DB_URL, JWT_SECRET)
│   └── tsconfig.json        # Configurações do compilador TS
│


├── frontend/                # Interface Web & PWA (Next.js)
│   ├── public/              # Assets estáticos e Manifest do PWA
│   ├── src/
│   │   ├── app/             # Rotas e Páginas (Next.js App Router)
│   │   ├── components/      # Componentes UI (Botões, Cards, Player)
│   │   ├── hooks/           # Lógica de estado e consumo de API (TanStack Query)
│   │   └── services/        # Configuração do Axios/API Client
│   └── tailwind.config.js   # Estilização do sistema
│



├── ai-engine/               # Infraestrutura de Inteligência Artificial
│   └── dify/                # Self-hosted Dify (via Docker)
│
└── docker-compose.yml       # Orquestração de containers (Postgres, Redis, Dify)

🏗️ Arquitetura do Sistema
O projeto segue os princípios da Arquitetura Limpa , separando responsabilidades para facilitar a manutenção e escalabilidade:

Cliente (PWA): Uma interface Next.js otimizada para dispositivos móveis, permitindo "instalar" o aplicativo no celular.

Servidor (API): Servidor Fastify que gerencia regras de negócio, autenticação e comunicação segura com o banco.

Dify Workflow: A lógica da IA ​​não é "hardcoded", mas sim em um workflow visual no Dify, facilitando o ajuste de prompts sem mexer no código.

🛠️ Como executar o projeto
Pré-requisitos
Docker e Docker Compose instalados.

Node.js v20 ou superior.

1. Clonar e Instalar
Bash
git clone https://github.com/seu-usuario/quickstudy-ai.git
cd quickstudy-ai
2. Configurar o Ambiente (Docker)
O projeto utiliza Docker para subir o banco de dados e o motor do Dify:

Bash
docker-compose up -d
3. Configurar o Backend
Bash
cd backend
npm install
# Configure o seu .env com a DATABASE_URL e DIFY_API_KEY
npx prisma migrate dev
npm run dev
4. Configurar o Frontend
Bash
cd ../frontend
npm install
npm run dev
📝 Funcionalidades Planejadas
[x] Cadastro e Login de usuários com JWT.

[x] Integração com API do Dify para geração de conteúdo.

[ ] Geração de áudio (TTS) para cada aula resumida.

[ ] Modo Offline (PWA) para leitura de aulas salvas.

[ ] Painel de progresso de estudos.

🎨 Protótipo e Design
A interface foi pensada para ser minimalista, focando no conteúdo gerado pela IA, utilizando Shadcn/UI para componentes de alta qualidade.

👨‍💻 Autor
Desenvolvido por Mateus – Um entusiasta de IA e desenvolvimento Fullstack.
