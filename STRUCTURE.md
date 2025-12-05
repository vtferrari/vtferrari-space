# Estrutura do Projeto - Jekyll Resume

## 📁 Estrutura de Arquivos

```
vtferrari-space/
│
├── _config.yml              # Configuração do Jekyll
├── Gemfile                  # Dependências Ruby
├── index.html               # Página principal
├── README.md                # Documentação geral
├── DEPLOYMENT.md            # Guia de deploy no GitHub Pages
├── STRUCTURE.md             # Este arquivo (estrutura do projeto)
│
├── _data/
│   └── resume.yml          # Dados do currículo em YAML
│
├── _layouts/
│   └── resume.html         # Template HTML do currículo
│
├── assets/
│   └── css/
│       └── style.css       # Estilos CSS
│
├── cursor/                  # Pasta com arquivos originais
│   ├── curriculum.md       # Currículo original em Markdown
│   ├── Resume Vinicius Ferrari - ENG.docx
│   └── Resume Vinicius Ferrari - ENG.pdf
│
└── .gitignore              # Arquivos ignorados pelo Git

```

## 📝 Arquivos Principais

### 1. `_config.yml`
Configuração do Jekyll com informações do site:
- Título do site
- Descrição
- URL base
- Plugins necessários

### 2. `_data/resume.yml`
Todos os dados do currículo estruturados em YAML:
- ✅ Informações pessoais
- ✅ About/Brief
- ✅ Experiências profissionais (7 posições)
- ✅ Skills (categorizado por tipo)
- ✅ Educação
- ✅ Cursos adicionais

### 3. `_layouts/resume.html`
Template HTML que renderiza o currículo:
- Header com nome e contato
- Seção About
- Experiências profissionais
- Skills organizadas
- Educação
- Cursos

### 4. `assets/css/style.css`
Estilos modernos e responsivos:
- Design limpo e profissional
- Otimizado para impressão
- Responsivo (mobile-friendly)
- Cores neutras e profissionais

### 5. `index.html`
Página inicial que usa o layout resume

## 🚀 Como Usar

### Testar Localmente

```bash
# 1. Instalar dependências
bundle install

# 2. Rodar servidor Jekyll
bundle exec jekyll serve

# 3. Abrir no navegador
# http://localhost:4000
```

### Publicar no GitHub Pages

1. Criar repositório no GitHub
2. Push do código
3. Ativar GitHub Pages nas configurações
4. Aguardar deploy automático

Ver detalhes completos em `DEPLOYMENT.md`

## ✏️ Como Editar o Currículo

### Editar informações pessoais
Arquivo: `_data/resume.yml`
```yaml
name: Seu Nome
title: Seu Cargo
email: seu@email.com
...
```

### Adicionar nova experiência
Arquivo: `_data/resume.yml`, na seção `experience:`
```yaml
- company: Nome da Empresa
  position: Seu Cargo
  start_date: "Mês Ano"
  end_date: "Mês Ano"
  description: |
    Descrição do que você fez...
```

### Adicionar nova skill
Arquivo: `_data/resume.yml`, na seção `skills:`
```yaml
skills:
  categoria:
    - "Skill 1"
    - "Skill 2"
```

### Modificar estilos
Arquivo: `assets/css/style.css`
- Alterar cores, fontes, espaçamentos, etc.

## 🎨 Personalização Avançada

### Mudar cores
Em `assets/css/style.css`, procure e altere:
```css
color: #2c3e50;  /* Cor principal dos títulos */
color: #3498db;  /* Cor dos links */
color: #7f8c8d;  /* Cor secundária */
```

### Adicionar nova seção
1. Adicionar dados em `_data/resume.yml`
2. Adicionar HTML em `_layouts/resume.html`
3. Adicionar estilos em `assets/css/style.css`

### Mudar layout
Edite `_layouts/resume.html` para reorganizar as seções

## 📱 Recursos

- ✅ Responsivo (mobile, tablet, desktop)
- ✅ Otimizado para impressão
- ✅ SEO friendly
- ✅ Acessível
- ✅ Rápido carregamento
- ✅ Fácil manutenção

## 🔗 Links Úteis

- [Jekyll Documentation](https://jekyllrb.com/docs/)
- [GitHub Pages Docs](https://docs.github.com/en/pages)
- [YAML Syntax](https://yaml.org/)
- [Liquid Template Language](https://shopify.github.io/liquid/)

## 📄 Licença

Baseado no Jekyll Resume Template por jglovier.

