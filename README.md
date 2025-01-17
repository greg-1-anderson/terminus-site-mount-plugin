# Terminus Site Mount Plugin

[![CircleCI](https://circleci.com/gh/terminus-plugin-project/terminus-site-mount-plugin.svg?style=shield)](https://circleci.com/gh/terminus-plugin-project/terminus-site-mount-plugin)
[![Terminus v1.x Compatible](https://img.shields.io/badge/terminus-v1.x-green.svg)](https://github.com/terminus-plugin-project/terminus-site-mount-plugin/tree/1.x)

Terminus plugin to mount [Pantheon](https://pantheon.io/) site environments.

## Usage:
```
terminus [site:]mount|[site:]u(n)mount site-name.env [--dir=<directory>]
```

By default, the site environment will be mounted in `/tmp/site-name.env`.

If you want to mount in a different directory, use the `--dir=<directory>` option.

Keep in mind, if you mount in a different directory, you will also need to specify the same `--dir` option when unmounting.

## Examples:
Mount the site environment awesome-site.dev.
```
terminus mount awesome-site.dev [--dir=<directory>]
```

Unmount the site environment awesome-site.dev.
```
terminus unmount awesome-site.dev [--dir=<directory>]
```

Learn more about [Terminus](https://pantheon.io/docs/terminus/) and [Terminus Plugins](https://pantheon.io/docs/terminus/plugins/).

## Prerequisites:

Executable mount, umount and sshfs commands must exist.

### Mac OSX:

- Download and install the latest release of [osxfuse-x.x.x.dmg](https://github.com/osxfuse/osxfuse/releases).
- Install sshfs via `brew install sshfs`

### Linux:

- Debian-based (Debian, Linux Mint, Ubuntu and derivatives): `sudo apt-get update && sudo apt-get install sshfs`
- RedHat-based (RedHat, Fedora, CentOS and derivatives): `sudo yum install sshfs`

## Installation:
For installation help, see [Extend with Plugins](https://pantheon.io/docs/terminus/plugins/).

```
mkdir -p ~/.terminus/plugins
composer create-project -d ~/.terminus/plugins terminus-plugin-project/terminus-site-mount-plugin:~1
```

## Configuration:

This plugin requires no configuration to use.

## Testing:

Replace `my-test-site` with the site you want to test:
```
export TERMINUS_SITE=my-test-site
cd ~/.terminus/plugins/terminus-site-mount-plugin
composer install
composer test
```

## Help:
Run `terminus help site:mount` for help.
