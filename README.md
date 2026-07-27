# SEAD Apps

Coleção de utilitários web independentes, cada um em um único arquivo `index.html` autocontido (HTML + CSS + JS), sem necessidade de backend, build ou instalação de dependências via `npm`. Basta abrir o arquivo no navegador.

## Estrutura do repositório

```
sead-apps/
└── sead-apps/
    ├── qr-code-studio/
    │   └── index.html
    └── shrink-local/
        └── index.html
```

> **Nota:** existe uma pasta `sead-apps/` duplicada dentro do repositório (`sead-apps/sead-apps/...`), provavelmente resultado do upload inicial dos arquivos. Os aplicativos funcionam normalmente, mas veja a seção [Problemas encontrados](#problemas-encontrados-na-revisão) para uma sugestão de correção.

---

## 📱 QR Code Studio

Gerador de QR Codes personalizável, **100% offline** (a biblioteca de geração de QR fica embutida no próprio HTML, nenhuma dependência externa é carregada).

**Local:** [`sead-apps/qr-code-studio/index.html`](sead-apps/qr-code-studio/index.html)

### Funcionalidades

- Geração de QR Code para 5 tipos de conteúdo:
  - Texto / Link
  - Wi-Fi (SSID, senha, tipo de segurança, rede oculta)
  - Contato (VCard)
  - E-mail (destinatário, assunto, corpo)
  - SMS (número, mensagem)
- Personalização visual: cor de primeiro plano, cor de fundo, paletas prontas (presets), margem interna (padding) e nível de correção de erro (L/M/Q/H)
- Upload de logo central com ajuste de tamanho (força automaticamente correção de erro alta quando há logo)
- Ajuste de resolução de saída (150–600 px)
- Ações: baixar como PNG, copiar imagem para a área de transferência, salvar no histórico local
- Histórico local persistido em `localStorage` (até 20 itens), com opção de recarregar ou excluir cada item
- Interface 100% em português (pt-BR), tema escuro (glassmorphism)

### Tecnologia

- HTML + CSS + JavaScript puro (vanilla), sem frameworks
- [QRious v4.0.2](https://github.com/neocotic/qrious) embutida diretamente no arquivo (minificada), garantindo funcionamento 100% offline após o primeiro carregamento
- Sem dependências externas de rede

### Como usar

Basta abrir o arquivo `index.html` diretamente no navegador (duplo clique ou `file://`).

---

## 📄 ShrinkLocal

Suíte de compactação e mesclagem de PDFs e imagens, processada inteiramente no navegador do usuário (client-side) — nenhum arquivo é enviado a servidores.

**Local:** [`sead-apps/shrink-local/index.html`](sead-apps/shrink-local/index.html)

### Funcionalidades

**Compactar documentos**
- Aceita PDF, JPG/JPEG e PNG (arraste e solte ou seleção manual)
- Presets de compactação: Máxima Nitidez, Equilibrado, Tamanho Mínimo e Personalizado
- Controles individuais: qualidade JPEG/PNG, resolução máxima (largura), fator de resolução (DPI) para renderização de PDF, qualidade de compressão de PDF
- Fila de arquivos com status (pendente / processando / concluído / falha), percentual de redução por arquivo e resumo total de economia
- Download individual ou de todos os arquivos compactados

**Juntar documentos**
- Mescla múltiplos PDFs e imagens (JPG/PNG) em um único PDF
- Reordenação manual da fila (mover para cima/baixo)
- Imagens são ajustadas proporcionalmente em páginas A4
- Nome de arquivo final configurável

### Tecnologia

- HTML + Tailwind CSS (via CDN) + FontAwesome (via CDN)
- [PDF-Lib](https://pdf-lib.js.org/) para criação/mesclagem de PDFs
- [PDF.js](https://mozilla.github.io/pdf.js/) para renderização de páginas de PDF em canvas
- JavaScript puro (vanilla), sem framework de frontend

### Como usar

Abra o arquivo `index.html` no navegador. **Requer conexão com a internet no primeiro carregamento**, pois Tailwind, FontAwesome, PDF-Lib e PDF.js são carregados via CDN (ver observação abaixo).

---

## Problemas encontrados na revisão

Veja a resposta no chat para a lista completa e priorizada de problemas identificados no código, com sugestões de correção.
