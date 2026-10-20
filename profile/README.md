<picture><source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/inkanjs/inkan/main/assets/wordmark-dark.svg"><img src="https://raw.githubusercontent.com/inkanjs/inkan/main/assets/wordmark-light.svg" alt="inkan" width="300"></picture>

**An API framework for Node where the docs can't lie.**

**[Docs](https://inkan-dev.vercel.app/docs)** · [Hanko](https://inkan-dev.vercel.app/hanko) · [Benchmarks](https://inkan-dev.vercel.app/benchmarks) · [Changelog](https://github.com/inkanjs/inkan/blob/main/CHANGELOG.md)

An *inkan* (印鑑) is the seal a Japanese contract gets stamped with. Here every route
carries one, written once: inkan checks what comes in, types your handler, trims what goes
out, writes OpenAPI, serves the docs, runs your examples as tests and hands your frontend a
typed client. The core has no dependencies.

```ts
import { inkan, t } from "@vxnsin/inkan";

inkan()
  .get("/hello/:name", { params: t.object({ name: t.string() }) }, ({ params }) => ({ hello: params.name }))
  .listen({ port: 3000 }); // docs on /docs, a live inspector on /_inkan
```

### Repositories

| | |
| --- | --- |
| [**inkan**](https://github.com/inkanjs/inkan) | the framework: routes and contracts, docs, `inkan check`, jobs, websockets, a typed client |
| [**middleware**](https://github.com/inkanjs/middleware) | official plugins: auth, session, secure-headers, etag, idempotency, proxy, circuit-breaker, otel, and stores for Redis, Postgres, MongoDB and MySQL |
| [**integrations**](https://github.com/inkanjs/integrations) | inkan where you already are: Next.js, Vite, TanStack Query, uWebSockets.js |
| [**inkan.dev**](https://github.com/inkanjs/inkan.dev) | the website and docs, itself an inkan app |

Everything that plugs into inkan, official or not, is listed on
**[Hanko](https://inkan-dev.vercel.app/hanko)**. Publish a package with the npm keyword
`inkan-plugin` and it shows up there by itself.

### Start

```sh
npx @vxnsin/inkan learn                      # twelve quests in your terminal, offline
npx @vxnsin/inkan examples                   # six explained projects to start from
npx @vxnsin/inkan create plugin inkan-quota  # a plugin package with tests, ready to publish
```

Questions, bugs and ideas go into [issues](https://github.com/inkanjs/inkan/issues), and pull
requests are welcome. Since 0.8 the API is
[stable](https://inkan-dev.vercel.app/docs/stability): renames keep working with a warning
for at least two releases. MIT licensed.
