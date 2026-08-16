# WhatsApp AI Business Bot

Production-oriented multi-tenant WhatsApp SaaS starter.

## What it does
- Multi-tenant businesses
- Business profile, services/products and FAQ knowledge
- WhatsApp Cloud API webhook verification and inbound messages
- AI replies using OpenAI Responses API
- Conversation history
- Human handoff keyword support
- Admin dashboard
- Secure secrets via environment variables
- Prisma + PostgreSQL
- Ready for deployment on Vercel/Render/etc.

## Important
This is not connected to a real WhatsApp number until you add Meta credentials and configure the webhook. WhatsApp Cloud API requires a Meta business portfolio, WhatsApp Business Account and business phone number.

## Local setup
1. Install Node.js 20+.
2. Copy `.env.example` to `.env`.
3. Create a PostgreSQL database and set `DATABASE_URL`.
4. Set the OpenAI and Meta variables.
5. Run:
   npm install
   npx prisma generate
   npx prisma migrate dev --name init
   npm run dev

## Production
- Use a managed PostgreSQL database.
- Set all environment variables in the hosting provider.
- Run `npx prisma migrate deploy`.
- Set Meta webhook callback URL to:
  https://YOUR-DOMAIN.com/api/webhooks/whatsapp
- Use the same `WHATSAPP_VERIFY_TOKEN` in Meta and the application.
- Subscribe the WhatsApp Business Account to `messages`.

## Security
Never commit `.env`, access tokens, database passwords, or OpenAI keys.
