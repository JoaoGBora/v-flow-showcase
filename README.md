# V-Flow — Plataforma de Operações Financeiras integrada ao ERP

> 🔒 Código privado (projeto corporativo). Esta página descreve o escopo e a arquitetura.

## Problema
O fluxo de caixa era montado manualmente em planilhas, a partir de relatórios exportados do ERP. Isso consumia horas por semana e as datas usadas nem sempre refletiam a realidade.

## Solução
Plataforma web que lê os títulos a pagar e a receber direto do **TOTVS Protheus** via API REST e entrega:
- **Fluxo de caixa realizado e projetado para 90 dias**, em dashboard
- Ajuste automático de vencimentos que caem em **fins de semana e feriados**
- Gerenciador de **pagamentos fixos** recorrentes
- Uso da **data de lançamento** dos títulos como referência, mais confiável que outras datas do sistema

## Arquitetura
```
Protheus (tabelas de contas a pagar/receber)
        │  endpoints REST em ADVPL
        ▼
Backend Node.js  ──►  Dashboard web (projeção 90 dias)
```

## Tecnologias
Node.js · ADVPL (endpoints REST no Protheus) · HTML/JS · TOTVS Protheus

## Resultado
Módulo de fluxo de caixa apresentado e aprovado pela diretoria. Próximo passo: validar os dados do ERP contra o XML das notas fiscais (NF-e).
