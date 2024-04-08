# Jestbug

To replicate:
1. Clone repo
2. `npm ci`
3. `nx serve jestbug`
4. Modify any source, eg `app.service.ts`

Example error log:

```
jestbug git:(main) ✗ npx nx serve jestbug --verbose

> nx run jestbug:serve:development

Build option outputFileName not set for jestbug. Using fallback value of dist/apps/jestbug/main.js.

> nx run jestbug:build

> webpack-cli build --node-env=production

chunk (runtime: main) main.js (main) 2.71 KiB [entry] [rendered]
webpack compiled successfully (f7cc4864fae435d6)

————

 NX   Successfully ran target build for project jestbug


Debugger listening on ws://localhost:9229/247e11dd-40eb-449b-8907-15df5f6a18fa
Debugger listening on ws://localhost:9229/247e11dd-40eb-449b-8907-15df5f6a18fa
For help, see: https://nodejs.org/en/docs/inspector

[Nest] 39563  - 09/04/2024, 7:37:07 am     LOG [NestFactory] Starting Nest application...
[Nest] 39563  - 09/04/2024, 7:37:07 am     LOG [InstanceLoader] AppModule dependencies initialized +6ms
[Nest] 39563  - 09/04/2024, 7:37:07 am     LOG [RoutesResolver] AppController {/api}: +2ms
[Nest] 39563  - 09/04/2024, 7:37:07 am     LOG [RouterExplorer] Mapped {/api, GET} route +1ms
[Nest] 39563  - 09/04/2024, 7:37:07 am     LOG [NestApplication] Nest application successfully started +1ms
[Nest] 39563  - 09/04/2024, 7:37:07 am     LOG 🚀 Application is running on: http://localhost:3000/api

 NX  File change detected. Restarting...

node:internal/process/promises:289
            triggerUncaughtException(err, true /* fromPromise */);
            ^

[Failed to process project graph.
  The "@nx/jest/plugin" plugin threw an error while creating nodes from apps/jestbug/jest.config.ts:
    Error: ● Validation Error:
    
      Option "displayName" must be of type:
        array
      but instead received:
        string
    
      Example:
      {
        "displayName": [
          "test-config",
          {
            "color": "blue",
            "name": "test-config"
          }
        ]
      }
    
      Configuration Documentation:
      https://jestjs.io/docs/configuration
    ] {
  name: 'ProjectGraphError'
}

Node.js v20.10.0
Build failed, waiting for changes to restart...
```