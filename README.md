# Coxinha do Barão — Sistema de Gestão e PDV

Sistema de vendas e controle financeiro feito sob medida para uma salgaderia: PDV rápido no balcão, estoque por produto e dashboard financeiro com filtro por período.

**Acesse:** https://coxinha-do-barao.vercel.app

![Tela de login do sistema Coxinha do Barão](tela-login.jpg)

> O código-fonte fica em repositório privado por ser um sistema em uso por um cliente. Este repositório é a vitrine do projeto.

## O que o sistema faz
- **PDV:** grade de produtos com botões grandes, carrinho e pagamento em dinheiro, Pix ou cartão
- **Estoque:** baixa automática a cada venda, alerta abaixo do mínimo e ajuste rápido
- **Financeiro:** livro de entradas e saídas, com lançamento automático de cada venda
- **Dashboard:** faturamento, despesas, lucro líquido e ranking de produtos (hoje, 7, 15 e 30 dias)
- **Aplicativo (PWA):** instala no notebook do balcão, com ícone próprio e aviso quando a internet cai

## Decisões técnicas
- Cada venda roda em uma única transação: baixa o estoque e gera o lançamento financeiro juntos, ou nada acontece
- Valores em dinheiro com `decimal.js`, sem erro de ponto flutuante
- Login com JWT e senhas com bcrypt; todas as rotas da API protegidas
- O service worker nunca guarda dados de venda em cache, para o caixa nunca mostrar número velho
- Layout mobile-first: barra inferior no celular, menu lateral no computador

## Stack
**Front-end:** React · TypeScript · Vite · Tailwind CSS · React Query · Recharts
**Back-end:** Node.js · Express · Prisma ORM · Zod · JWT · bcrypt
**Deploy:** Vercel

Desenvolvido por [Paulo Henrique](https://github.com/phsantos06) · [Portfólio](https://phsantos06.github.io)
