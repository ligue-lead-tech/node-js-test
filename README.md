# 🚀 Desafio Técnico — Node.js

## 🎯 Objetivo
Criar uma **API REST** em **Node.js** para gerenciar **projetos e tarefas**, incluindo:
- CRUD completo
- Integração com API externa
- Autenticação/autorização
- Boas práticas de arquitetura, segurança e performance

---

## 📋 Requisitos Funcionais

### 1. CRUD de Projetos
- `POST /projects` → Cria um projeto.
- `GET /projects` → Lista todos os projetos (com paginação).
- `GET /projects/:id` → Retorna dados do projeto (incluindo tarefas).
- `PUT /projects/:id` → Atualiza informações do projeto.
- `DELETE /projects/:id` → Remove um projeto.

### 2. CRUD de Tarefas
- `POST /projects/:projectId/tasks` → Cria tarefa vinculada a um projeto.
- `PUT /tasks/:id` → Atualiza status/título/descrição.
- `DELETE /tasks/:id` → Remove tarefa.

### 3. Integração Externa (GitHub)
- `GET /projects/:id/github/:username` → Busca os **5 últimos repositórios públicos** de um usuário no GitHub e vincula ao projeto (salvando no banco).
- API: `https://api.github.com/users/{username}/repos`

### 4. Autenticação e Autorização
- Cadastro (`POST /auth/register`) e login (`POST /auth/login`).
- Autenticação via **JWT**.
- Apenas usuários autenticados podem criar/editar/excluir projetos e tarefas.
- Apenas o **dono do projeto** pode editá-lo ou excluí-lo.

---

## 📦 Requisitos Técnicos
- **Node.js + Express** ou **Fastify**
- Banco de dados **MySQL**
- ORM: **Sequelize** ou **TypeORM** ou **Prisma**
- Arquitetura em camadas: `controllers → services → repositories`
- Tratamento global de erros com middleware
- Variáveis de ambiente com `.env`
- Testes automatizados com **Jest** (mínimo: autenticação, CRUD de projeto)
- Documentação detalhada no README
- Paginação e filtros no `GET /projects`
- Cache dos resultados da API do GitHub (Redis ou in-memory) por 10 minutos

---

## 🔒 Requisitos de Segurança
- Sanitização de inputs
- Configuração de CORS
- Hash de senhas com bcrypt

---

## 📑 Entrega
O candidato deve entregar:
1. **Repositório Git** com código e README contendo:
   - Instruções para rodar a API localmente
   - Variáveis de ambiente necessárias
   - Como rodar testes
2. Script `npm run seed` para popular o banco com dados de exemplo
3. Coleção do Postman ou arquivo `.http` para testar endpoints

---

## Diferenciais:
1. Dockerfile e docker-compose para subir API e banco
2. Uso de cache in memory ou Redis para guardar resultados da integração por 10 minutos

---

## 💡 Observações
- Sinta-se livre para usar bibliotecas que ajudem na produtividade, mas mantenha boas práticas.
- Organização e clareza do código serão avaliadas junto com a implementação das funcionalidades.
