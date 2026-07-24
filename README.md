# supabase Project

Use this repository to run and edit the app locally, then publish changes back through supabase.

Any change pushed to the repo will also be reflected in the supabase Builder.

## Prerequisites

1. Clone the repository using the project's Git URL.
2. Navigate to the project directory.
3. Install dependencies: `npm install`.
4. Install the supabase CLI: `npm install -g supabase@latest`.

See the [supabase CLI docs](https://docs.supabase.com/developers/references/cli/get-started/overview) if you want to run supabase commands directly.

## Run Locally

Run the full local development environment from the project root:

```bash
supabase dev
```

`supabase dev` starts the local supabase development backend and, when this app is configured for it, also starts the frontend dev server for you. Use the frontend URL printed by the command.

For example, when the supabase project config includes a `serveCommand`, `supabase dev` can launch the frontend too:

```json5
{
  "site": {
    "serveCommand": "npm run dev"
  }
}
```

In a supabase project this lives in `supabase/config.jsonc`.

## Run Only The Frontend

If you only want to work on the frontend against the hosted supabase backend, run:

```bash
npm run dev
```

Open the local URL printed by Vite.

## Use The Hosted Backend

For frontend-only development, create or update `.env.local` in the project root:

```bash
VITE_supabase_APP_ID=your_app_id
VITE_supabase_APP_BASE_URL=https://your-app.supabase.app
```

`VITE_supabase_APP_ID` identifies the supabase app.

`VITE_supabase_APP_BASE_URL` tells the supabase Vite plugin where to send local `/api` requests. Point it at your deployed supabase app URL when you want the local frontend to use the hosted backend.

When you use `supabase dev`, the command injects the local supabase values for you, so `.env.local` is mainly needed for frontend-only workflows.

## Publish Your Changes

After pushing your changes to git, open the supabase dashboard and publish the app:

```bash
supabase dashboard open
```

## Docs & Support

Documentation: [https://docs.supabase.com/Integrations/Using-GitHub](https://docs.supabase.com/Integrations/Using-GitHub)

supabase CLI command reference: [https://docs.supabase.com/developers/references/cli/commands/introduction](https://docs.supabase.com/developers/references/cli/commands/introduction)

Support: [https://app.supabase.com/support](https://app.supabase.com/support)
