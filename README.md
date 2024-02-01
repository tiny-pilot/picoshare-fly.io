# picoshare-fly.io

[![CircleCI](https://circleci.com/gh/tiny-pilot/picoshare-fly.io.svg?style=svg)](https://circleci.com/gh/tiny-pilot/picoshare-fly.io)
[![License](http://img.shields.io/:license-mit-blue.svg?style=flat-square)](LICENSE)

## Overview

This repo controls deployments to TinyPilot's [PicoShare](https://github.com/mtlynch/picoshare) instance on Fly.io.

## Purpose

TinyPilot uses PicoShare as a simple way to share files within the company and with external partners.

PicoShare doesn't do well on [files larger than 1 GB](https://github.com/mtlynch/picoshare/issues/355), but it's convenient for files that are too large for an email attachment and too small to be worth the trouble of uploading to Backblaze.

## Updating PicoShare versions

To update to a new version of PicoShare, create a PR that updates the version of the `build.image` property within the `fly.toml` file.

When the PR is merged, CircleCI will automatically deploy the new version of PicoShare. TinyPilot's files on PicoShare will persist due to the persistent volume (specified in the `mounts` property of `fly.toml`).
