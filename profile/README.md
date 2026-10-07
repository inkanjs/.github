<picture><source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/inkanjs/inkan/main/assets/wordmark-dark.svg"><img src="https://raw.githubusercontent.com/inkanjs/inkan/main/assets/wordmark-light.svg" alt="inkan" width="300"></picture>

**An API server for Node where the docs can't lie.**

An *inkan* (印鑑) is the seal a Japanese contract gets stamped with. Here every route
carries one, written once: inkan checks what comes in, types your handler, trims what goes
out, writes OpenAPI, serves the docs, runs your examples as tests and hands your frontend a
typed client. No dependencies.

```ts
import { inkan, t } from "@vxnsin/inkan";

inkan()
  .get("/hello/:name", { params: t.object({ name: t.string() }) }, ({ params }) => ({ hello: params.name }))
  .listen(3000); // docs on /docs, a live inspector on /_inkan
```

| | |
| --- | --- |
| [**inkan**](https://github.com/inkanjs/inkan) | the framework: routes, contracts, docs, inspector, `inkan check`, `inkan diff`, typed client |
| [examples](https://github.com/inkanjs/inkan/tree/main/templates) | six explained projects: `npx @vxnsin/inkan examples` |
| [changelog](https://github.com/inkanjs/inkan/blob/main/CHANGELOG.md) | what changed, release by release |

Want to help? Issues marked
[good first issue](https://github.com/inkanjs/inkan/labels/good%20first%20issue) are a good
place to start. MIT licensed.
