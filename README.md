# Eduarda Prestes — Odontologia & Estética Facial

Site em React + Tailwind CSS, com build estático Vite e identidade marrom (#6B4F3A) e bege (#E8DDD0).

## Publicar pelo cPanel / HostGator

1. Abra a pasta `dist` deste projeto.
2. Envie **o conteúdo de dist**, incluindo `index.html`, `favicon.svg` e a pasta `assets`, para a pasta do domínio no cPanel (normalmente `public_html`). Não envie a pasta `dist` como uma subpasta, a menos que deseje esse endereço.
3. Abra o domínio para conferir. Nenhum servidor Node é necessário na hospedagem.

O build já está incluído. O site ainda não foi enviado à HostGator: faltam a conexão com a conta de hospedagem e os secrets de publicação.

## Editar e executar

Requer Node 22 ou superior.

```sh
npm ci
npm run dev
```

Gerar novamente a pasta de publicação após alterações:

```sh
npm run build
npm run preview
```

- Conteúdo e componentes: `src/main.jsx`.
- Visual, responsividade e animações: `src/style.css`.
- Tailwind: `tailwind.config.js`.
- Metadados: `index.html`.
- Base relativa: `vite.config.js` (`base: './'`).

## Publicação automática via GitHub

O arquivo `.github/workflows/deploy.yml` reproduz exatamente o workflow fornecido no briefing. Publique o projeto em um repositório GitHub e configure os secrets em Settings > Secrets and variables > Actions:

- `FTP_SERVER`
- `FTP_USERNAME`
- `FTP_PASSWORD`
- `FTP_PATH` (padrão `./`; a conta FTP deve estar restrita ao diretório deste site)

Um push na branch `main` compila o projeto e envia o build por FTPS. Não inclua senhas no código. O fluxo não foi executado contra uma conta real neste trabalho.

O site tem uma única página com navegação por âncoras, sem rotas SPA. Portanto não necessita regras de fallback para rotas em `.htaccess`.

## Conteúdo a completar

- O hero tem fundo gráfico provisório e indicação do espaço destinado à fotografia da clínica.
- A seção Sobre tem espaço descritivo para a fotografia real da Dra. Eduarda. Para substituir, use um `img` com `alt` descritivo, dimensões definidas e `loading="lazy"`; a imagem de abertura deve carregar sem lazy loading.
- A seção de experiências informa que os relatos serão disponibilizados. Não foram inventados depoimentos, pacientes, fotos, parceiros, números de atendimento ou anos de experiência.
- Confirme o e-mail `contato@gmail.com`, fornecido no briefing, antes de divulgar.
- Insira os dados profissionais e a identificação CRO fornecidos pela responsável na versão final.
- Ao definir o domínio e uma imagem de compartilhamento, acrescente URL canônica, `og:url` e `og:image` absolutas em `index.html`.

## Funcionalidades e verificações

Menu móvel expansível com fechamento por Escape; navegação por âncoras; FAQ expansível; WhatsApp com mensagens específicas por tratamento; Instagram; e-mail; mapa externo; foco visível; link de salto; redução de movimento respeitada.

Build de produção executado com sucesso; bundle minificado e caminhos relativos conferidos; renderização desktop e expansão do FAQ verificadas no navegador. Layout móvel definido por breakpoints, mas não verificado visualmente em dispositivo móvel. Acessibilidade preparada, sem auditoria formal completa WCAG.

Não há formulário, coleta local de dados, cookies de rastreamento ou analytics. Links externos abrem os serviços correspondentes.

## Atualização — 23/11/2026

Logo original aplicado no cabeçalho, rodapé, selo, espaço da seção Sobre e ícone da aba. Fundo creme e marrom harmonizados. A fotografia profissional segue pendente.

Mapa Google incorporado na localização confirmada (-29.2287235, -51.3484005), com link para a ficha da clínica. O iframe depende da conexão com o Google.

Três trechos reais de avaliações do Google incluídos com atribuição. Nota 5,0 e 16 avaliações verificadas em 23/11/2026, sem atualização automática. A seção informa a data da consulta. Os textos curtos são trechos, não avaliações integrais; o botão abre a ficha original.

A versão atual prevalece sobre as observações anteriores de depoimentos pendentes. Ainda não publicado na HostGator.
