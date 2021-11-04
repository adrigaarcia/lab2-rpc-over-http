# Solution

## Running Server and Client

In order to run the app, first, the server must be built and started:

```console
.\gradlew :server:build
.\gradlew :server:bootRun
```

Then we can proceed to do the same with the client:

```console
.\gradlew :client:build
.\gradlew :client:bootRun
```

After running these commands, we can see that an error appears in the client, saying something went wrong in the server. This error is due to the missing function translation.

## Solving the server error

To solve this error, we must implement the missing function translation, with the code below:

```kotlin
fun translation(@RequestPayload request: TranslationRequest): TranslationResponse = 
        TranslationResponse().apply {
            translation = "¡Traduceme!"
        }
```

## Adding CI to work branch

After creating the work branch, the CI.yml file must be modified to include the new branch in the CI process.
By doing this, the app is being built everytime we push the work branch.
