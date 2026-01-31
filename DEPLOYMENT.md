# Guia de Deploy no GitHub Pages

## Pré-requisitos
- Conta no GitHub
- Git instalado localmente

## Passos para publicar seu currículo no GitHub Pages

### 1. Criar Repositório no GitHub

Opção A - Para usar como página principal do usuário:
- Crie um repositório com o nome: `seu-usuario.github.io`
- Seu currículo ficará em: `https://seu-usuario.github.io/`

Opção B - Para usar como página de projeto:
- Crie um repositório com qualquer nome (ex: `resume`, `cv`, etc.)
- Seu currículo ficará em: `https://seu-usuario.github.io/nome-do-repo/`

### 2. Configurar Git localmente

```bash
# Inicializar repositório Git (se ainda não foi feito)
git init

# Adicionar todos os arquivos
git add .

# Fazer o primeiro commit
git commit -m "Initial commit: Jekyll resume setup"

# Conectar com o repositório remoto
git remote add origin https://github.com/seu-usuario/nome-do-repo.git

# Enviar para o GitHub
git branch -M main
git push -u origin main
```

### 3. Ativar GitHub Pages

1. Acesse o repositório no GitHub
2. Vá em **Settings** (Configurações)
3. No menu lateral, clique em **Pages**
4. Em **Source**, selecione:
   - Branch: `main` (ou `master`)
   - Folder: `/ (root)`
5. Clique em **Save**

### 4. Aguardar o deploy

- O GitHub levará alguns minutos para processar e publicar
- Você receberá uma notificação quando estiver pronto
- Acesse a URL fornecida para ver seu currículo online

### 5. Atualizações futuras

Para atualizar seu currículo:

```bash
# Edite os arquivos necessários (principalmente _data/resume.yml)
# Adicione as mudanças
git add .

# Faça commit
git commit -m "Update resume"

# Envie para o GitHub
git push
```

O GitHub Pages atualizará automaticamente em alguns minutos.

## Personalização adicional

### Usar domínio personalizado

#### Passo 1: Configurar no GitHub
1. Acesse o repositório no GitHub
2. Vá em **Settings** → **Pages** (menu "Code and automation")
3. Em **Custom domain**, digite seu domínio (ex: `vtferrari.space`)
4. Clique em **Save** (isso cria/atualiza o arquivo CNAME no repositório)
5. Aguarde a verificação DNS (pode levar alguns minutos)
6. Marque **Enforce HTTPS** quando a opção ficar disponível (pode levar até 24h)

#### Passo 2: Configurar DNS no provedor do domínio

**Para domínio apex** (ex: `vtferrari.space` - sem www):
- Crie **4 registros A** apontando para os IPs do GitHub Pages:
  ```
  185.199.108.153
  185.199.109.153
  185.199.110.153
  185.199.111.153
  ```
- Ou use **1 registro ALIAS/ANAME** apontando para `seu-usuario.github.io`

**Para subdomínio www** (ex: `www.vtferrari.space`):
- Crie um **registro CNAME** apontando para `seu-usuario.github.io`

#### Solução de problemas (erro ERR_CERT_COMMON_NAME_INVALID)
- **Remover e readicionar o domínio**: Em Settings → Pages, clique em **Remove** no domínio, depois adicione novamente e clique **Save** para reativar o provisionamento do certificado
- **Aguardar propagação**: Pode levar até 24h para o certificado HTTPS ficar disponível
- **Cloudflare**: Se usar proxy (nuvem laranja), considere usar "DNS only" (nuvem cinza) temporariamente para testar

### Ajustar baseurl para repositório de projeto

Se estiver usando um repositório de projeto (não `usuario.github.io`), 
edite `_config.yml` e adicione:

```yaml
baseurl: "/nome-do-repo"
```

## Testar localmente antes de publicar

### Opção 1: Com Docker (recomendado)

```bash
# Subir o servidor Jekyll (requer Docker instalado)
docker compose up

# Acessar em http://localhost:4000
```

O LiveReload está habilitado - alterações nos arquivos atualizam o navegador automaticamente.

### Opção 2: Com Ruby/Bundler

```bash
# Instalar dependências
bundle install

# Rodar servidor local
bundle exec jekyll serve

# Acessar em http://localhost:4000
```

## Solução de problemas

### Site não carrega no GitHub Pages

1. Verifique se o GitHub Pages está ativado nas configurações
2. Verifique se o branch correto está selecionado
3. Aguarde alguns minutos - o primeiro deploy pode demorar

### Estilos não aparecem

1. Verifique o `baseurl` no `_config.yml`
2. Limpe o cache do navegador
3. Verifique se o caminho dos assets está correto

### Erro de build

1. Verifique o email do GitHub para ver mensagens de erro
2. Teste localmente com `bundle exec jekyll serve`
3. Verifique se não há erros de sintaxe no YAML

## Links úteis

- [Documentação GitHub Pages](https://docs.github.com/en/pages)
- [Documentação Jekyll](https://jekyllrb.com/docs/)
- [Jekyll Themes](https://jekyllthemes.io/)

