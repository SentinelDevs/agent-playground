# Ad Service

The Ad service provides advertisement based on context keys. If no context keys
are provided then it returns random ads.

## Features

- **Context-based targeting**: Serves ads based on provided context keys
- **Response caching**: Caches ad responses to improve performance and reduce lookup time
- **Fallback mechanism**: Returns random ads when no targeted ads are available
- **OpenTelemetry integration**: Full observability with traces, metrics, and logs

## Building Locally

The Ad service requires at least JDK 17 to build and uses gradlew to
compile/install/distribute. Gradle wrapper is already part of the source code.
To build Ad Service, run:

```sh
./gradlew installDist
```

It will create an executable script
`src/ad/build/install/oteldemo/bin/Ad`.

To run the Ad Service:

```sh
export AD_PORT=8080
export FEATURE_FLAG_GRPC_SERVICE_ADDR=featureflagservice:50053
./build/install/opentelemetry-demo-ad/bin/Ad
```

### Upgrading Gradle

If you need to upgrade the version of gradle then run

```sh
./gradlew wrapper --gradle-version <new-version>
```

## Building Docker

From the root of `opentelemetry-demo`, run:

```sh
docker build --file ./src/ad/Dockerfile ./
```
