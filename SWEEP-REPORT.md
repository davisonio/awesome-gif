# Sweep Report

## Summary

This is an awesome-list (Markdown only, no buildable code), so the sweep did the dead-link and formatting pass instead of steps 1-5. One dead link and some formatting problems were fixed. The link checker moved from `awesome_bot` (which ran on Ruby 2.7, now EOL) to a lychee GitHub Action that also runs once a week.

## Done

- Dead-link + formatting sweep: **done**
  - ImageMagick link `https://imagemagick.org/script/index.php` returned 404; replaced with `https://imagemagick.org/`.
  - Fixed the mismatched `<h3 id="c-sharp">C#</h2>` closing tag.
  - Typos: "libary" -> "library", "browing" -> "browsing". Added the missing trailing period on the last "Use" bullet and a trailing newline to `contributing.md`.
- Link-check GitHub Action: **done**. New `.github/workflows/link-check.yml` uses `lycheeverse/lychee-action@v2` on push/PR to master, weekly (Mon 06:00 UTC) and manual dispatch. The old exclusions are kept (davison.io cert mismatch, reddit.com bot block), and 429 counts as alive. The workflow needs no secrets; it only uses the built-in `GITHUB_TOKEN`.
- `main.yml` now only runs `awesome-lint`, on Node 22 via `actions/setup-node@v5`. The Ruby/awesome_bot steps were removed.
- 1. Maintenance: **skipped**, there are no dependencies or build.
- 2. Tests + CI: **skipped** for tests (no code to test); CI is covered by the lint and link-check workflows above.
- 3. Security + correctness: **skipped**, no code and nothing that handles auth, user data or input.
- 4. Site audit: **skipped**, this is not a website (the README is rendered by GitHub).
- 5. Grind: **skipped**, no TypeScript, dead code or Workers config.

## Test coverage

Not applicable (no code): 0 tests -> 0 tests.

## Commands verified passing

- `npx awesome-lint`: no content errors. Locally it reports only "must reside in a valid git repository", because this sandbox's git remote is a proxy URL instead of github.com. In CI the remote is github.com, so this will not trigger there.
- Workflow YAML parses (`yaml.safe_load` on both files).
- `curl` link check of all 60 unique URLs. Every non-GitHub link answered except the ones listed below.

## Follow-ups needing a human

- All github.com links (about 40) returned 403 through this sandbox's proxy, so they could not be checked here. The first lychee run in CI will check them.
- `https://giflr.com/` timed out on both HTTP and HTTPS from the sandbox; it may be dead. If CI confirms that, remove it or find a replacement.
- `https://giftoframes.org/` answered over HTTP but the HTTPS tunnel dropped here. It is probably fine, but check the lychee result.
- giphy.com and sourceforge.net returned 403 to the bot here. If lychee flags either of them in CI, add an `--exclude` for it. superuser.com (Stack Exchange) also returns 403 to bots, so it is now excluded alongside reddit.com.
