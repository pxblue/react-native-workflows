# Changelog
All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## v2.0.0

### Changed
-   Updated to use React Native Paper version 4 components — this update requires you to update your project to use v4 as well.

## v1.4.0

### Added
-   `phoneContactLink` prop to allow specification of tel URI details while keeping `phoneContact` for human-readable UI display of the same number

### Fixed
-   ChangePassword was not using the correct error message
-   EULA checkbox will only be available to tap after the webview has loaded
-   Tapping the "X" from an Android cold boot deep link will now properly navigate to Login

### Changed
-   ChangePassword now uses the property callbacks rather than directly using security helper
-   Additional support for Android hardware back button closing out of the various deep link flow to Login
-   Default TextInput selection color is now light blue for Android

## v1.3.0

### Added
-   i18n utilities
    -   This was relocated from [@pxblue/react-auth-shared](https://www.npmjs.com/package/@pxblue/react-auth-shared)
-   DismissKeyboardView component
    -   This was relocated from @pxblue/react-auth-shared

### Fixed
-   Fixed custom `passwordRequirements` validation on the create password and change password screens.

## v1.2.1
### Changed
-   Shareable logic has been extracted to [@pxblue/react-auth-shared](https://www.npmjs.com/package/@pxblue/react-auth-shared). This package re-exports all exports from the shared package, so there are no breaking changes in usage. The majority of the API documentation in now in the shared repository.

## v1.1.0
### Added
- New required `RegistrationUIActions` for self registration, `requestRegistrationCode`, which takes an email string
- Optional email parameter (`validationEmail?: string`) to the following registration actions: `validateUserRegistrationRequest`, `completeRegistration`
- Optional email parameter (`email?: string`) to the following authentication actions: `verifyResetCode`, `setPassword`
- `TextInput` and `TextInputSecure` can optionally accept a testID property
-   `AuthUIContextProvider` has a `eulaIsHtml` property allowing the EULA to be displayed as text or as HTML

### Changed
-   The return of the `validateUserRegistrationRequest` action to be `Promise<boolean>`
-   README deep link documentation: `Note: It is recommended to update navigation > DeepLinking.ts to include the initialRouteParam in the config if you haven’t already` referring to [stack-navigator documentation](https://reactnavigation.org/docs/stack-navigator/#initialroutename)
-   Deep Link parameters have changed from `verificationCode`, `validationCode`, and `verifyCode` to `code`
-   EULA now supports HTML content in addition to plaintext

## v1.0.0
### Changed
- Package published under the @pxblue scope and made publicly available
- Removed internal theming to defer to the end-user application theme
- Removed dependency on react-native-elements

## v0.2.3
### Added

- iOS and Android icons
- Support for setting language based on device's locale
- More strong typing
- Script for example to use local code first, but if moved out of the folder it will use the node_module folder

### Fixed

- Next button state on first screen of self registration

### Changed

- Define tighter dependencies
- Prevent users who reach the email verification step in self registration from jumping back in the flow
- Email regex
- Use PX Blue Typography for most textual elements
- Significant documentation clarifications

## v0.2.1
### Added

- Deep link support
- TypeDoc code documentation generation and folder
- Additional testing of new components
- `yarn precommit` task for code validation, testing, code documentation generation, and licenses generation
- Documentation for mock actions within the examples folder

### Fixed

- Change Password keyboard overlaying text input
- Status bar colours across iOS and Android
- Enable state of EULA accept button when EULA is not loaded
- Resolved additional TODOs and FIXMEs throughout the code

### Changed

- Updated README with more specific integration information
- Refactored contexts for global authentication and registration states and actions
- Moved extra strings into the english.ts translations file and added TODOs for missing French translations

## v0.2.0
### Added
- Networking mocks for examples
- Error handling for all networking
- UI and unit tests
- Rename applications to AuthUIExample
- Embed ChangePassword in AuthNavigator
- Debug mode
- Ability to configure external options showSelfRegistration, allowDebugMode, contactEmail, contactPhone, projectImage at a high level
- Support for a wider array of screen sizes
- Packaging for NPM
- Validation tasks
- Ability to launch UI from a provided code

### Fixed
- UI fixes
- Images not loading in Android (React Native bug workaround)
- Handle Android back button
- Sentence case all buttons
- Linting and prettifying

### Changed
- Rearchitecture Android and iOS examples into separate directory
- Refactor security context
- Replace promises with await/async pattern

## v0.1.0
### Added
- Initial beta release
