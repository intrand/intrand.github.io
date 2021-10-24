# relay-webhook

`relay-webhook` was a service to receive a webhook and push it to another place, often changing the structure. It started as a way to transform and forward [docker hub](https://hub.docker.com) automated build webhooks to discord webhooks so I could get updates inside discord every time an automated build finished.

## Design

`relay-webhook` acted like a filtering proxy between the public Internet and my own services. It was a simple program that listened for web requests, looked at a config file and decided where to send it. The `relay-webhook` service ran in my kubernetes cluster behind an ingress controller.

## Status

Abandoned. I stopped using everything that used to send webhooks to `relay-webhook`, so there's no point in maintaining it anymore.
