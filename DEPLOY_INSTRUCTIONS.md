
# 📋 Instruções de Deploy - Fluxo da Moda Landing Page

## 🚀 Como fazer o deploy da Landing Page no Hostinger

### Pré-requisitos
- Conta na Hostinger
- Domínio configurado (fluxodamoda.com)
- Node.js 18+ instalado localmente

### Opção 1: Deploy automático via GitHub + Hostinger

1. **Criar repositório no GitHub:**
   ```bash
   git init
   git add .
   git commit -m "Initial commit - Fluxo da Moda Landing"
   git branch -M main
   git remote add origin https://github.com/SEU_USUARIO/fluxo-da-moda-landing.git
   git push -u origin main
   ```

2. **Configurar no Hostinger:**
   - Acesse hPanel → Website → Manage
   - Vá em "Git" ou "GitHub Deployment"
   - Conecte seu repositório GitHub
   - Configure:
     - **Branch:** main
     - **Build command:** `npm run build`
     - **Publish directory:** `dist`
     - **Node version:** 18+

3. **Deploy automático:**
   - Qualquer push para `main` fará deploy automático
   - Logs disponíveis no painel da Hostinger

### Opção 2: Deploy manual via File Manager

1. **Build local:**
   ```bash
   npm install
   npm run build
   ```

2. **Upload via File Manager:**
   - Acesse hPanel → File Manager
   - Navegue para `public_html/`
   - Exclua arquivos existentes (se houver)
   - Faça upload de todos os arquivos da pasta `dist/`
   - Certifique-se de que `.htaccess` está no diretório raiz

### Opção 3: Deploy via FTP

1. **Build local:**
   ```bash
   npm install
   npm run build
   ```

2. **Configurar FTP:**
   - Host: seu-dominio.com
   - Usuário: seu-usuario-ftp
   - Senha: sua-senha-ftp
   - Porta: 21

3. **Upload via FTP:**
   - Conecte via FileZilla ou similar
   - Navegue para `/public_html/`
   - Faça upload de todos os arquivos da pasta `dist/`

## 🌐 Configuração do Domínio

### DNS Configuration
```
Tipo: A
Nome: @
Valor: IP do servidor Hostinger
TTL: 3600

Tipo: CNAME
Nome: www
Valor: fluxodamoda.com
TTL: 3600
```

### SSL Configuration
- Vá em hPanel → SSL/TLS
- Ative "Force HTTPS Redirect"
- Certifique-se de que o certificado está ativo

## 🔧 Configurações importantes

### Arquivo .htaccess (já incluído)
```apache
# Apache configuration for Hostinger
RewriteEngine On

# Handle React Routes
RewriteBase /
RewriteRule ^index\.html$ - [L]
RewriteCond %{REQUEST_FILENAME} !-f
RewriteCond %{REQUEST_FILENAME} !-d
RewriteRule . /index.html [L]

# Redirect HTTP to HTTPS
RewriteCond %{HTTPS} off
RewriteRule ^(.*)$ https://%{HTTP_HOST}%{REQUEST_URI} [L,R=301]

# Cache static assets
<IfModule mod_expires.c>
    ExpiresActive on
    ExpiresByType text/css "access plus 1 year"
    ExpiresByType application/javascript "access plus 1 year"
    ExpiresByType image/png "access plus 1 year"
    ExpiresByType image/jpg "access plus 1 year"
    ExpiresByType image/jpeg "access plus 1 year"
</IfModule>

# Gzip compression
<IfModule mod_deflate.c>
    AddOutputFilterByType DEFLATE text/plain
    AddOutputFilterByType DEFLATE text/html
    AddOutputFilterByType DEFLATE text/xml
    AddOutputFilterByType DEFLATE text/css
    AddOutputFilterByType DEFLATE application/xml
    AddOutputFilterByType DEFLATE application/xhtml+xml
    AddOutputFilterByType DEFLATE application/rss+xml
    AddOutputFilterByType DEFLATE application/javascript
    AddOutputFilterByType DEFLATE application/x-javascript
</IfModule>

# Security headers
<IfModule mod_headers.c>
    Header always set X-Content-Type-Options nosniff
    Header always set X-Frame-Options DENY
    Header always set X-XSS-Protection "1; mode=block"
</IfModule>
```

## 📱 Teste pós-deploy

### Checklist de funcionalidades
- [ ] Página carrega corretamente
- [ ] Navegação smooth entre seções funciona
- [ ] Botões de planos redirecionam para Stripe
- [ ] Links do WhatsApp abrem corretamente
- [ ] Calculadora interativa funciona
- [ ] Design responsivo no mobile
- [ ] SSL ativo (https://)
- [ ] Redirecionamentos funcionando

### Teste de performance
- [ ] Velocidade de carregamento < 3s
- [ ] Imagens otimizadas
- [ ] Cache configurado
- [ ] Compressão ativa

### Teste de SEO
- [ ] Meta tags corretas
- [ ] Open Graph funcionando
- [ ] Schema.org implementado
- [ ] Canonical URL configurada

## 🌐 URLs importantes

- **Produção:** https://fluxodamoda.com
- **Checkout Mensal:** https://buy.stripe.com/7sY5kD0zA9YMcIJaDc8N202
- **Checkout Anual:** https://buy.stripe.com/9B66oHgyyb2Q5ghdPo8N200
- **WhatsApp:** https://wa.me/5511999999999

## 📞 Configurações de contato

### WhatsApp
- Número: `5511999999999`
- Mensagem padrão: "Olá! Tenho interesse no Fluxo da Moda..."

### Email
- Suporte: suporte@fluxodamoda.com
- Comercial: comercial@fluxodamoda.com

## 🔄 Atualizações futuras

### Via GitHub (automático)
1. Fazer alterações no código
2. Commit e push para `main`
3. Deploy automático via Hostinger

### Via FTP (manual)
1. Fazer alterações locais
2. Executar `npm run build`
3. Upload da pasta `dist/` via FTP

## 🛠️ Troubleshooting

### Problema: Página não carrega
- Verifique se `.htaccess` está no diretório raiz
- Confirme se SSL está ativo
- Teste em modo privado do navegador

### Problema: Imagens não aparecem
- Verifique se estão na pasta `public/`
- Confirme os caminhos nas imagens
- Teste permissions dos arquivos

### Problema: Redirects não funcionam
- Verifique configuração do `.htaccess`
- Teste se mod_rewrite está ativo
- Confirme se não há conflitos

## 📊 Monitoramento

### Métricas importantes
- Tempo de carregamento
- Taxa de conversão
- Cliques nos botões de planos
- Interações com WhatsApp

### Ferramentas recomendadas
- Google Analytics
- Google Search Console
- PageSpeed Insights
- GTmetrix

---

**Importante:** Sempre teste em ambiente de desenvolvimento antes de fazer deploy em produção.

**Suporte:** Para problemas técnicos, consulte a documentação da Hostinger ou entre em contato com o suporte.
