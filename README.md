# Bitrise-Fastlane-Match-Sample

## Install Fastlane

```brew install fastlane```

## Verify Fastlane is installed

```fastlane -v```

## Fastlane Match Docs

[Fastlane Match Docs](https://docs.fastlane.tools/actions/match/)

----

## Creating the Encrypted Certificate Repo

1. Create a new empty repo

2. Checkout the repo locally

3. Run the following command in the root of the repo (Make sure to remember the Match Decrypt Password you entered as you will need it later)

```fastlane match init```

![fastlane init](https://docs.fastlane.tools/img/actions/match_init.gif)

4. Update the `git_url` in the generated [Matchfile](https://github.com/LexZavala/Bitrise-Fastlane-Match-Sample/blob/main/Matchfile#L2)

5. Update the `app_identifier` in the generated [Matchfile](https://github.com/LexZavala/Bitrise-Fastlane-Match-Sample/blob/main/Matchfile#L9)

6. Update the `username` (This is your Apple Developer Portal email address) in the generated [Matchfile](https://github.com/LexZavala/Bitrise-Fastlane-Match-Sample/blob/main/Matchfile#L10)

----

## Generating the Certificates and Profiles

### Development Certs and Profiles
```fastlane match development```

### App Store Certificates and Profiles

```fastlane match appstore```

![fastlane match development](https://docs.fastlane.tools/img/actions/match_appstore_small.gif)

----

## Updating the sample app

1. Update the Xcode Project Bundle ID to match your Bundle ID

2. Make sure that Automatic Code Signing is disabled

----

## Using Fastlane Match on Bitrise

1. Add the Fastlane Match step to your workflow before you build your app.

2. Add your `Match Decrypt Password` entered when running `fastlane init` as a Secret on Bitrise

3. Configure the Fastlane Match step with your `git url`, `branch`, `App ID`, `Match Password`, `Platform` and `Team ID`

4. Run your build. (Make sure your `Fastlane Match` step is run before your `Xcode Archive` Step for code signing to work)

![Workflow](https://github.com/LexZavala/Bitrise-Fastlane-Match-Sample/raw/main/workflow.png)

----
