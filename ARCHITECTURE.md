# Architecture Overview

SocialMedia Manager is organized as a local-first control room with a clear boundary between content generation, media processing, approval, and publishing.

## Flow

1. A user creates a project from an idea.
2. The generation pipeline produces structured metadata and scenes.
3. Renderers create local MP4, subtitle, thumbnail, and manifest assets.
4. The user approves the project.
5. Platform adapters publish independently and record separate outcomes.
6. Failed publications can be retried without duplicating successful platforms.
7. The worker handles queued jobs, scheduling, and guarded automation.

## Safety Model

- Publishing requires an explicit approval state.
- Platform results are isolated per publication.
- Idempotency keys prevent duplicate posts.
- Daily limits, quiet hours, account pauses, and failure circuit breakers constrain automation.
- Mock providers allow workflow testing without real credentials.

## Deployment Considerations

The complete application uses a persistent Node process, filesystem-backed media processing, a database, and a worker. A hosted production deployment therefore needs a persistent backend/runtime and durable database/media storage. A static or serverless frontend-only deployment is not a substitute for the full application runtime.
