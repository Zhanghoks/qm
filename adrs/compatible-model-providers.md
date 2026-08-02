# OpenAI / Anthropic-compatible providers (like CC Switch)

Hey — undergrad in China here. Same person who poked at the Chinese docs entry.
I'm into agents and got interested in qm for the distributed collaboration side.

Right now the product surface is basically anthropic / openai / openrouter. That
works if you already live on those three, but a lot of people I know can't use
Anthropic cleanly, already pay for some other coding plan or gateway, or want a
local / self-hosted OpenAI-compatible endpoint. OpenRouter helps for variety, but
it doesn't cover "I need my own base URL" or "my team's model is only on this
compatible API."

What I'd love is closer to how CC Switch thinks about it: not an endless list of
hard-coded vendor enums, but a small number of wire protocols people can point
at anything that speaks them.

Rough shape (implementation is yours — this is just the ask):

- Org admin can register providers as OpenAI-compatible or Anthropic-compatible,
  with base URL + API key (and whatever model ids should show up).
- A few presets would lower the setup cost — e.g. DeepSeek, Kimi/Moonshot,
  MiniMax, xAI/Grok — as starting points, not as the only universe.
- After admin enables them and the org allowlist includes the models, people use
  the existing web-ui model picker. No need for a new switcher UI.
- Regular users shouldn't paste arbitrary base URLs; admin-only keeps the blast
  radius sane.

That would make it easier to try qm with keys or endpoints people already have,
including setups where Anthropic isn't an option, without waiting for every new
vendor to land as a first-class enum.

I'm not shipping code in this PR — CONTRIBUTING says text is the right form. If
the direction makes sense, happy to help test against real compatible endpoints
once something lands.
