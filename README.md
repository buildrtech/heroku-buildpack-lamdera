# heroku-buildpack-lamdera

Push: [![Test](https://github.com/buildrtech/heroku-buildpack-lamdera/actions/workflows/test.yml/badge.svg?event=push)](https://github.com/buildrtech/heroku-buildpack-lamdera/actions/workflows/test.yml)
Scheduled: [![Test](https://github.com/buildrtech/heroku-buildpack-lamdera/actions/workflows/test.yml/badge.svg?event=schedule)](https://github.com/buildrtech/heroku-buildpack-lamdera/actions/workflows/test.yml)

A Heroku buildpack for lamdera that always downloads the latest [static build](https://dashboard.lamdera.app/docs/download).
Unlike other build packs, I never compile anything.

## Usage

Run the following from the heroku command line:

```
heroku buildpacks:add --index 1 https://github.com/buildr/heroku-buildpack-lamdera.git
```

You can set a custom download URL by setting the variable `LAMDERA_DOWNLOAD_URL`.

Note: This buildpack should be added before the main language buildpack (by using `--index 1`),
since the application process types are calculated from the last buildpack in the list if no
`Procfile` is specified.
