# SocialMedia Manager

> A local-first video studio and publishing control room for social media teams.

## Live Demo

Deployment is being verified. The production URL will be published here after the hosted runtime passes its smoke checks.

## Overview

SocialMedia Manager turns a content idea into a reviewable short-form video workflow: structured script, scene plan, rendered MP4, approval gate, and platform publishing. The product is designed around explicit human approval and operational safety rather than blind automation.

## Highlights

- AI-assisted script and scene generation
- Real FFmpeg video rendering with captions, thumbnails, and manifests
- Visual style and series consistency workflows
- Facebook Pages, Instagram professional accounts, and YouTube publishing adapters
- Retryable partial-failure handling with idempotency protection
- Topic bank, queue, scheduler, and autopilot safety rails
- Mock mode for local evaluation without external credentials

## Technology

- **Application:** Next.js 15, React 19, TypeScript
- **Data:** Prisma with SQLite for the local-first runtime
- **Media:** FFmpeg, ffprobe, local media storage, optional stock and AI providers
- **Integrations:** Meta Graph API, YouTube Data API, optional ComfyUI and Kaggle generation
- **Operations:** Node.js worker for jobs, scheduling, and automation

## Architecture

```text
Idea
  -> generation pipeline
  -> scenes and media assets
  -> FFmpeg render
  -> approval gate
  -> platform adapters
  -> independent publication status and retry
```

The full implementation remains private. This repository is the public portfolio presentation and intentionally contains no production credentials or private application source.

## Engineering Notes

The workflow is built around explicit state transitions, per-platform publication records, idempotency keys, retry of failed platforms only, and a mock provider suite that exercises the critical publishing paths without requiring live social accounts.

## Project Status

Local production build and test suite verified. Public hosting is being configured and will be linked here once the live demo is independently smoke-tested.

## Ownership

Built by **[@ulasmango-cmd](https://github.com/ulasmango-cmd)**.

- Private source repository: [socialmedia-manager-source](https://github.com/ulasmango-cmd/socialmedia-manager-source)
- GitHub profile: [github.com/ulasmango-cmd](https://github.com/ulasmango-cmd)

## License

The production implementation is private and proprietary. This portfolio repository contains documentation and project presentation material only.
