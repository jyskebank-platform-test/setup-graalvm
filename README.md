# setup-graalvm

This action sets up the GraalVM built by Gluon environment for using in GitHub Actions.

* It downloads (if it is not cached yet) required version of Gluon's build of GraalVM Community edition
* Adds executors provided by GraalVM distribution to the environment
* Register problem matchers for error output

# Usage

```yaml
steps:
- uses: actions/checkout@latest
- uses: gluonhq/setup-graalvm@master
  # set GITHUB_TOKEN to avoid exceeding GitHub's API rate limit
  env:
    GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
  with:
    # GraalVM version. Default: latest
    graalvm: '21.1.0-dev-20210415_0700'
- run: java -version
```

# License

The scripts and documentation in this project are released under the [MIT License](LICENSE)
