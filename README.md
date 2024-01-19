# `ghcr.io/amp-buildpacks/scarb`

A Cloud Native Buildpack for scarb

## Configuration

| Environment Variable     | Description                                                                                                                                                                                                                                                                                     |
|--------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `$BP_SCARB_VERSION`        | Configure the version of Scarb to install. It can be a specific version or a wildcard like `2.4.3`. It defaults to the latest `2.*` version.                                                                                                                                                    |
| `$BP_SCARB_LIBC`         | Configure the libc implementation used by the installed toolchain. Available options: `gnu` or `musl`. Defaults to `gnu` for compatiblity. You do not need to set this option with the Paketo full/base/tiny/static stacks. It can be used for compatibility with more exotic or custom stacks. |
| `$BP_ENABLE_SCARB_PROCESS` | Configure the Scarb launch process, default: `false`. Set to `true` means execute the `scarb run` command.                                                                                                                                                                                      |

Usage

### 1. To use this buildpack, simply run:

```shell
pack build <image-name> \
    --path <cairo-path> \
    --buildpack ghcr.io/amp-buildpacks/scarb \
    --builder paketobuildpacks/builder-jammy-full
```

For example:

```shell
pack build scarb \
    --path ./samples/hello_scarb \
    --buildpack ghcr.io/amp-buildpacks/scarb \
    --builder paketobuildpacks/builder-jammy-full
```

### 2. To run the image, simply run:

```shell
docker run -u <uid>:<gid> -it <image-name>
```

For example:

```shell
docker run -u 1001:cnb -it scarb
```

## Contributing

If anything feels off, or if you feel that some functionality is missing, please
check out the [contributing
page](https://docs.amphitheatre.app/contributing/). There you will find
instructions for sharing your feedback, building the tool locally, and
submitting pull requests to the project.

## License

Copyright (c) The Amphitheatre Authors. All rights reserved.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

      https://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.

## Credits

Heavily inspired by https://github.com/paketo-community/rustup