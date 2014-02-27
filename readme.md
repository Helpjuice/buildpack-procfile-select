# Heroku Buildpack: Environment-specific Procfiles

Because sometimes you just want to run different configurations of the same app on Heroku.

## Usage
You almost definitely want to use this as part of a
[multi-buildpack](https://github.com/ddollar/heroku-buildpack-multi)

This buildpack must come before you're actual environment buildpack (when the process starts).
A sample node.js `.buildpack` file may look like:
```
https://github.com/jessefulton/env-procfile-buildpack.git
https://github.com/heroku/heroku-buildpack-nodejs.git
```

Then if you want to use a different Procfile than the standard one, simply set
an environment variable, and push!

```
heroku config:set PROCFILE=Procfile.dev
```

