# 🚛 Plataforma de Controle de Jornada - Revenda Lima

Sistema completo para controle de jornada dos motoristas da Revenda Lima, incluindo registro de viagens, controle de horários, geração de relatórios em PDF e sistema de assinatura digital.

## ✨ Funcionalidades Principais

### 🚗 Para Motoristas
- **Registro de Jornada**: Formulário completo com todos os campos necessários
- **Controle de Horários**: Saída da empresa, chegada na fábrica, refeição/descanso
- **Tempo de Espera**: Registro opcional de tempo de espera na fábrica
- **Cálculo Automático**: Tempo total da jornada, KM total, médias
- **Histórico**: Visualização de todas as jornadas realizadas
- **Estatísticas**: Resumo mensal e geral das atividades
- **Perfil**: Gerenciamento de informações pessoais e profissionais

### 👨‍💼 Para Administradores
- **Dashboard**: Visão geral com estatísticas em tempo real
- **Gestão de Jornadas**: Visualização e gerenciamento de todas as jornadas
- **Gestão de Motoristas**: Cadastro e controle de motoristas
- **Relatórios em PDF**: Geração de documentos para impressão
- **Estatísticas Avançadas**: Análises por período, motorista e veículo
- **Sistema de Usuários**: Criação e gerenciamento de contas

### 📋 Campos do Controle de Jornada
- **Dados do Motorista**: Nome, placa do veículo
- **Dados da Viagem**: KM inicial, KM final, destino
- **Horários**: Saída da empresa, chegada na fábrica
- **Refeição/Descanso**: Início e fim com cálculo automático
- **Tempo de Espera**: Opcional com início e fim
- **Cálculos**: Tempo total da jornada, KM total
- **Observações**: Campo para anotações importantes
- **Data**: Data da jornada sendo registrada
- **Assinaturas**: Digital do motorista e gerente
- **Declaração**: "Por ser verdade firmo o presente, Rio Verde-Go, data"

## 🚀 Instalação e Configuração

### Pré-requisitos
- Node.js 16+ 
- npm ou yarn
- Navegador moderno (Chrome, Firefox, Safari, Edge)

### 1. Clone o repositório
```bash
git clone <url-do-repositorio>
cd plataforma-jornada-motoristas
```

### 2. Instale as dependências
```bash
npm install
```

### 3. Configure as variáveis de ambiente
Crie um arquivo `.env` na raiz do projeto:
```env
PORT=3001
JWT_SECRET=sua-chave-secreta-aqui
NODE_ENV=development
```

### 4. Inicie o servidor
```bash
# Modo desenvolvimento (com auto-reload)
npm run dev

# Modo produção
npm start
```

### 5. Acesse a aplicação
Abra seu navegador e acesse: `http://localhost:3001`

## 🔐 Usuários Padrão

### Administrador
- **Usuário**: `admin`
- **Senha**: `admin123`
- **Função**: Acesso completo ao sistema

### Motorista de Exemplo
- **Usuário**: `motorista1`
- **Senha**: `motorista123`
- **Função**: Acesso às funcionalidades de motorista
- **Placa**: `ABC-1234`

## 📱 Como Usar

### 🚗 Motoristas

#### 1. Login
- Acesse a plataforma
- Clique em "Entrar"
- Use suas credenciais de motorista

#### 2. Nova Jornada
- Clique em "Nova Jornada" no menu lateral
- Preencha todos os campos obrigatórios:
  - Dados do motorista e veículo
  - KM inicial e final
  - Destino da viagem
  - Horários de saída e chegada
  - Tempo de refeição (opcional)
  - Tempo de espera (se houver)
  - Observações importantes
- Clique em "Salvar Jornada"

#### 3. Visualizar Histórico
- Clique em "Minhas Jornadas"
- Veja todas as jornadas realizadas
- Filtre por data e status

#### 4. Estatísticas
- Clique em "Estatísticas"
- Visualize resumo mensal e geral
- Acompanhe KM total e tempo trabalhado

### 👨‍💼 Administradores

#### 1. Dashboard
- Visão geral das estatísticas
- Total de jornadas, KM e horas
- Estatísticas por motorista

#### 2. Gestão de Jornadas
- Visualize todas as jornadas
- Filtre por motorista, data e status
- Gere PDFs individuais

#### 3. Relatórios
- Relatórios consolidados por período
- Estatísticas detalhadas
- Exportação em PDF

#### 4. Gestão de Usuários
- Crie novos motoristas e administradores
- Gerencie perfis e permissões

## 🛠️ Tecnologias Utilizadas

### Backend
- **Node.js**: Runtime JavaScript
- **Express**: Framework web
- **JWT**: Autenticação e autorização
- **PDFKit**: Geração de relatórios em PDF
- **Moment.js**: Manipulação de datas e horários
- **bcryptjs**: Criptografia de senhas

