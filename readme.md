# Heroku Buildpack: Procfile Select

Because sometimes you just want to run different configurations of the same app on Heroku.
See [buildpack-procfile-select-test](https://github.com/jessefulton/buildpack-procfile-select-test)
for an example.

## Usage
You almost definitely want to use this as part of a
[multi-buildpack](https://github.com/ddollar/heroku-buildpack-multi).

This buildpack must come before your actual environment buildpack (when the process starts).
A sample node.js `.buildpack` file may look like:
```
https://github.com/Helpjuice/env-procfile-buildpack.git
https://github.com/heroku/heroku-buildpack-nodejs.git
```

Then if you want to use a different Procfile than the standard one, simply set
an environment variable, and push!

```
heroku config:set PROCFILE=Procfile.dev
```

