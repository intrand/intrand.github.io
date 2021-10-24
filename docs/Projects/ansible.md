# ansible

`ansible` is upstream `ansible` inside of a container.

## Design

`ansible` is just a Dockerfile with some dependencies for commonly-used `ansible` modules installed alongside `ansible` itself. Typically one would run `ansible-playbook` but all of the core tools are available in the same container image.

## Status

Useful, but I stopped hosting my own stuff, so there's presently little to no need for `ansible`.
