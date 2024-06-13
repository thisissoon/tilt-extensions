# Overview

This extension contains functions for use along with the Google Cloud PubSub emulator.

Please see the [example](./example/Tiltfile) for usage. Functions within the Tiltfile are fully documented if you need any further details.

# Prerequisites

This extension requires you to be running the Google Cloud PubSub emulator, via your `docker-compose.yaml` file for example;

```
pubsub-emulator:
    image: gcr.io/google.com/cloudsdktool/google-cloud-cli:emulators@sha256:7da...
    command:
      - gcloud
      - beta
      - emulators
      - pubsub
      - start
      - --project=ecom-store
      - --host-port=0.0.0.0:8999
    stdin_open: true
    tty: true
    ports:
      - "8999:8999"
```
