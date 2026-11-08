# Norte — suas finanças, seu próximo destino

Aplicação web estática para finanças pessoais, contas a pagar, múltiplos bancos, cartões, fontes de receita e metas de viagem/estudos no exterior. Feita em **HTML5, CSS moderno (com utilitários compilados do Tailwind CSS 4) e JavaScript Vanilla**, sem backend, banco de dados externo ou login.

## Iniciar em poucos segundos

1. Agora o arquivo `index.html` é autossuficiente: contém os estilos e o código JavaScript completos. Você pode abrir o `Norte-Financas-Abrir-Direto.html` sem instalar nada, mesmo sem as pastas `assets` ou `icons`. Para publicar no GitHub Pages, extraia o ZIP e mantenha os arquivos e pastas no repositório.
2. Para instalar como aplicativo (PWA) e ativar o cache offline, publique via HTTPS. Você pode usar GitHub Pages.
3. Na primeira vez, cadastre uma conta e seu saldo inicial; depois registre entradas, despesas, transferências, contas recorrentes e metas. Em **Configurações → Testar exemplo** há dados fictícios opcionais para explorar o painel.

## Publicar no GitHub Pages

1. Crie um repositório no [GitHub](https://github.com/new), por exemplo `norte-financas` (público para Pages no plano gratuito).
2. Extraia o arquivo ZIP deste projeto no computador. **Envie os arquivos e as pastas diretamente para a raiz do repositório**: `index.html`, `sw.js`, `manifest.webmanifest`, `assets/`, `icons/` e `README.md`. **Não envie a pasta `norte-financas` por fora**, senão você poderá ver erro 404 na URL principal.
3. Faça commit dos arquivos.
4. No repositório, entre em **Settings → Pages → Build and deployment → Deploy from a branch**; selecione `main`, a pasta `/ (root)` e **Save**.
5. Abra o endereço informado pelo GitHub Pages, geralmente `https://SEU-USUARIO.github.io/norte-financas/`.
6. No iPhone, abra o link pelo **Safari → Compartilhar → Adicionar à Tela de Início**. No Android, use a opção **Instalar app** do navegador compatível.

## O que já funciona

- Dashboard: patrimônio líquido (bancos + investimentos − cartões), entradas, saídas e resultado do mês; gráficos de 6 meses e distribuição de gastos.
- Contas: corrente, poupança, investimentos, espécie e cartão de crédito. O saldo é calculado a partir do saldo inicial + movimentações.
- Lançamentos: receitas e despesas com data, descrição, conta e categoria; edição, exclusão, filtros e CSV.
- Transferências: inclusive pagamento de cartão, sem criar receita/despesa artificial.
- Contas a pagar: regras mensais ou únicas, vencimentos, status pendente/atrasada/paga e despesas geradas quando o pagamento é confirmado.
- Fontes de renda: recorrentes/variáveis, com receita consolidada a partir de lançamentos reais.
- Metas: CHF/EUR/USD/BRL, câmbio **manual**, data-limite, progresso, reservas e aporte recomendado/mês. Permite múltiplos objetivos e histórico de aportes.
- Backup JSON, importação, dados de exemplo e opção de apagar dados.
- PWA instalável; cache offline após o primeiro carregamento por HTTPS e navegador compatível.

## Importante: segurança, saldos e dados

**Os dados são salvos localmente no navegador via `localStorage`, por origem (site e dispositivo).** Publicar o site não disponibiliza seus saldos para outras pessoas, mas também **não cria sincronização entre computador e iPhone**. Para mudar de dispositivo, use **Configurações → Baixar backup** e depois **Importar JSON** no outro dispositivo. Não armazene dados sensíveis como senhas e números completos de cartão. Pessoas com acesso ao navegador/dispositivo podem acessar os dados locais; backups JSON não são criptografados.

O app não acessa bancos, não lê extratos automaticamente e não oferece atualização automática de câmbio. O valor da dívida de cartões é estimado; parcelamentos, juros e ajustes exigem lançamento manual. A data da fatura mostrada é uma estimativa por fechamento e vencimento.

**Cuidados para evitar duplicação:** defina o saldo inicial uma vez e, dali em diante, registre **somente movimentações novas**. Marcar conta como paga cria uma despesa automaticamente. Transferir valores para uma poupança não é despesa; pagar uma fatura é uma transferência da conta corrente para o cartão, e não uma nova despesa (a compra no cartão já foi despesa). Aportes em metas indicam reserva de valores e não debitam contas.

O cálculo da meta considera **um aporte no mês atual e um em cada mês seguinte, inclusive no mês do prazo**. Para uma programação mais precisa no dia, ajuste a data-limite e o aporte mensal planejado; o método é intencionalmente mensal, não diário.

## Arquivos

- `index.html`: versão autossuficiente, com HTML, CSS e JavaScript incorporados; não depende das pastas para abrir a interface.
- `assets/styles.css`: cópia separada do design system e dos componentes responsivos (referência e manutenção).
- `assets/tailwind.css`: utilitários Tailwind pré-compilados (não exige npm nem CDN).
- `assets/app.js`: cópia separada da lógica e armazenamento (referência e manutenção).
- `sw.js`, `manifest.webmanifest`, `icons/`: cache offline e instalação.

## Evoluções possíveis

Se quiser sincronizar entre aparelhos no futuro, será necessário introduzir autenticação, banco de dados e regras de acesso (por exemplo, Supabase/Firebase); **isso não faz parte desta versão estática**.

Uso pessoal, sem necessidade de instalação de dependências.
