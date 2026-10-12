# Gestão Empresarial - ERP para Pequeno Varejo

> Sistema completo de gestão desenvolvido para fazer um comércio real faturar mais. Foco em margem, giro de estoque e tomada de decisão com dados - não só cadastro.

🔗 **Demo ao vivo:** https://eduardoagram-br.github.io/Gestaoempresarial/
📦 **Repositório:** `eduardoagram-Br/Gestaoempresarial`
👨‍💻 **Autor:** Eduardo Agra Messas - Eng. de Produção | Pós em Eng. de Segurança do Trabalho | Niterói - RJ

---

### O que é

Sistema 100% offline, roda no navegador, sem backend, sem mensalidade. Criado para a realidade de um comércio que já vende bem mas não sabe quanto lucra, o que repor e quem são os melhores clientes.

Salva tudo no `localStorage` do navegador. Dados exportáveis em JSON e Excel.

### Funcionalidades implementadas

#### 📊 Painel
- **Hoje:** pedidos, unidades vendidas, faturamento e lucro do dia
- **Este mês:** mesmos indicadores acumulados
- Margem de lucro do mês
- Top 4 produtos mais vendidos e top 4 melhores clientes

#### 👥 Clientes
- Cadastro completo (nome, telefone com máscara, e-mail, endereço, observações)
- Busca, impressão da lista
- Estatísticas por cliente: total de compras, total gasto, ticket médio, lucro gerado, última compra
- Histórico de compras com link para notinha
- Top 3 produtos mais comprados por cliente

#### 🏷️ Precificação (Engenharia de Produto)
**Aba Ingredientes:**
- Cadastro de matéria-prima: quantidade comprada, unidade (kg, g, L, ml, un), preço pago
- Cálculo automático de custo por unidade
- Validade

**Aba Produtos:**
- Receita com composição de ingredientes (quantidade por rendimento)
- Custo de ingredientes, embalagem, mão de obra e outros
- Margem desejada -> preço sugerido automático
- Preço praticado editável
- Ficha técnica: tempo de preparo, conservação, modo de preparo passo a passo
- **Informação nutricional opcional:** porção, porções por embalagem, kcal, carboidratos, açúcares, proteínas, gorduras, fibra, sódio
- Impressão: ficha técnica, tabela nutricional padrão ANVISA (mercado) e etiqueta bonita com logo do negócio

> Atualizar preço de ingrediente recalcula todos os produtos automaticamente.

#### 📦 Estoque
- Produtos prontos e matéria-prima separados
- Estoque atual vs estoque mínimo desejado
- Alerta visual de itens abaixo do mínimo (o que comprar/produzir)
- Ajuste manual de entrada/saída (+10, -5)
- Registro de produção: informa quanto vai produzir, abate matéria-prima e soma no produto final
- Impressão: posição de estoque e ficha de contagem para conferência física

#### 🛒 Nova Venda / Pedidos
- Seleção de cliente cadastrado ou avulso
- Itens com produto, qtd, preço e custo unitário
- Adição rápida de itens vindos da Precificação (puxa preço e custo calculados)
- Desconto, taxa, forma de pagamento (Dinheiro, PIX, Débito, Crédito...), canal (WhatsApp, iFood, Venda direta...)
- Status: Pendente, Em produção, Pronto, Entregue, Pago, Cancelado
- Cálculo em tempo real: subtotal, total, custo, lucro
- Ao salvar: baixa estoque automaticamente e incrementa número do pedido

**Notinha:**
- Recibo interno (não fiscal) em A4/PDF
- Impressão térmica 58mm (impressora de cupom)
- Compartilhar texto ou enviar no WhatsApp
- Opção de mostrar custo e lucro (uso interno)

#### 💸 Custos
**Fixos recorrentes:** cadastra uma vez (aluguel, funcionários, internet). Conta proporcional ao período automaticamente. Pode pausar.

**Variáveis:** lança por data e categoria (Ingredientes, Embalagens, Gás, Energia, Transporte, Taxas de cartão/delivery, Impostos, Marketing, etc). Filtro por período (hoje, semana, mês, mês anterior, personalizado).

Visão de total do período e distribuição por categoria.

#### 📈 Resultado do Mês (DRE Simplificada)
- Faturamento bruto, descontos, receita de vendas
- Custo de produção, taxas, custos variáveis, custos fixos
- Lucro líquido e margem líquida
- Não substitui contabilidade oficial - foco gerencial.

#### 🏆 Rankings
- Produtos: ordenação por quantidade, lucro ou faturamento
- Clientes: por faturamento, nº de compras ou compra mais recente

#### 🥊 Concorrentes
- Cadastro de concorrentes (nome, local, obs)
- Itens do concorrente com preço e data de coleta
- Vinculação com seu produto para comparativo
- Tela de comparativo: seu preço vs média da concorrência, diferença em R$ e %

#### 📉 Gráficos (Chart.js)
- Filtro 3/6/12 meses
- Faturamento, lucro, custos e nº de pedidos por mês
- Produtos mais vendidos (qtd) e mais lucrativos

#### 🧾 Planilhas
- **Controle de caixa semanal:** modelo em Excel (.xlsx) com fórmulas (total vendido, diferença) e versão para impressão/PDF. 5 semanas prontas.
- **Controle de estoque:** Excel com abas Produtos e Matéria-prima, já preenchido com estoque atual do sistema, colunas para contagem manual e diferença automática.

#### 💾 Backup
- Exportar backup .json com tudo (clientes, vendas, custos, ingredientes, produtos, config)
- Restaurar em qualquer dispositivo/navegador
- Aviso claro de que dados ficam só no navegador local

#### ⚙️ Configurações
- Nome do negócio (aparece em recibos, impressões e ícone do app)
- Moeda: BRL, USD, EUR, ARS, MZN
- Idioma: pt/en (formato de data)
- Acessibilidade: tamanho do texto (Normal, Grande, Extra Grande) via zoom e alto contraste
- PWA: manifest e ícones gerados dinamicamente com iniciais do negócio - instalável no celular como app

### Tecnologias
- HTML5, CSS3, JavaScript vanilla (SPA single-file)
- `Chart.js 4.4.4` - gráficos
- `SheetJS (xlsx 0.18.5)` - exportação Excel
- `localStorage` - persistência
- `GitHub Pages` - hospedagem
- Impressão: `@media print` + layout térmico 58mm

Sem build, sem npm. Um único `index.html`.

### Como rodar local
```bash
git clone https://github.com/eduardoagram-Br/Gestaoempresarial.git
# abra index.html no navegador
```
Ou acesse direto: https://eduardoagram-br.github.io/Gestaoempresarial/

### Próximos passos sugeridos (para faturar mais)
- [ ] Ponto de equilíbrio diário (quanto precisa vender para não ter prejuízo)
- [ ] Alerta de produto Curva A parado há X dias
- [ ] Exportação de relatório DRE para Excel
- [ ] Cadastro de fornecedores e cotação

### Autor
Desenvolvido por Eduardo Agra Messas para aplicação real em pequeno comércio da família. Projeto de portfólio de Eng. de Produção aplicando PCP, Curva ABC, precificação e gestão de custos com tecnologia de baixo custo.

LinkedIn: https://www.linkedin.com/in/eduardo-agra-messas-a0980273/
GitHub: https://github.com/eduardoagram-Br

---
> Este sistema é um comprovante interno de gestão e não substitui emissão fiscal, contabilidade ou responsabilidade técnica.
