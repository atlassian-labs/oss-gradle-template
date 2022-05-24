# oss-gradle-template

This project template sets up your Gradle-based project to be published to Maven Central.

## Building

```
./gradlew build
```

## Publishing to Artifactory

```
./gradlew artifactoryPublish
```

## CI 

This project contains a [GitHub Actions workflow file](.github/workflows/branch.yml) that:

* runs the build on every push to any branch
* publishes to Artifactory on every push to the `release` branch (uses the [artifact-publish-token](https://github.com/atlassian-labs/artifact-publish-token) GitHub action to generate temporary access tokens for Artifactory).

To make that work, add these secrets to your GitHub project:

* `SIGNING_KEY`: the private key that is used for signing the artifacts
* `SIGNING_PASSWORD`: the password to the private key

