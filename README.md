# Tifig Buildpack

This is a [Heroku buildpack][0] for bundling a compatible [tifig][1]
binary with your environment.

## Versions

* Buildpack:   `0.2`
* tifig: `0.2.2` by default

## Usage

[Add this buildpack][2] to your Heroku application to install the `tifig`
binay,
into the dynos:

```bash
$ heroku buildpacks:add https://github.com:alan-eu/tifig-buildpack.git
```

If you want to use a `tifig` version other than 0.2.2, set
`TIFIG_VERSION`:

```bash
heroku config:set TIFIG_VERSION="0.2.2"
```

### Clearing Repo Cache

Remember to clean your repository cache if you are updating the version of
buildpack. To do that, run:

```bash
$ heroku plugins:install https://github.com/heroku/heroku-repo.git
$ heroku repo:purge_cache -a appname
```

## Troubleshooting

If you run into issues when trying to deploy with this buildpack, make sure your
app is running on `cedar-14` or `heroku-16`. You can check this with:

```bash
$ heroku stack
```

[0]: http://devcenter.heroku.com/articles/buildpacks
[1]: https://github.com/monostream/tifig
[2]: https://devcenter.heroku.com/articles/using-multiple-buildpacks-for-an-app
