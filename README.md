# jest-reporter-teamcity

> Integrate Jest test results into your Teamcity CI builds

![screenshot1](https://raw.githubusercontent.com/harelmo/jest-reporter-teamcity/master/docs/screenshot1.png)

![screenshot2](https://raw.githubusercontent.com/harelmo/jest-reporter-teamcity/master/docs/screenshot2.png)

![screenshot3](https://raw.githubusercontent.com/harelmo/jest-reporter-teamcity/master/docs/screenshot3.png)

![screenshot4](https://raw.githubusercontent.com/harelmo/jest-reporter-teamcity/master/docs/screenshot4.png)

This package will report your JavaScript Jest test results to your Teamcity CI server, so you can see the number of executed tests, test failures and the tests tab right from your Teamcity UI.

---

### Usage

First, install the package from NPM: `npm install --save-dev jest-reporter-teamcity`

The reporter integrates with Jest in form of a [testResultsProcessor](https://facebook.github.io/jest/docs/en/configuration.html#testresultsprocessor-string). Put this into your projects `package.json`:

```
"jest": {
    "testResultsProcessor": "jest-reporter-teamcity"
}
```

The reporter is only active when the environment variable `TEAMCITY_VERSION` is present which should be the case for most common Teamcity server installations. So on your local machine the reporter should be disabled by default. You can test the reporter by temporarily setting the environment variable:

`export TEAMCITY_VERSION="your_version"`

Then, just use Jest as usual, e.g. put this in your `package.json`

```
"scripts": {
    "test": "jest"
}
```

Then, simply run `npm test` locally and from Teamcity.

> Versions < 0.5.0 also supported activation via cli option `--teamcity` but Jest no longer supports custom options, so this option is no longer available.

### License

MIT © [Benjamin Winterberg](https://twitter.com/winterbe_) © Harel Moshe