### Frontend
- **HTML5**: Estrutura da aplicação
- **CSS3**: Estilização moderna e responsiva
- **JavaScript ES6+**: Lógica da aplicação
- **Bootstrap 5**: Framework CSS responsivo
- **Font Awesome**: Ícones

### Banco de Dados
- **SQLite**: Banco de dados local (pode ser migrado para MySQL/PostgreSQL)

## 📁 Estrutura do Projeto

```
plataforma-jornada-motoristas/
├── public/                 # Frontend estático
│   ├── index.html         # Página principal
│   ├── styles.css         # Estilos CSS
│   └── app.js            # Lógica JavaScript
├── routes/                # Rotas da API
│   ├── auth.js           # Autenticação
│   ├── jornada.js        # Controle de jornada
│   ├── motorista.js      # Gestão de motoristas
│   └── admin.js          # Funcionalidades administrativas
├── models/                # Modelos de dados
├── middleware/            # Middlewares
├── utils/                 # Utilitários
├── server.js             # Servidor principal
├── package.json          # Dependências
└── README.md             # Documentação
```

## 🔧 Configurações Avançadas

### Banco de Dados
Por padrão, o sistema usa SQLite em memória. Para usar um banco persistente:

1. Instale o driver do banco desejado:
```bash
npm install mysql2    # Para MySQL
npm install pg        # Para PostgreSQL
```

2. Configure as variáveis de ambiente:
```env
DB_TYPE=mysql
DB_HOST=localhost
DB_USER=usuario
DB_PASS=senha
DB_NAME=revenda_lima
```

### Segurança
- **JWT**: Tokens com expiração configurável
- **bcrypt**: Senhas criptografadas
- **Helmet**: Headers de segurança
- **CORS**: Controle de acesso cross-origin

### Produção
Para deploy em produção:

1. Configure variáveis de ambiente
2. Use HTTPS
3. Configure proxy reverso (nginx/Apache)
4. Use PM2 para gerenciamento de processos
5. Configure logs e monitoramento

## 📊 API Endpoints

### Autenticação
- `POST /api/auth/login` - Login de usuário
- `GET /api/auth/verify` - Verificar token
- `POST /api/auth/register` - Criar novo usuário

### Jornadas
- `POST /api/jornada` - Criar nova jornada
- `GET /api/jornada/:id` - Obter jornada específica
- `PUT /api/jornada/:id` - Atualizar jornada
- `DELETE /api/jornada/:id` - Deletar jornada
- `GET /api/jornada/motorista/:id` - Jornadas do motorista

### Administração
- `GET /api/admin/jornadas` - Listar todas as jornadas
- `GET /api/admin/jornada/:id/pdf` - Gerar PDF da jornada
- `POST /api/admin/relatorio-consolidado/pdf` - Relatório consolidado
- `GET /api/admin/estatisticas` - Estatísticas gerais

### Motoristas
- `GET /api/motorista/perfil/:id` - Perfil do motorista
- `PUT /api/motorista/perfil/:id` - Atualizar perfil
- `GET /api/motorista/:id/historico` - Histórico de jornadas

## 🐛 Solução de Problemas

### Erro de Conexão
- Verifique se o servidor está rodando
- Confirme a porta configurada
- Verifique as configurações de CORS

### Erro de Autenticação
- Verifique se o token está válido
- Confirme as credenciais do usuário
- Verifique a configuração do JWT_SECRET

### Erro ao Gerar PDF
- Verifique se o PDFKit está instalado
- Confirme as permissões de escrita
- Verifique se os dados estão completos

## 🤝 Contribuição

1. Faça um fork do projeto
2. Crie uma branch para sua feature
3. Commit suas mudanças
4. Push para a branch
5. Abra um Pull Request

## 📄 Licença

Este projeto está sob a licença MIT. Veja o arquivo `LICENSE` para mais detalhes.

## 📞 Suporte

Para suporte técnico ou dúvidas:
- **Email**: suporte@revendalima.com
- **Telefone**: (64) 99999-9999
- **Horário**: Segunda a Sexta, 8h às 18h

## 🔄 Atualizações

### Versão 1.0.0
- ✅ Sistema básico de controle de jornada
- ✅ Formulários completos com validação
- ✅ Geração de relatórios em PDF
- ✅ Sistema de autenticação JWT
- ✅ Interface responsiva e moderna
- ✅ Dashboard administrativo
- ✅ Estatísticas e relatórios

### Próximas Versões
- 🔄 Sistema de assinatura digital
- 🔄 App mobile para motoristas
- 🔄 Integração com GPS
- 🔄 Notificações push
- 🔄 Backup automático
- 🔄 Relatórios avançados

---

**Revenda Lima** - Sistema de Controle de Jornada © 2024
