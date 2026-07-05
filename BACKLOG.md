# Backlog de Ideias - Bot Figurinhas Ninna Rata 💅🐀

Lista de ideias, melhorias e novos recursos planejados para o futuro do bot, painel de administração e ecossistema.

---

## 🚀 Ideias de Funcionalidades

### 📥 1. Recuperação de Carrinho Abandonado (VIP)
- **Descrição:** Programar o envio de mensagens de acompanhamento (follow-up) automáticas no WhatsApp para usuários que iniciaram o processo de checkout do VIP (geraram link de pagamento/Pix) mas não finalizaram a compra após um período determinado (ex: 2 horas ou 24 horas).
- **Objetivo:** Recuperar vendas e aumentar a conversão de novos usuários VIP.
- **Implementação Sugerida:**
  - Registrar no banco de dados SQLite a data/hora e o link de checkout gerado quando o comando `/vip` é executado e o link do Stripe é gerado.
  - Um script/cron job periódico verifica checkouts pendentes há mais de X horas que não tiveram uma ativação correspondente.
  - Enviar uma mensagem persuasiva com o tom da Ninna Rata (ex: oferecendo ajuda com o pagamento ou lembrando as vantagens exclusivas do VIP).

---
