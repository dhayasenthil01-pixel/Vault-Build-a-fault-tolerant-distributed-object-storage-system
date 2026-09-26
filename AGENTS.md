<!-- LOVABLE:BEGIN -->
> [!IMPORTANT]
> This project is connected to [Lovable](https://lovable.dev). Avoid rewriting
> published git history — force pushing, or rebasing/amending/squashing commits
> that are already pushed — as it rewrites history on Lovable's side and the
> user will likely lose their project history.
>
> Commits you push to the connected branch sync back to Lovable and show up in
> the editor, so keep the branch in a working state.
<!-- LOVABLE:END -->

## Project rules

- Data access goes through the browser Supabase client in `src/lib/vault.ts` with RLS-scoped tables; no server functions are used, because every read/write is user-owned.
- Replica placement and repair-timeline entries are created by the `on_file_created` database trigger, so the UI never writes replicas itself.
- Authenticated pages live under `src/routes/_authenticated/app.*`; `/` and `/auth` stay public.
