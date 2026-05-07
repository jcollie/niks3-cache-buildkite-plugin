<!-- SPDX-FileCopyrightText: © 2024 Jeffrey C. Ollie <jeff@ocjtech.us> -->
<!-- SPDX-License-Identifier: MIT -->

# Enable caching of your Nix builds on your Buildkite agent using niks3

## Example

```yml
secret:
  - NIKS3_AUTH_TOKEN

steps:
  - command: nix build .#myproject
    plugins:
      - jcollie/niks3-cache#v1.0.0:
          cache_url: https://cache.example.org/
          server_url: https://niks3.example.org/
          public_key: cache.example.org-1:6NCHdD59X431o0gWypbMrAURkbJ16ZPMQFGspcDShjY=
```

## Configuration

## Developing

### BuildKite tests

To run the tests:

```shell
podman run -it --rm -v "$PWD:/plugin:ro" docker.io/buildkite/plugin-linter --id jcollie/niks3-cache
```
