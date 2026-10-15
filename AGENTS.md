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

- Roles live in `user_roles` (admin/driver); the first signup becomes admin via the `handle_new_user` trigger — keeps privileges server-controlled.
- Order acceptance/completion goes through `accept_order`/`complete_order` SQL functions — guarantees first-to-accept wins atomically.
- Locked-screen alerts use built-in Web Push: public/push-sw.js + push_subscriptions table, sent by notifyDrivers server fn; VAPID keys derived from the VAPID_SEED secret — no third-party account needed.
