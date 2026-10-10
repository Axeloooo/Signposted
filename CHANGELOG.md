## 1.0.0 (2026-10-10)

### Features

* add multi-agent trip planner (FastAPI, LangGraph, Groq, PostgreSQL) ([bb3ab48](https://github.com/Axeloooo/Signposted/commit/bb3ab484163767caef707e530057ab9f2f84d43d))
* add Waywise web UI templates ([#4](https://github.com/Axeloooo/Signposted/issues/4)) ([f555f78](https://github.com/Axeloooo/Signposted/commit/f555f7808b90dd289bb2f51ec88cea45771e7ce3))
* rebuild web UI as the T-A terminal board ([#5](https://github.com/Axeloooo/Signposted/issues/5)) ([e29c8f8](https://github.com/Axeloooo/Signposted/commit/e29c8f8a15bf011b836b337f095070eb8db81510))
* release 2026-10-10 ([#10](https://github.com/Axeloooo/Signposted/issues/10)) ([dc694ad](https://github.com/Axeloooo/Signposted/commit/dc694ad22ac421e0a699a145c9a3a2a496ffdb66))
* wire the web UI to the API and add deployment config ([#12](https://github.com/Axeloooo/Signposted/issues/12)) ([c096872](https://github.com/Axeloooo/Signposted/commit/c0968728e0df38f6f13d762941c35053155d12c4))

### Bug Fixes

* allow release branches into main ([#11](https://github.com/Axeloooo/Signposted/issues/11)) ([a07a77e](https://github.com/Axeloooo/Signposted/commit/a07a77e37a71c8b39b5aaabdbe65a5aad2b6e84d))
* harden planner with 502 handling, revision context and input limits ([b866f9e](https://github.com/Axeloooo/Signposted/commit/b866f9e6518b1a01c0c6741f6dca66b2c2fe7660))
* resolve mypy errors in llm and agent nodes ([dc32330](https://github.com/Axeloooo/Signposted/commit/dc3233020f11bdba11dfbfbd1e771ffa86aa47b4))
* use release token for semantic-release ([#16](https://github.com/Axeloooo/Signposted/issues/16)) ([907c338](https://github.com/Axeloooo/Signposted/commit/907c3384abaa9aa25bae0e9f47985f86e4d5f965))

### Infrastructure

* add linting, formatting, pre-commit, CI and semantic-release tooling ([7f27d9f](https://github.com/Axeloooo/Signposted/commit/7f27d9f48ad785282a8085646107ed17c96353b4))
* drop vendored figma skills pending license ([1a80e59](https://github.com/Axeloooo/Signposted/commit/1a80e59d4d8d90ec9c1598e8843be75a53043724))
* fix release rules, back-merge and CI title checks ([32ae1f6](https://github.com/Axeloooo/Signposted/commit/32ae1f69e9ec2ee79f4cba1117ead42742903e69))
* forbid AI attribution trailers in commit messages ([c0660f2](https://github.com/Axeloooo/Signposted/commit/c0660f2930479e237bbcfc3c8cceed8d3b626f2e))
* reject AI trailers in CI and bind compose Postgres to localhost ([#2](https://github.com/Axeloooo/Signposted/issues/2)) ([6796c77](https://github.com/Axeloooo/Signposted/commit/6796c773a8fd16e443da243fd82338dae8c3a6b5))
* restructure into apps/api monorepo layout ([8f1f552](https://github.com/Axeloooo/Signposted/commit/8f1f55211df123e681ad47db81356658aead4c3c))
* revert CI trailer check and Postgres localhost binding ([#3](https://github.com/Axeloooo/Signposted/issues/3)) ([4f1857e](https://github.com/Axeloooo/Signposted/commit/4f1857e4cdaea8316d980ff83cb7ff2020bae8a0))
* scope black and ruff hooks to apps/api ([1a6cf34](https://github.com/Axeloooo/Signposted/commit/1a6cf34a2fed45a3ae7bef0ba73f41ea74fe988f))
* simplify release workflow to built-in GITHUB_TOKEN ([#17](https://github.com/Axeloooo/Signposted/issues/17)) ([36a3016](https://github.com/Axeloooo/Signposted/commit/36a301621b4aafbe6f0a04df0f4458470ba12758))
* use RELEASE_TOKEN for semantic-release ([#15](https://github.com/Axeloooo/Signposted/issues/15)) ([9bbd421](https://github.com/Axeloooo/Signposted/commit/9bbd42163efd6098ddcdda619d2d9dab443eb496))
* vendor plugin skills into .claude/skills ([78770a0](https://github.com/Axeloooo/Signposted/commit/78770a05faa7e331bef9cfd4c338ea55d3460cf2))

### Documentation

* add CLAUDE.md and contributing guide ([f3059f7](https://github.com/Axeloooo/Signposted/commit/f3059f79be9beacae8d5a6a619e6b24a676dc2fc))
* rename to Signposted and describe squash-merged release flow ([#6](https://github.com/Axeloooo/Signposted/issues/6)) ([db9ef53](https://github.com/Axeloooo/Signposted/commit/db9ef53ed58e8599fd78ba152bc7abffce132821))
* say squash-merge when syncing main back into devel ([#8](https://github.com/Axeloooo/Signposted/issues/8)) ([b4ba347](https://github.com/Axeloooo/Signposted/commit/b4ba347ff7f6cec1043212e678cf910fd27546ee))
