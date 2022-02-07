## Getting started
- Have Node >v16
- Run `npm install` 

## Running
- `npm run dev`
- Then, in a separate window: `dotnet watch`

## For Production
- `npm run prod`

## format
`dotnet format --severity warn`

## FAQ
### Tailwind
An npm script has been set up with the appropriate calls to the tailwindcli (see `package.json`). Newer versions of tailwind operate in JIT mode. The tl;dr here is your css (`webroot/css/index.css`) needs to be *compiled* before it can be *included*. 

It's output will be stored at `webroot/dist/site.css`, where it will be referenced by the main layout file (`Views/Shared/_Layout.cshtml`).

#### dev
Running `npm run dev` will start tailwindcli in "watch" mode. Any changes you make will automatically be reflected.

#### prod
Running `npm run dev` will start tailwindcli in build mode. In addition to compiling your `index.css`, the resulting output will be minified as well.

### Nullable warnings
It's "safe" to ignore warnings on startup about nullables. These are scaffolded from a template. Feel free to correct them. See https://docs.microsoft.com/en-us/dotnet/csharp/nullable-references.

### Database
Install ef tools if they aren't already present.
`dotnet tool install --global dotnet-ef`

#### Run migrations
- `dotnet ef database update`

Alternatively, run the web app and let dotnet run migrations automatically. If you encounter an exception page, click on "Run migrations" and refresh.

#### Clean state
Remove `livinglab_main.sqlite`, rerun migrations.
