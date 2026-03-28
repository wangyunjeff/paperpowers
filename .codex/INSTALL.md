# Installing Paperpowers for Codex

Enable `paperpowers` skills in Codex through native skill discovery.

## Prerequisites

- Git

## Installation

1. Clone this repository into your Codex directory:

   ```bash
   git clone /Users/wangyunjeff/0_CODE/paperpowers ~/.codex/paperpowers
   ```

2. Create the skills symlink:

   ```bash
   mkdir -p ~/.agents/skills
   ln -s ~/.codex/paperpowers/skills ~/.agents/skills/paperpowers
   ```

3. Restart Codex so it rediscovers skills.

## Verify

```bash
ls -la ~/.agents/skills/paperpowers
```

You should see a symlink pointing to the repository's `skills` directory.

If you later publish this repository to GitHub, replace the local source path with the hosted repository URL.
