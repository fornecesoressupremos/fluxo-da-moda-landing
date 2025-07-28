
# Fluxo da Moda - Landing Page

Landing page standalone do Fluxo da Moda para deploy independente.

## 🚀 Como fazer deploy

### Pré-requisitos
- Node.js 18+
- npm ou yarn

### Desenvolvimento local
```bash
npm install
npm run dev
```

### Build para produção
```bash
npm run build
```

### Preview da build
```bash
npm run preview
```

## 📦 Deploy no Hostinger

### Opção 1: Deploy automático via GitHub
1. Conecte seu repositório GitHub à Hostinger
2. Configure:
   - Build command: `npm run build`
   - Publish directory: `dist`
   - Node version: 18+

### Opção 2: Deploy manual via FTP
1. Execute `npm run build`
2. Faça upload dos arquivos da pasta `dist` para o diretório público do Hostinger
3. Certifique-se de que o `.htaccess` está no diretório raiz

### Opção 3: Deploy via File Manager
1. Execute `npm run build`
2. Compacte a pasta `dist` em um arquivo ZIP
3. Faça upload e extraia no File Manager da Hostinger

## 🌐 Configuração do domínio

### DNS no Hostinger
1. Aponte o domínio para os nameservers da Hostinger
2. Configure SSL automático
3. Teste os redirects

### Configurações importantes
- ✅ SSL habilitado
- ✅ Redirects HTTP → HTTPS
- ✅ Compressão Gzip
- ✅ Cache de assets

## 📱 Funcionalidades

- 📊 Seção Hero com video placeholder
- 🎯 Benefícios e checkpoints
- 💰 Como funciona (4 passos)
- 🎥 Demonstrações com videos do YouTube
- 🧮 Calculadora interativa de precificação
- 💳 Seção de planos (mensal/anual)
- 🗣️ Depoimentos de clientes
- 💬 Contato via WhatsApp
- 🛡️ Garantia de 30 dias
- ❓ FAQ completo
- 📱 Totalmente responsivo

## 🔧 Personalização

### Alterar URLs do Stripe
Edite o arquivo `src/components/landing/PricingSection.tsx`:
```typescript
const checkoutUrls = {
  monthly: 'SUA_URL_STRIPE_MENSAL',
  annual: 'SUA_URL_STRIPE_ANUAL'
};
```

### Alterar número do WhatsApp
Procure por `5511999999999` nos arquivos e substitua pelo número correto.

### Adicionar imagens
Coloque as imagens na pasta `public/` e referencie como `/nome-da-imagem.jpg`.

## 🎨 Tecnologias utilizadas

- ⚡ Vite
- ⚛️ React 18
- 🎨 Tailwind CSS
- 🧩 Radix UI
- 📱 Responsive Design
- 🔍 SEO otimizado

## 📊 Performance

- Bundle size otimizado
- Lazy loading de componentes
- Compressão de assets
- Cache headers configurados

## 🔒 Segurança

- Headers de segurança configurados
- SSL forçado
- XSS Protection
- Content Security Policy

## 📞 Suporte

Para dúvidas sobre o deploy ou configuração:
- Email: suporte@fluxodamoda.com
- WhatsApp: (11) 99999-9999
