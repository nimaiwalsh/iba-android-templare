# android-app-template
A template Android Application Project.

# After cloning the template

### Altering the project name and namespace

Several project files refer to the "Android App Template", and each Kotlin file declares itself part
of the `com.ittybittyapps.apptemplate.android` package. Update these files to suit the client's new
application.

- In `app/build.gradle`, modify `android.namespace` and `android.defaultConfig.applicationId`.
- Change the `rootProject.name` variable in `settings.gradle`.
- Rename the app's themes in `Theme.kt` and `themes.xml`.
- In `strings.xml`, set the `app_name` string resource.
- Update the package declarations in all Kotlin files by performing a project-wide find and
  replace of `com.ittybittyapps.apptemplate.android`.
- Update the package name `com.ittybittyapps.apptemplate` in `continuous-deployment.yml`.

### Github Actions
Configure Github secrets for `IBA_GOOGLEPLAY_KEYSTORE`, `IBA_GOOGLEPLAY_KEYSTORE_PASSWORD`,
`IBA_GOOGLEPLAY_KEYSTORE_KEY_ALIAS`, `IBA_GOOGLEPLAY_KEYSTORE_KEY_PASSWORD` and 
`GOOGLEPLAY_SERVICE_ACCOUNT`.

See `continuous-deployment.yml` for more information.

If the deployment workflow is not yet required, you can disable the action manually in Github.

# Building and testing
Build and run
```shell
./gradlew assembleDebug
./gradlew installDebug
```

Unit test 
```shell
./gradlew testDebugUnitTest
```

Instrumentation test
```shell
./gradlew connectedandroidtest
```
