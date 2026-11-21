# AIGROW provider for Agent Zero

Use [AIGROW](https://aigrow.gg/ai-api) models in [Agent Zero](https://github.com/agent0ai/agent-zero) as a chat
model provider.

AIGROW is a prepaid API for Claude, GPT, Gemini, Grok, Qwen and Kimi models with an OpenAI-compatible endpoint.
AIGROW maintains this plugin. It is not affiliated with Agent Zero.

## Why a plugin?

Agent Zero can reach AIGROW through its "Other OpenAI compatible" option. This plugin adds **AIGROW** to the
provider dropdown, sets the base URL, and maps your key to `AIGROW_API_KEY`.

## Install

Install **AIGROW Provider** from the Plugin Hub in Agent Zero.

## Configure

1. Create a key at [aigrow.gg/dashboard/api](https://aigrow.gg/dashboard/api). Requests are paid from prepaid
   credit.
2. In Agent Zero, open **Settings** → **Models** → **Edit Presets**.
3. Under **Main Model**, set **Provider** to **AIGROW**, choose a model such as `claude-haiku-5.5`, and paste
   your key into **API key**.
4. To run Agent Zero's background tasks on AIGROW as well, set **Utility Model** the same way, for example
   `claude-haiku-5.5`. The key carries over.
5. Click **Save**.

## Models

Agent Zero reads the list from `https://aigrow.gg/v1/models`. Model ids have no vendor prefix, for example:

| Model | Family |
|---|---|
| `claude-haiku-5.5`, `claude-sonnet-5.5`, `claude-opus-5.5` | Anthropic Claude |
| `gpt-6.2-sol`, `gpt-6.2-astra` | OpenAI GPT |
| `gemini-4-neon`, `gemini-3.8-flash` | Google Gemini |
| `grok-4.7` | xAI Grok |
| `qwen3.8-max` | Qwen |
| `kimi-k3.1-pro` | Kimi |

The full list with per-token prices is public at `https://aigrow.gg/v1/models` (no key needed) and on
[aigrow.gg/ai-api](https://aigrow.gg/ai-api). Each model is checked against its maker's own endpoint with a
public script; the results are at [aigrow.gg/ai-api/genuine-models](https://aigrow.gg/ai-api/genuine-models).

## Security and footprint

- **Network:** Agent Zero sends your requests, including prompts and any files or images in them, to
  `https://aigrow.gg` using your AIGROW key. See the [privacy policy](https://aigrow.gg/privacy).
- **Code:** the plugin holds only configuration: 1 provider entry. It runs no code, adds no tools, and has no
  dependencies.
- **Credentials:** Agent Zero holds the key. The plugin stores no secrets.
- **Telemetry:** the plugin sends no telemetry.

## Remove

Remove the plugin from Agent Zero's plugin settings. Your other providers stay as they are.

## License

MIT
