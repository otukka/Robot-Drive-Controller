# CLAUDE.md

Guidance for Claude Code when working in this repository.

## Project overview

Drive controller for an Ackermann steering robot, running on an Onion Omega2S
and commanded by a ROS 2 PC over Wi-Fi or Ethernet. See [README.md](README.md)
and [docs/](docs/). Hardware specs are in [docs/hardware.md](docs/hardware.md)
only; don't duplicate them here.

- ROS 2 runs on the PC only. Keep the controller free of ROS dependencies.
- micro-ROS on the Omega2S is not an option. Don't suggest it.
- Transport: a custom lightweight protocol, with a ROS 2 bridge node on the PC.
  See [docs/architecture.md](docs/architecture.md).

## Tech stack

- Language: C++, C++17 at minimum. Don't use features that need a newer
  standard unless the project's minimum is raised.
- Toolchain: OpenWrt SDK cross-compiler for the Omega2S (`mipsel-openwrt-linux-musl-g++`).
  See [docs/getting-started.md](docs/getting-started.md).

## Repository layout

```
docs/   project documentation
TODO
```

## Commands

```sh
# Build:  TODO
# Test:   TODO
# Deploy: TODO
# Format: clang-format -i <files>
# Lint:   TODO
```

## Conventions

- Code style: format all C++ sources with `clang-format`, using the repo's
  [.clang-format](.clang-format). Run it on changed files before finishing a task.
- _TODO: naming, error handling_
- Commit messages: a short one-line description. End with a `Co-Authored-By:`
  trailer crediting the AI agent that helped, e.g.
  `Co-Authored-By: Claude Opus 5.5 <noreply@anthropic.com>`.

## Testing

- _TODO: how to test without hardware (mocks/simulation) and on the board_

## Notes for Claude

- Motor and servo outputs must default to a safe state (stopped, steering
  centred) on startup, on exit, and when commands time out, including after
  network loss.
- Keep dependencies and binary size small. The target is resource-constrained.
- Don't run code that drives motors on real hardware without asking first.
- Don't stage files (`git add`) or create git commits unless explicitly asked.
- Don't write a monolithic README. Put documentation in `docs/`, one file per
  topic, and keep README.md a short intro with links to those files.
