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

### 💾 2. Automação de Backups da VPS e Banco de Dados (SQLite)
- **Descrição:** Configurar um sistema robusto de backups periódicos e automatizados para a base de dados SQLite (`database.sqlite`) e os arquivos essenciais do bot na VPS.
- **Objetivo:** Garantir a integridade dos dados dos usuários, VIPs ativos e histórico de eventos em caso de falha de hardware ou instabilidade do servidor.
- **Implementação Sugerida:**
  - Criar um script bash na VPS que realiza o `VACUUM` (compactação de segurança) do banco SQLite e gera uma cópia comprimida (`.zip` ou `.tar.gz`).
  - Configurar um cron job no Linux para rodar o backup de forma automatizada (ex: diariamente às 03:00 da manhã).
  - Enviar a cópia de backup de forma criptografada para um serviço externo em nuvem (como Google Drive, AWS S3 ou Telegram Private Channel/Bot) ou para um repositório Git privado de backup.
  - Notificar o administrador via WhatsApp ou E-mail caso a rotina de backup falhe.

---
