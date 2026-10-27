# AtendeFácil

Sistema web de atendimento ao cliente para pequenas e médias empresas.

## Tecnologias
- **Frontend**: React, TypeScript, Vite, Tailwind CSS, React Router, Lucide icons
- **Backend**: Node.js, Express, TypeScript, Prisma ORM, PostgreSQL
- **Autenticação**: JSON Web Tokens (JWT) com hash de senhas Argon2id

## Estrutura do projeto
```
AtendeFacil/
├─ frontend/      # Aplicação React
├─ backend/       # API REST em Express
├─ docs/          # Documentação adicional
├─ .gitignore
├─ .env.example   # Variáveis de ambiente (sem valores reais)
└─ README.md
```

## Como iniciar localmente
1. **Pré-requisitos**
   - Node.js 20+ 
   - PostgreSQL 15+ 
   - Git
2. **Clonar o repositório**
   ```bash
   git clone https://github.com/iasmimmachado016-arch/AtendeFacil.git
   cd AtendeFacil
   ```
3. **Configurar variáveis de ambiente**
   ```bash
   cp .env.example .env
   # Edite .env com as credenciais do seu banco e secret JWT
   ```
4. **Instalar dependências**
   ```bash
   # Backend
   cd backend && npm install && cd ..
   # Frontend
   cd frontend && npm install && cd ..
   ```
5. **Executar migrations do Prisma**
   ```bash
   cd backend && npx prisma migrate dev --name init && cd ..
   ```
6. **Iniciar aplicações**
   - Backend: `cd backend && npm run dev`
   - Frontend: `cd frontend && npm run dev`

## Testes
```bash
cd backend && npm test
cd frontend && npm test
```

## Deploy
- **Frontend**: Vercel (variável `VITE_API_URL` apontando para o endpoint do backend)
- **Backend**: Render ou Railway (configurar variáveis de ambiente equivalentes)
- **Banco**: PostgreSQL gerenciado (ex.: Supabase, Railway)

## Criação do primeiro administrador
Após iniciar o backend, registre um usuário normalmente e depois, no banco, altere o campo `perfil` para `ADMIN` manualmente ou execute:
```sql
UPDATE "User" SET perfil = 'ADMIN' WHERE email = 'seu@email.com';
```

*Este documento será atualizado conforme o projeto evoluir.*
