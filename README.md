# Relay Messaging Platform

A lightweight browser-based messaging app backed by your Supabase project. It includes email/password accounts, profiles, direct chats, group chats, and live message updates.

## Run it on your Windows PC

1. Extract this ZIP file to a folder.
2. Open that folder in File Explorer.
3. Click the address bar, type `powershell`, and press Enter.
4. Run:

   ```powershell
   python -m http.server 5500
   ```

5. Open this address in your browser: <http://localhost:5500>

Keep the PowerShell window open while using Relay. Stop the local server with `Ctrl+C`.

## One-time Supabase Auth redirect setting

In the Supabase dashboard for the Relay project, open **Authentication → URL Configuration**.

- Set **Site URL** to `http://localhost:5500`
- Add `http://localhost:5500/**` under **Redirect URLs**

This lets email confirmation links return to the local app. When you host the app on a real domain later, add that domain to the Redirect URLs and update the Site URL.

## Create your account

Choose **Create an account**, enter your display name, username, email, and password, then confirm your email if Supabase asks you to. After confirming, return to Relay and sign in.

## Notes

- The Supabase schema and row-level security policies have already been applied to the linked project.
- The app uses the public publishable key. It does not contain a service-role or secret key.
- Keep Row Level Security enabled. Do not put a Supabase secret/service-role key in this HTML file.
- Supabase Auth's leaked-password protection is currently disabled in the project; enable it in **Authentication → Password Security** for stronger password checks.
