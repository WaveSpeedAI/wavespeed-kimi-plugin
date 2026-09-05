# WaveSpeed plugin for Kimi Code CLI

A [Kimi Code CLI](https://github.com/MoonshotAI/kimi-code) plugin that lets the agent generate and edit AI media — image, video, audio, 3D — on the [WaveSpeed](https://wavespeed.ai) platform.

It bundles two things:

- **MCP server** — [`@wavespeed/mcp`](https://github.com/WaveSpeedAI/mcp-server), started with `npx`. Tools: `search_models`, `get_model_schema`, `get_price`, `upload_file`, `run_model`, `get_prediction`, `get_balance`.
- **Skill** — the same `wavespeed` skill that ships with the open-source [`@wavespeed/cli`](https://github.com/WaveSpeedAI/wavespeed-cli). It teaches the agent the find → inspect → run pattern: search the live catalog, read any model's input schema, execute it, upload local files with the `@path` marker, and quote prices before spending credits.

## Install

Inside Kimi Code:

```
/plugins install https://github.com/WaveSpeedAI/wavespeed-kimi-plugin
```

Then `/reload` (or start a new session). `/plugins` shows it under Installed.

## Requirements

- Node.js ≥ 18 (`npx` runs the MCP server on demand, nothing to install by hand)
- A WaveSpeed account. Either set `WAVESPEED_API_KEY` in your environment, or install the CLI (`npm install -g @wavespeed/cli`) and run `wavespeed login` once — one login covers both the MCP server and the CLI. Keys live at [wavespeed.ai/accesskey](https://wavespeed.ai/accesskey).

## What the agent can do with it

- *"Generate a 16:9 hero image of a cyberpunk skyline at golden hour."*
- *"Animate ./hero.jpg into a 5-second clip with subtle parallax."*
- *"Replace the background of ./product.png with a sunlit kitchen."*
- *"How much would a 10-second 1080p video cost before you run it?"*

Recommended starting models: `bytedance/seedream-v5.0-pro` for images, `wavespeed-ai/minimax-h3/*` for video (cheap, open-weights, native audio), `bytedance/seedance-2.5/*` when you need the highest video quality. The agent browses everything else with `search_models`.

## Same skill, other agents

- Claude Code: [WaveSpeedAI/claude-plugins](https://github.com/WaveSpeedAI/claude-plugins)
- Cursor / Codex / OpenCode: `wavespeed skill install`
- Gemini CLI: [WaveSpeedAI/wavespeed-gemini-extension](https://github.com/WaveSpeedAI/wavespeed-gemini-extension)
- DeepSeek Harness: [WaveSpeedAI/wavespeed-dsh-skill](https://github.com/WaveSpeedAI/wavespeed-dsh-skill)

## License

[MIT](LICENSE) — same as the CLI and the MCP server.

---

**[WaveSpeedAI](https://wavespeed.ai/)** — AI image & video generation platform.
Try it in the browser: **[Image generator](https://wavespeed.ai/image-generator)** · **[Video generator](https://wavespeed.ai/video-generator)**
