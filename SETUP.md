# Aquenza Production System
This package implements the recommended synchronized version: cloud database, login, roles, sales, inventory, customers, expenses, reports and audit trail.

## Setup
1. Create a Supabase project.
2. Open SQL Editor and run `supabase.sql`.
3. Enable Email/Password authentication.
4. Create the first user in Supabase Authentication > Users.
5. Get that user's UUID and run:
`update public.profiles set role='owner' where id='YOUR-USER-UUID';`
6. Open `config.js` and replace the Supabase URL and anon/public key. Never put a service_role key in browser code.
7. Upload the folder to an HTTPS host such as Netlify, Vercel, GitHub Pages or your own server.
8. Open the HTTPS URL on a phone and use Add to Home Screen / Install App.

## Roles
owner/admin: management controls and void authorization
cashier: sales operations
inventory: inventory maintenance

New users are automatically created as cashier. Change roles in SQL:
`update public.profiles set role='inventory' where id='USER-UUID';`

## Going live
Customize actual products/prices, delivery charges, container deposits/returns, customer credit policy, official receipt format and staff accounts. Reconcile cash/GCash daily and maintain accounting/tax records separately.

The application code is ready, but publishing requires your own Supabase project and hosting credentials; those cannot be safely invented or embedded here.
