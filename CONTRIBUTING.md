# Contributing

Thanks for wanting to help. Bug reports, fixes, docs and plugins are all welcome.

## Before you start

For a bug, an issue with the smallest code that shows it is the most useful thing you can
send. For a bigger change, open an issue first and say what you'd like to do, so we can
agree on the shape before you spend time on it. Small fixes can go straight to a pull
request.

## Setup

You need Node 22.18 or newer (`.ts` files run without a build step from there on).

```sh
git clone https://github.com/inkanjs/inkan
cd inkan
npm ci
npm run typecheck
npm test
```

The middleware and integrations repos work the same way, with npm workspaces: `npm install`,
`npx tsc`, `npm test` at the root. The store packages test against real databases; without
`REDIS_URL`, `DATABASE_URL`, `MONGO_URL` or `MYSQL_URL` they start one for the tests or skip
with a message.

## What a pull request needs

- **Tests.** A fix comes with a test that fails without it. A feature comes with tests for
  what it does and for the ways it can go wrong.
- **No new runtime dependencies** in the core. It has none, and that's on purpose.
- **No `eval` or `new Function`.**
- **The public API.** If your change touches what `@vxnsin/inkan` exports, run
  `npm run api:update` and commit the updated `api/inkan.d.ts.txt`; the test fails until you
  do. Stable API follows [the stability policy](https://inkan-dev.vercel.app/docs/stability): renames keep the old name
  as a deprecated alias.
- **A CHANGELOG line** under the next version, in the style of the ones around it.
- **Short commit messages** in the conventional style: `fix(client): …`, `feat(ws): …`,
  `docs: …`. Pull requests are squashed when they're merged, so the history stays readable.

Performance changes need numbers. The bench is in `bench/`; for small changes
`node bench/inproc.mjs` compares two versions on your machine, and the `bench` workflow
runs the full comparison on GitHub.

## Plugins

You don't need to send a plugin here to share it. Run `npx @vxnsin/inkan create plugin
<name>`, publish it on npm with the keyword `inkan-plugin`, and it shows up on
[Hanko](https://inkan-dev.vercel.app/hanko) by itself.

## AI-written code

That's fine, as long as you understand what you're sending and have run it. inkan itself is
written that way too (see "How inkan is made" in the README). A pull request is judged by
what it does and whether its tests hold, not by how it was typed.

## Conduct

Be kind and assume good intent. See the [code of conduct](CODE_OF_CONDUCT.md).
