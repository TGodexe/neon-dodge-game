# 🌾 PIXEL HARVEST — Farm RPG Multiplayer Prototype

A browser farming RPG built with HTML, CSS and JavaScript. Runs on GitHub Pages with no build step.

## Features
- Plant, grow and harvest carrots, corn and strawberries
- Buy seeds, sell crops, earn gold, XP and character levels
- Energy regeneration, daily rewards, foraging quests
- WASD, arrow keys, on-screen controls and tap-to-move
- Local save using browser localStorage
- **Optional multiplayer:** live player positions and room chat using Supabase Realtime Presence + Broadcast

## Play locally
Open `index.html` in a browser. Internet is needed to load the Supabase client module from esm.sh; solo farming works without Supabase credentials.

## Publish on GitHub Pages
1. Merge the feature branch to `main`.
2. In GitHub, open **Settings → Pages**.
3. Select **Deploy from a branch**, `main`, `/(root)`.
4. Your expected URL is https://tgodexe.github.io/neon-dodge-game/ once published.

## Enable multiplayer
1. Create a free Supabase project at https://supabase.com.
2. In the project dashboard, copy **Project URL** and **anon/publishable key**. **Never enter the service_role/secret key** in the browser.
3. Ensure Supabase Realtime is enabled for public channels. This prototype uses ephemeral **Presence** and **Broadcast**; it does not require database tables.
4. All players enter the **same Supabase project URL, public key and room name**, with their own character names, and click **Connect room**.
5. Open the game URL on separate devices to see each other's avatars and chat messages.

## Important limitations
- Multiplayer shares **player presence, movement and chat only**. Crops, inventory, gold, XP and quest progress are **local per device**, not shared or authoritative.
- There is no authentication, moderation, anti-cheat, persistent multiplayer world, PvP or server-backed economy.
- Public Realtime rooms are suitable for a demo among friends; don't share private information in chat.
- Supabase's public project key is intended for browser use; secret/service_role keys are not.
- This is a new game replacing the old NEON DODGE interface. The GitHub repository name stays `neon-dodge-game`.

## Next steps
For true persistent shared-world RPG gameplay, add authenticated player accounts, server-side game logic, Postgres persistence, authoritative inventory/economy and rate-limited chat.
