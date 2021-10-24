# watchdog

`watchdog` is a service to inform you when other things stop checking in regularly.

## Design

`watchdog` has a single `api` component that listens for routine requests and reacts when they stop coming after some pre-determined timeout, usually by sending an alert in the form of an email or webhook. There is no registration necessary. Configuration can be adjusted however the requester prefers. There is currently zero security with this project, although it would be straightforward to change.

## Status

Shelved. I don't have time to maintain this right now. I've also stopped hosting my own stuff, so I no longer have a need for this. Perhaps in the future I will work on this again, as I'm aware there are paid options out there, but I'm not aware of any free and open source options.
