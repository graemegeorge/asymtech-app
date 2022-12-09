## Expo submission to app store

_eas, expo, build, submit, testflight_

### Requirements:

- Expo project `npx create-expo-app my-app`
- An Expo account

### Resources

- [Creating your first build - Expo Documentation](https://docs.expo.dev/build/setup/)
- [ASCAppId](https://github.com/expo/fyi/blob/main/asc-app-id.md)
- [Submit iOS](https://docs.expo.dev/submit/ios/)
- [Article: How to publish expo app to testflight](https://levelup.gitconnected.com/react-native-how-to-publish-an-expo-app-to-testflight-debug-common-errors-90e427b4b5ea)
- [AppStoreConnect](https://help.apple.com/app-store-connect/#/devdc42b26b8)

I've summarised the process to ensure we understand the key steps. Resources above go into finer detail.

### Build

1. Install CLI `npm install -g eas-cli` use `npm` or `npx eas-cli *` if using `yarn` `pnpm`
2. Log in to eas `eas login`
3. Prepare the build `eas build:configure`
4. Run the build `eas build —platform [all|iOS|android]`
   1. Prompt: Log in to apple dev account
   2. Prompt: Generate apple dist cert (Y)
   3. Prompt: Generate apple provisioning profile (Y)

### Submit

1. Start submission `eas submit`
2. Prompt: Log in to apple dev account
3. Prompt: Select “Add new ASC API key” since other option soon to be deprecated

### Distribute

1. Once built, you'll be given a url that that takes you to TestFlight configuration
2. Here you'll need to wait for your build to be approved (15 minutes for me)
3. After some time, you'll then asked to confirm what encryption methods your app uses. I selected "None".
4. After a little more time your build will be ready for distribution and any groups included on the build will be sent emails to beta test the app.
5. In order to do so you'll need to download the TestFlight app from app store
6. Find the email, hit the link and you'll be given an app inside TestFlight as well as a standalone version on your home screen.
7. Optionally: Add emails to public beta testing (This is where you can share a public URL as well) Beta testing takes a little longer to be approved and a beta testing plan must be submitted.
