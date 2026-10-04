# ReelGenie publishing skill for Codex

Create original social posts in Codex, keep each brand's brief and finished media in ReelGenie, and review each Post before choosing whether to publish.

This repository distributes ReelGenie's [official publishing skill](https://reelgenie.app/reelgenie-codex-skill.md). The service holds workspace guidance, team Favourites, finished media, captions and delivery results. Codex supplies the creative tools available in your plan.

## Install

From the project where you use Codex:

```sh
npx skills add reelgenieapp/reelgenie-skill --skill reelgenie-v4-publishing --agent codex
```

Review the install prompt and choose the scope you want. This installs the skill instructions. Connecting your ReelGenie workspace is a separate, user-approved setup step; installing this package does not create an account, authorize access or publish a Post.

You can also start from [ReelGenie's Codex setup page](https://reelgenie.app/codex) and copy its setup prompt into Codex. If skills or newly configured MCP tools do not appear, start a fresh Codex turn or session as your client requires.

## Try one private Post

Ask Codex:

> Set up ReelGenie and help me prepare my first post for private review. Keep publishing paused until I approve the final Post, account, delivery mode and timing.

The skill guides sign-in, a scoped MCP connection, workspace guidance and the first Post. You can prepare a private Post before connecting a social account. Inspect the actual images and full caption in the review page.

## Keep brands separate

For each workspace, the skill retrieves its audience, product, voice, goals and boundaries before planning creative. Saved Favourites guide visual style; they do not replace the brand brief.

[See the two-brand example](https://reelgenie.app/guides/multiple-brands-with-codex). This is a demonstration using our own workspaces, not a customer-growth or time-saving benchmark.

## Supported delivery

- Instagram: eligible images and video, subject to connected-account permissions
- TikTok: inbox drafts that you finish inside TikTok
- YouTube: eligible finished video

The service reports each destination separately. Queue acceptance or a TikTok inbox draft is not proof of a live public post. ReelGenie does not generate video. This package documents the Codex workflow; compatibility with other agents has not been established here.

## Authentication and data

The service uses Streamable HTTP MCP at `https://reelgenie.app/api/mcp`. A team admin creates a revocable token in the console and scopes it to the intended workspace. Standard content permissions can create review Posts; approve/publish is a separate opt-in.

Complete sign-in, provider consent and protected token entry yourself. Use an approved environment or secret manager; the documented environment-variable name is `REELGENIE_MCP_TOKEN`. Never paste the token into chat, a public issue, a URL or a committed file. Authenticated `reelgenie_health` proves the connection; a saved configuration alone does not.

Using the connected service sends the workspace content and operations you authorize to ReelGenie. Approved delivery sends the chosen media and copy to your connected platform. See the [privacy policy](https://reelgenie.app/privacy) and [terms](https://reelgenie.app/terms).

## Reference permissions

Before saving a reference or uploading files, confirm the intended ReelGenie team/workspace and the user's permission to store those materials there. Private review means the Post is not yet published to social media; it is still stored in the service under the workspace's existing access controls. Use original copy or material the user has rights to reuse. A skill never overrides the user's permissions or the agent's safety rules.

## Cost

ReelGenie's free plan includes ten Posts per team per UTC day and two workspaces. Codex access and image-generation limits are separate. [Current product and plan details](https://reelgenie.app/).

## Updates and scope

`SKILL.md` is a byte-for-byte copy of the official hosted skill at the time of this release. The skill checks that same official HTTPS source once at the start of a new ReelGenie task; review its update behavior before installing. This repository contains only public skill documentation, not the application implementation.

Report package or documentation issues in this repository. Do not include credentials, personal workspace contents or customer data in reports.

## License

The skill and documentation in this repository are available under the [MIT license](LICENSE). This grant does not include the ReelGenie application implementation, trademarks, third-party content or service access.
