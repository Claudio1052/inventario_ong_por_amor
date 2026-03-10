# 🏠 ONG Por Amor — Sistema de Inventário & Almoxarifado

Sistema completo de gestão de inventário e almoxarifado para a ONG Por Amor.

## 🚀 Como Usar

### 1. Configurar o Banco de Dados (Supabase)

1. Acesse [app.supabase.com](https://app.supabase.com)
2. Entre no seu projeto
3. Vá em **SQL Editor**
4. Copie e execute o conteúdo do arquivo `supabase_schema.sql`
5. Aguarde a confirmação "Success"

### 2. Login Padrão

- **Email:** `admin@ongporamor.org.br`
- **Senha:** `Admin@2024`

> ⚠️ **IMPORTANTE:** Altere a senha após o primeiro acesso!

---

## 🔐 Proteção de Dados Sensíveis para GitHub

Para proteger suas credenciais no GitHub, use um dos métodos abaixo:

### Método 1: Variáveis de Ambiente (Recomendado para deploy)

Se hospedar no GitHub Pages, Netlify, Vercel, etc:

```javascript
// Em vez de hardcode, use variáveis de ambiente:
const SUPABASE_URL = process.env.SUPABASE_URL;
const SUPABASE_KEY = process.env.SUPABASE_ANON_KEY;
```

Configure as variáveis em:
- **Netlify:** Site settings → Environment variables
- **Vercel:** Project settings → Environment Variables
- **GitHub Pages:** Use GitHub Secrets + GitHub Actions

### Método 2: Arquivo .env (para desenvolvimento local)

Crie um arquivo `.env` na raiz:
```
SUPABASE_URL=https://unidzfxifxjruonbjspe.supabase.co
SUPABASE_ANON_KEY=sua_chave_aqui
ADMIN_EMAIL=admin@ongporamor.org.br
```

Adicione ao `.gitignore`:
```
.env
.env.local
.env.production
config.js
secrets.js
```

### Método 3: Arquivo de Config Separado (para HTML puro)

Crie `config.js` (não commitado):
```javascript
window.APP_CONFIG = {
  supabaseUrl: 'https://unidzfxifxjruonbjspe.supabase.co',
  supabaseKey: 'sua_chave_aqui'
};
```

No HTML principal, carregue antes do script principal:
```html
<script src="config.js"></script>
```

**Importante:** Adicione `config.js` ao `.gitignore`

Crie um `config.example.js` como template:
```javascript
window.APP_CONFIG = {
  supabaseUrl: 'SEU_SUPABASE_URL',
  supabaseKey: 'SUA_SUPABASE_ANON_KEY'
};
```

---

## 📱 Funcionalidades

### 📦 Inventário
- Cadastro completo de itens com categoria, origem (doação/compra), estado de conservação
- Controle de quantidade total e disponível
- Localização no almoxarifado
- Número de série/patrimônio
- Valor estimado para controle patrimonial

### 🤝 Empréstimos
- Registro de saída de itens com responsável
- Data prevista de devolução
- Atualização automática do estoque ao emprestar/devolver
- Detecção automática de atrasos
- Comprovante imprimível

### 👥 Pessoas
- Cadastro de beneficiários, voluntários, funcionários e parceiros
- Histórico de empréstimos por pessoa

### 🗂️ Categorias
- Organização por categorias com cores personalizadas
- Contagem de itens por categoria

### 📊 Dashboard KPIs
- Total de itens e quantidades
- Empréstimos ativos e em atraso
- Patrimônio estimado total
- Gráficos de distribuição por categoria
- Gráfico doações vs compras
- Gráfico estado de conservação
- Alertas de itens em atraso

### 📋 Relatórios (Impressão)
- Relatório completo de inventário
- Empréstimos ativos
- Itens em atraso
- Relatório de patrimônio por categoria

---

## 🗄️ Estrutura do Banco de Dados

```
categorias      → Categorias de itens
itens           → Inventário completo
pessoas         → Cadastro de pessoas
emprestimos     → Cabeçalho dos empréstimos
emprestimo_itens → Itens de cada empréstimo
administradores → Usuários administradores
logs_acoes      → Auditoria de ações
```

---

## 🔧 Tecnologias

- **Frontend:** HTML5, CSS3 puro, JavaScript vanilla
- **Backend:** Supabase (PostgreSQL + REST API)
- **Gráficos:** Chart.js
- **Fontes:** Syne + DM Sans (Google Fonts)
- **Impressão:** Window.print() nativo do browser

---

## 📞 Suporte

Sistema desenvolvido para a **ONG Por Amor**.
Para dúvidas ou problemas, consulte a documentação do [Supabase](https://supabase.com/docs).
