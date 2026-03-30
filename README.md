# The Eagles — Good Samaritans of Wichita

A fully populated demo community portal built on [Wild Lychee](https://github.com/kychee-com/wildlychee) + [Run402](https://run402.com).

**Live demo: https://eagles.run402.com**

Everything is AI-generated — member photos, event images, logo, all text content. This is a showcase of what a Wild Lychee community portal looks like with real-feeling data.

## What's in the demo

| Feature | Count |
|---------|-------|
| Members with AI-generated avatars | 28 |
| Events (upcoming + past) | 12 |
| Forum categories | 5 (18 topics, 56 replies) |
| Committees with members | 6 (37 assignments) |
| Announcements | 10 (2 pinned) |
| Resources | 15 |
| Newsletter drafts | 2 |
| Activity log entries | 40 |
| AI-generated images | 36 |

## Deploy

Requires the [Run402 CLI](https://run402.com):

```bash
node deploy.js
```

Override the project ID:

```bash
EAGLES_PROJECT_ID=prj_xxx node deploy.js
```

## Regenerate images

Requires an OpenAI API key with gpt-image-1.5 access:

```bash
OPENAI_API_KEY=sk-... bash generate-images.sh
```

Then upload to Run402 storage:

```bash
for f in assets/*; do
  run402 storage upload $PROJECT_ID assets "$(basename $f)" --file "$f"
done
```

## Built with

- [Wild Lychee](https://github.com/kychee-com/wildlychee) — community portal template
- [Run402](https://run402.com) — serverless platform (database, auth, functions, storage, hosting)
- [OpenAI gpt-image-1.5](https://platform.openai.com) — AI image generation
