# Gobaith Reborn Client

Client bundles for running Gobaith Reborn in Selene:

- `illarion-client-core/`: shared Lua behavior for movement, combat, and music,
  plus Vue/TypeScript services for inventory, vitals, skills, magic, books, and
  world actions.
- `illarion-gobaith-ui/`: the Gobaith HUD, including panels, input handling,
  viewport, and cursor graphics. Depends on `illarion-client-core` and `moonlight-ui`.

## Development

Use pnpm (the version is pinned in `package.json`). The `moonlight` bundle checkout
must be beside this checkout; its UI package is a local dependency.

Run from this repository root:

```sh
pnpm install
pnpm dev
```

Build the HUD with `pnpm build`. Output goes to
`illarion-gobaith-ui/client/ui/dist`. Use `pnpm build:watch` to rebuild on changes.

To check the code:

```sh
pnpm typecheck
pnpm lint
```

## Loading in Selene

Load both bundles and their `moonlight-ui` dependency. For example, when launching
from the Selene client directory with this checkout under `bundles/gobaith-reborn-client`:

```sh
-b moonlight-ui ../../bundles/moonlight/moonlight-ui \
-b illarion-client-core ../../bundles/gobaith-reborn-client/illarion-client-core \
-b illarion-gobaith-ui ../../bundles/gobaith-reborn-client/illarion-gobaith-ui
```
