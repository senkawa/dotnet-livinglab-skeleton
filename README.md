## Running
`dotnet watch`

## format
`dotnet format --severity warn`

## FAQ
### Nullable warnings
It's "safe" to ignore warnings on startup about nullables. These are scaffolded from a template. Feel free to correct them. See https://docs.microsoft.com/en-us/dotnet/csharp/nullable-references.

### Database
Install ef tools if they aren't already present.
`dotnet tool install --global dotnet-ef`

#### Run migrations
- `dotnet ef database update --context ApplicationDbContext`
- `dotnet ef database update --context IdentityDataContext`

Alternatively, run the web app and let dotnet run migrations automatically. If you encounter an exception page, click on "Run migrations" and refresh.

#### Clean state
Remove `livinglab_main.sqlite`, rerun migrations.
