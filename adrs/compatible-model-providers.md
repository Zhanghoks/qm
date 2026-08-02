# OpenAI / Anthropic-compatible providers

Hey — undergrad in China here. Same person as the Chinese docs note. I've been
getting into agents a lot, and qm pulled me in on the distributed agent
collaboration side.

Quick thought on models. Today the product surface is basically anthropic /
openai / openrouter. Fine if you already live there. A lot of folks around me
can't use Anthropic cleanly, already have some other coding plan or gateway, or
want a local / self-hosted OpenAI-compatible box. OpenRouter helps for variety,
but it doesn't cover "I need my own base URL" or "my team's model only speaks
this compatible API."

What I'd actually want is closer to CC Switch's idea: not an endless hard-coded
vendor list, but a couple of wire protocols you can point at anything that
speaks them.

Rough ask (you own the design — just the shape that would help):

- Org admin registers a provider as OpenAI-compatible or Anthropic-compatible,
  with base URL + API key, plus which model ids should show up.
- A few presets to make setup less painful — DeepSeek, Kimi/Moonshot, MiniMax,
  xAI/Grok as examples, not the whole universe.
- Once admin turns them on and the org allowlist includes those models, people
  just use the existing web-ui model picker. No new switcher UI needed.
- Regular users shouldn't paste arbitrary base URLs — admin-only keeps that
  safer.

That way it's easier to try qm with keys or endpoints people already have,
including places where Anthropic isn't an option, without waiting for every new
vendor to become a first-class enum.

Text only from me. If the direction sounds right, happy to help test against
real compatible endpoints once something's there.
