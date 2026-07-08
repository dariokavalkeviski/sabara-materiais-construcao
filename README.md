# Materiais de Construção Sabará — Landing Page

Landing page institucional para a **Materiais de Construção Sabará**, loja de materiais de construção em Ponta Grossa - PR. Site single-page, responsivo, com foco em geração de contato via WhatsApp.

🔗 **Demo:** _adicione aqui o link do GitHub Pages / Vercel / Netlify quando publicar_

## Funcionalidades

- Seções: Home, Sobre, Produtos, Diferenciais, Galeria, Marcas parceiras, Depoimentos, Formulário de orçamento, Contato/Mapa
- Formulário de orçamento que monta a mensagem e abre direto no WhatsApp
- Botão flutuante de WhatsApp e telefone/endereço clicáveis (`tel:` e Google Maps)
- Badge dinâmico de **Aberto agora / Fechado agora** calculado a partir do horário de funcionamento
- Menu mobile acessível (`aria-expanded`, fecha com Esc ou clique fora)
- Destaque automático do item ativo no menu conforme o scroll
- Galeria com lightbox (fotos reais quando disponíveis, placeholder honesto quando não)
- SEO local: meta tags Open Graph e dados estruturados (JSON-LD `HardwareStore`) com endereço, telefone e horários
- Mapa incorporado do Google Maps

## Tecnologias

- HTML5 + [Tailwind CSS](https://tailwindcss.com/) via CDN
- [Lucide Icons](https://lucide.dev/) via CDN
- Google Fonts (Bebas Neue + Work Sans)
- JavaScript puro (sem frameworks, sem build step)

## Estrutura

```
├── index.html        # página completa (markup, estilos e scripts)
└── Assets/
    └── logo.jpg       # logo da loja
```

## Como rodar localmente

Não há build nem dependências para instalar — é um HTML estático. Basta abrir o arquivo direto no navegador:

```bash
# opção 1: abrir diretamente
open index.html          # macOS
start index.html         # Windows

# opção 2: servir com um servidor local (recomendado, evita problemas de CORS/cache)
npx serve .
# ou
python -m http.server 8000
```

## Personalização

Os principais dados do negócio (título, subtítulo, WhatsApp, endereço, telefone) ficam centralizados no objeto `defaultConfig`, no `<script>` final do `index.html`:

```js
const defaultConfig = {
  hero_title: 'TUDO PARA SUA OBRA DO INÍCIO AO ACABAMENTO',
  hero_subtitle: '...',
  whatsapp_number: '5542999414645',
  address: 'R. Avelino Pereira de Campos, 839<br>Chapada, Ponta Grossa - PR, 84062-290',
  phone: '(42) 3227-0498',
  ...
};
```

Produtos, diferenciais, galeria, marcas e depoimentos são arrays de dados logo abaixo desse objeto — para editar o conteúdo, basta alterar os itens desses arrays.

## Pendências conhecidas

- Galeria: apenas 1 foto real (fachada). As demais estão marcadas como "Foto em breve" até que fotos reais da loja sejam adicionadas.
- Depoimentos são placeholders de exemplo — substituir por avaliações reais dos clientes antes de publicar.
- Tailwind é carregado via CDN (JIT no navegador); para produção em maior escala, considerar migrar para um build compilado.

## Contato da loja

- 📍 R. Avelino Pereira de Campos, 839 - Chapada, Ponta Grossa - PR
- 📞 (42) 3227-0498 / (42) 99941-4645
- [Instagram](https://www.instagram.com/mcsabara/) · [Facebook](https://www.facebook.com/mcsabarapg/)
