# heroku-buildpack-lamdera

Push: [![Test](https://github.com/buildr/heroku-buildpack-lamdera/workflows/Test/badge.svg?branch=master&event=push)](https://github.com/buildr/heroku-buildpack-lamdera/actions?query=workflow%3ATest+event%3Apush+branch%3Amaster)
Scheduled: [![Test](https://github.com/buildr/heroku-buildpack-lamdera/workflows/Test/badge.svg?branch=master&event=schedule)](https://github.com/buildr/heroku-buildpack-lamdera/actions?query=workflow%3ATest+event%3Aschedule+branch%3Amaster)

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
