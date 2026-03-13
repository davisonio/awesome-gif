# Awesome GIF - Comprehensive Audit Plan

---

## 1. REPO HEALTH CHECK

### LICENSE
- **Status: PASS** - `license.txt` contains CC0 1.0 Universal, which is the standard for awesome lists.
- **Issue**: File is named `license.txt` instead of `LICENSE`. The awesome list convention is typically `license` (no extension) or `LICENSE`. Minor cosmetic issue.

### CONTRIBUTING.md
- **Status: NEEDS IMPROVEMENT** - `contributing.md` exists but is minimal (10 lines).
- Missing: no mention of quality standards, what makes something "awesome", link format requirements, or PR process.
- The filename uses lowercase `contributing.md` - should be uppercase `CONTRIBUTING.md` per convention.

### .github/ setup
- **Status: PARTIAL** - Has CI workflow (`main.yml`) with awesome-lint and awesome_bot.
- **Missing**: No PR template, no issue template.
- **CI Issues**:
  - `actions/checkout@v3` is outdated (current is v4).
  - `ruby/setup-ruby@v1` with `ruby-version: 2.7` - Ruby 2.7 is EOL.
  - `awesome_bot` gem is unmaintained; consider replacing with a modern link checker.
  - The whitelist includes `davison.io` (SSL cert mismatch noted) - should verify if still needed.

### Awesome Badge
- **Status: PASS** - Badge is present on line 1: `[![Awesome](https://awesome.re/badge-flat.svg)](https://awesome.re)`

### awesome-lint Results
- **1 error**: `Awesome list must reside in a valid git repository` - This is a false positive caused by running in a shallow clone. In a full clone, this should pass. The CI should handle this correctly (uses `fetch-depth: 0`).

### Open Issues/PRs
- Could not check (no `gh` CLI available in this environment). **Action**: Verify manually on GitHub.

### Inclusion in Main Awesome List
- **Status: INCLUDED** - `davisonio/awesome-gif` is listed under "Media" in the main [sindresorhus/awesome](https://github.com/sindresorhus/awesome) list. This was restored via [issue #872](https://github.com/sindresorhus/awesome/issues/872).

### Repo Metadata
- Could not programmatically verify GitHub repo description/topics. **Action**: Ensure repo has description "A curated list of awesome GIF resources", and topics include `awesome`, `awesome-list`, `gif`, `graphics`.

---

## 2. LINK AUDIT

### All GitHub Repository Links
All 34 GitHub repository links returned HTTP 200 - none are dead or moved. However, several have concerning statuses:

#### Archived Repository
| Entry | Stars | Note | Recommendation |
|-------|-------|------|----------------|
| [android-gif-encoder](https://github.com/nbadal/android-gif-encoder) | 350 | **Archived** | **REMOVE** - archived repos shouldn't be in an awesome list |

#### Unmaintained (No commits in 2+ years)
| Entry | Stars | Last Push | Recommendation |
|-------|-------|-----------|----------------|
| [Screengif](https://github.com/dergachev/screengif) | 1,312 | 2020-07 | Flag - 5+ yrs stale but decent stars |
| [Gifline](https://github.com/zehfernandes/gifline) | 69 | 2019-06 | **REMOVE** - 6+ yrs stale, very low stars |
| [Ccapture.js](https://github.com/spite/ccapture.js) | 3,748 | 2022-12 | Keep - high stars, still widely referenced |
| [Gifcurry](https://github.com/lettier/gifcurry) | 1,431 | 2021-08 | Flag - 4+ yrs stale |
| [gif (Haxe)](https://github.com/snowkit/gif) | 40 | 2018-12 | **REMOVE** - 7+ yrs stale, very low stars, niche language |
| [GifImageView](https://github.com/felipecsl/GifImageView) | 1,174 | 2023-04 | Flag - 2+ yrs stale, superseded by modern Android solutions |
| [gif-animation](https://github.com/extrapixel/gif-animation) | 178 | 2021-10 | **REMOVE** - 4+ yrs stale, Processing-specific |
| [Gifffer](https://github.com/krasimir/gifffer) | 784 | 2019-08 | Flag - 6+ yrs stale |
| [node-gify](https://github.com/tj/node-gify) | 300 | 2022-09 | **REMOVE** - 3+ yrs stale, low activity |
| [GifFrameExtractor](https://github.com/Sybio/GifFrameExtractor) | 179 | 2022-07 | Flag - 3+ yrs stale |
| [dot-screencap](https://github.com/Speiser/dot-screencap) | 34 | 2017-11 | **REMOVE** - 8+ yrs stale, 34 stars |
| [tty2gif](https://github.com/z24/tty2gif) | 160 | 2023-05 | Flag - 2+ yrs stale |
| [gifgen](https://github.com/lukechilds/gifgen) | 563 | 2023-01 | Flag - 3+ yrs stale but useful tool |
| [DeepDreamVideo](https://github.com/graphific/DeepDreamVideo) | 2,120 | 2022-07 | Flag - referenced in Scripts section |
| [gif.js](https://github.com/jnordberg/gif.js) | 4,962 | 2023-10 | Keep - high stars, widely used, de facto standard |
| [Animated_GIF](https://github.com/sole/Animated_GIF) | 228 | 2024-02 | Flag - 2+ yrs stale |
| [gifify](https://github.com/jclem/gifify) | 1,137 | 2024-02 | Flag - 2+ yrs stale |

#### Active Repositories (healthy)
| Entry | Stars | Last Push |
|-------|-------|-----------|
| [gifski](https://github.com/ImageOptim/gifski) | 5,437 | 2026-02 |
| [android-gif-drawable](https://github.com/koral--/android-gif-drawable) | 9,660 | 2026-02 |
| [yt-dlp](https://github.com/yt-dlp/yt-dlp) | 150,896 | 2026-03 |
| [GIFit](https://github.com/takempf/GIFit) | 134 | 2026-03 |
| [XamlAnimatedGif](https://github.com/XamlAnimatedGif/XamlAnimatedGif) | 462 | 2025-06 |
| [gif-h](https://github.com/charlietangora/gif-h) | 536 | 2024-07 |
| [FLAnimatedImage](https://github.com/Flipboard/FLAnimatedImage) | 7,980 | 2024-03 |

#### Could Not Verify (API rate-limited)
These repos returned 200 on HTTP check but I couldn't get metadata:
- `notnullnotvoid/msf_gif`, `XamlAnimatedGif/WpfAnimatedGif`, `deanm/omggif`, `rubentd/gifplayer`, `eugeneware/gifencoder`, `Sybio/GifCreator`, `alexiscreuzot/SwiftyGif`, `kaishin/gifu`

### Non-GitHub Links
Non-GitHub links could not be reliably tested from this environment (network restrictions). The following should be manually verified:

| Link | Notes |
|------|-------|
| `http://www.graphicsmagick.org/` | Uses HTTP, should be HTTPS if available |
| `https://zulko.github.io/moviepy/` | Verify still active |
| `https://getkap.co/` | Verify still active |
| `https://sourceforge.net/projects/qgifer/` | Returned 200, but Qgifer is very old |
| `https://giflr.com/` | Verify still active |
| `https://giftoframes.org/` | Verify still active |
| `http://blog.pkh.me/p/21-high-quality-gif-with-ffmpeg.html` | Uses HTTP, returned 403 |
| `http://zulko.github.io/blog/2014/01/23/...` | Uses HTTP, returned 403 (2 links) |
| `http://zulko.github.io/blog/2015/02/01/...` | Uses HTTP, returned 403 |
| `https://kornel.ski/lossygif` | Verify still active |
| `https://davison.io` | SSL cert mismatch noted in CI whitelist |
| `https://ismailbaaj.fr` | Verify still active |

---

## 3. QUALITY AUDIT - IS EVERYTHING TRULY AWESOME?

### Entries Recommended for REMOVAL (not awesome enough)

| Entry | Reason |
|-------|--------|
| **Gifline** (69 stars, 6+ yrs stale) | Chrome extension for putting GIFs in emails. Extremely niche, near-zero community, abandoned. |
| **dot-screencap** (34 stars, 8+ yrs stale) | Typo in description ("libary"). 34 stars, no activity since 2017. Not awesome. |
| **gif (Haxe)** (40 stars, 7+ yrs stale) | Haxe is extremely niche. 40 stars. No activity. Not enough community to warrant inclusion. |
| **android-gif-encoder** (350 stars, archived) | Archived by owner. Should not be in an awesome list. |
| **gif-animation** (178 stars, 4+ yrs stale) | Processing library - very niche. Unmaintained. |
| **node-gify** (300 stars, 3+ yrs stale) | Low stars, unmaintained. Better alternatives exist (gifski, ffmpeg directly). |
| **Qgifer** (SourceForge) | SourceForge-hosted, very old. No evidence of maintenance. The GUI section has only this one entry - consider removing the entire section or adding better alternatives. |
| **Giflr** | Relatively unknown online tool. Needs verification that it still works and is useful. |
| **GIF Frame Extractor (giftoframes.org)** | Unknown provenance. Needs verification. |

### Entries to FLAG for Discussion

| Entry | Concern |
|-------|---------|
| **Screengif** (1,312 stars, 5+ yrs stale) | Decent stars but completely unmaintained. Keep if still functional. |
| **Gifcurry** (1,431 stars, 4+ yrs stale) | Haskell-based, niche. Decent stars but unmaintained. |
| **Ccapture.js** (3,748 stars, 3+ yrs stale) | High stars but HTML5 canvas capture is niche. Still widely referenced. Lean keep. |
| **Gifffer** (784 stars, 6+ yrs stale) | Useful concept (pause/play GIFs) but abandoned. |
| **tty2gif** (160 stars, 2+ yrs stale) | Niche. asciinema/agg may be better alternatives. |
| **GifImageView** (1,174 stars, 2+ yrs stale) | Superseded by android-gif-drawable and modern Compose approaches. |
| **GIFit** (134 stars, active) | Low stars for its age. Chrome extension to make GIF from YouTube - yt-dlp + ffmpeg does this better. |
| **Gifplayer** (unknown stars) | jQuery plugin - jQuery is declining. Need to verify relevance. |
| **Animated_GIF** (228 stars, 2+ yrs stale) | Low stars. Overlaps with gif.js. |

### Entries That Are Fine

| Entry | Why |
|-------|-----|
| **FFmpeg, ImageMagick, GraphicsMagick, MoviePy** | Foundational tools. Unquestionable. |
| **gifski** (5,437 stars, active) | Best-in-class GIF encoder. Excellent. |
| **Kap** | Popular, well-known screen recorder. |
| **gif.js** (4,962 stars) | De facto standard for browser GIF creation. |
| **android-gif-drawable** (9,660 stars, active) | Dominant Android GIF library. |
| **FLAnimatedImage** (7,980 stars) | Standard iOS GIF engine by Flipboard. |
| **SwiftyGif, Gifu** | Solid Swift GIF libraries. |
| **gif-h** (536 stars) | Useful single-header C++ library. |
| **omggif** | Solid low-level GIF encoder/decoder. |
| **gifgen** (563 stars) | Simple, focused utility. |
| **EzGif** | Well-known, widely-used online tool. |
| **Giphy, /r/educationalgifs** | Key community resources. |
| **yt-dlp** (150,896 stars) | Industry standard. |
| **Imgur** | Standard hosting. Though GIF hosting landscape has evolved. |

---

## 4. MISSING AWESOME PROJECTS

### Strong Recommendations (should definitely be added)

| Project | URL | Description | Stars | Why Awesome |
|---------|-----|-------------|-------|-------------|
| **gifsicle** | https://github.com/kohler/gifsicle | Command-line tool for creating, editing, and optimizing GIFs. | ~3.7k | Industry standard GIF manipulation tool. Already referenced in Scripts section but not listed as a tool! Glaring omission. |
| **ScreenToGif** | https://github.com/NickeManarin/ScreenToGif | Screen, webcam, and sketchboard recorder with integrated editor. | ~26.5k | Best-in-class Windows GIF recorder/editor. |
| **LICEcap** | https://github.com/justinfrankel/licecap | Simple animated screen capture tool for Windows/macOS. | ~5.5k | Classic, lightweight, focused GIF recorder. |
| **Peek** | https://github.com/phw/peek | Simple animated GIF screen recorder for Linux. | ~10.5k | The go-to Linux GIF recorder. **Note: deprecated** (Jan 2023) due to Wayland compatibility. Still widely used. Your call on including deprecated tools. |
| **ShareX** | https://github.com/ShareX/ShareX | Screen capture, file sharing and productivity tool with GIF recording. | ~35.8k | Most-starred screen capture tool on GitHub. |
| **vhs** | https://github.com/charmbracelet/vhs | CLI tool for creating terminal GIFs from declarative `.tape` scripts. | ~17.5k | Modern, elegant, CI-friendly terminal-to-GIF recorder by Charmbracelet. |
| **Pillow** | https://github.com/python-pillow/Pillow | Python Imaging Library with GIF read/write support. | ~12k | The standard Python image library. Belongs in Libraries > Python. |
| **GIFLIB** | https://giflib.sourceforge.net/ | Foundational C library for GIF encoding/decoding, in use since 1989. | N/A | Used by Mosaic (first graphical browser). Extremely mature, speaks GIF87a and GIF89a. Belongs in Libraries > C. |
| **Tenor** | https://tenor.com | GIF search engine and sharing platform (owned by Google). | N/A | Major GIF platform, used in messaging apps everywhere. **Caveat**: Tenor API for third-party devs sunsetting Sept 2026, but platform continues. |
| **agg** | https://github.com/asciinema/agg | Converts asciinema terminal recordings to animated GIFs using gifski. | ~1.6k | Modern Rust-based replacement for tty2gif. |
| **r/HighQualityGifs** | https://www.reddit.com/r/HighQualityGifs/ | Subreddit for creating and sharing high-quality GIFs. | N/A | Major GIF creation community. Very active. |
| **r/perfectloops** | https://www.reddit.com/r/perfectloops/ | Subreddit for seamlessly looping GIFs. | N/A | Directly relevant to the "Perfect Loop" scripts section. |

### Good Recommendations (worth considering)

| Project | URL | Description | Stars | Why Awesome |
|---------|-----|-------------|-------|-------------|
| **t-rec** | https://github.com/sassman/t-rec-rs | Terminal recorder in Rust that generates animated GIFs directly. | ~1.2k | Idle frame detection, wallpaper/shadow effects. |
| **SDWebImage** | https://github.com/SDWebImage/SDWebImage | Async image loading with GIF support for iOS/macOS. | ~25k | Major iOS image library with GIF support. |
| **Glide** | https://github.com/bumptech/glide | Android image loading with GIF support. | ~35k | Standard Android image loader. |
| **Coil** | https://coil-kt.github.io/coil/gifs/ | Kotlin-first Android image loader with built-in GIF/animated WebP/HEIF support. | ~11k | Modern Kotlin-native replacement for Glide. |
| **image-gif (Rust)** | https://github.com/image-rs/image-gif | Standard Rust GIF encoder/decoder crate. | N/A | Part of the image-rs ecosystem. |
| **image/gif (Go)** | https://pkg.go.dev/image/gif | Go standard library GIF package. | N/A | Built-in GIF support, no third-party dependency needed. |
| **sharp** | https://github.com/lovell/sharp | High-performance Node.js image processing (GIF support via libvips). | ~29k | De facto Node.js image processor. |
| **imageio** | https://github.com/imageio/imageio | Python library for reading and writing image data including GIFs. | N/A | Complements Pillow for GIF I/O. |
| **pygifsicle** | https://github.com/LucaCappelletti94/pygifsicle | Python wrapper for gifsicle. | N/A | Enables GIF optimization from Python, ~3x file size reduction. |
| **Gifox** | https://gifox.app | macOS GIF recording app. | N/A | Popular paid alternative to Kap on macOS. |
| **Lottie** | https://github.com/airbnb/lottie-web | Render After Effects animations natively (modern GIF alternative). | ~30k | Tangentially related - could go in a "GIF Alternatives" note. |
| **GIF89a Specification** | https://www.w3.org/Graphics/GIF/spec-gif89a.txt | The official GIF89a format specification. | N/A | Foundational reference. Could go in Miscellaneous. |

### Also Notable: Gfycat shut down (Sept 2023). Do NOT add, but worth knowing.

### New Sections to Consider
- **Libraries > Python** - Currently missing entirely despite Python being heavily used for GIF work (Pillow, imageio).
- **Libraries > C** - GIFLIB is the foundational GIF library used since 1989.
- **Libraries > Go** - Go has built-in GIF support in its standard library.
- **Libraries > Rust** - gifski is Rust-based; could add the `image-gif` crate.
- **Libraries > Kotlin** - Android ecosystem has moved to Kotlin; Coil has GIF support.
- **Specifications / Standards** - Link to the GIF89a specification.

---

## 5. STRUCTURE & FORMATTING

### Category Structure Issues
1. **Scripts section is unusual** for an awesome list. It contains inline code snippets rather than links to projects. While educational, this is atypical and bloats the README. Consider:
   - Moving script examples to a separate `scripts/` directory or wiki page.
   - Or keep them but clean up formatting.

2. **GUI section has only 1 entry** (Qgifer, which is stale). Either add more GUI tools (ScreenToGif, LICEcap, Peek, Gifox) or merge into Utilities.

3. **Hosting section has only 1 entry** (Imgur). Should either add Tenor/Giphy as hosting or merge with Community.

4. **Online Tools section is thin** (3 entries). Could be expanded with EZGIF alternatives.

5. **Missing language sections**: Python, Go, Rust, Kotlin are unrepresented in Libraries despite having notable GIF libraries.

### Formatting Issues
1. **Line 41**: `GraphicsMagick` URL uses `http://` - should be `https://` if supported.
2. **Line 64**: Uses raw HTML `<h3 id="c-sharp">C#</h2>` - mismatched h3/h2 tags. Should use markdown heading with anchor.
3. **Line 66**: Typo "libary" should be "library" in dot-screencap description.
4. **Line 138**: Inline backticks around filename `frames2gif.sh` use triple backticks instead of single.
5. **Line 182**: Article link uses `http://` instead of `https://`.
6. **Line 230, 246**: Article links use `http://` instead of `https://`.
7. **Lines 39-42**: General Tools entries are inconsistent - FFmpeg and ImageMagick have no descriptions while GraphicsMagick and MoviePy do.
8. **Line 108**: Qgifer has no description at all.
9. **Line 112**: Imgur description is just "Maximum file upload is 50MB" - not really a description of what Imgur is.
10. **Line 122**: Giphy has no description.
11. **Line 299**: Typo "browing" should be "browsing".
12. **TOC**: Has `<!--lint disable awesome-toc-->` which suppresses TOC linting. The TOC should be verified for accuracy.
13. **Missing**: No "Footnotes" or "Related" section linking to related awesome lists.

### Ordering
- Entries within sections are **not consistently alphabetized**. Some sections appear alphabetical, others don't. Should pick a convention and apply it consistently.

### awesome list guidelines compliance
- Missing a "Contents" link at the top (the TOC exists but doesn't have a clear marker).
- Descriptions should start with a capital letter and end with a period - several entries violate this.
- List items should have consistent description format: `- [Name](url) - Description.`
- Some entries lack descriptions entirely (FFmpeg, ImageMagick, Qgifer, Giphy).

---

## 6. SUMMARY & EXECUTION PLAN

### Quick Wins (can fix immediately, no input needed)

1. **Fix typo**: "libary" -> "library" (line 66)
2. **Fix typo**: "browing" -> "browsing" (line 299)
3. **Fix HTML tag mismatch**: `<h3>...</h2>` -> proper markdown heading (line 64)
4. **Fix triple backtick in inline context**: line 138
5. **Upgrade HTTP links to HTTPS** where supported (GraphicsMagick, blog links)
6. **Add missing descriptions** to entries that lack them (FFmpeg, ImageMagick, Giphy, Qgifer if kept)
7. **Ensure descriptions end with periods** consistently
8. **Update CI**: `actions/checkout@v3` -> `v4`, update Ruby version
9. **Remove archived repo**: android-gif-encoder (archived by owner)

### Recommendations (need your input)

#### Removals (entries I recommend removing - say yes/no to each):
1. **Gifline** - 69 stars, 6+ yrs stale, extremely niche
2. **dot-screencap** - 34 stars, 8+ yrs stale
3. **gif (Haxe)** - 40 stars, 7+ yrs stale, niche language
4. **gif-animation (Processing)** - 178 stars, 4+ yrs stale, niche
5. **node-gify** - 300 stars, 3+ yrs stale, better alternatives
6. **Qgifer** - SourceForge, very old, only GUI entry
7. **GIFit** - 134 stars, niche Chrome extension, yt-dlp does it better
8. **Giflr** / **GIF Frame Extractor** - unknown provenance, need verification

#### Additions (projects I recommend adding - say yes/no to each):

**Strong (I'd add all of these):**
1. **gifsicle** (~3.7k stars) - in General Tools or Utilities
2. **ScreenToGif** (~26.5k stars) - in GUI (replaces Qgifer)
3. **ShareX** (~35.8k stars) - in GUI or Utilities
4. **vhs** (~17.5k stars) - in Utilities (modern terminal-to-GIF)
5. **LICEcap** (~5.5k stars) - in GUI
6. **Peek** (~10.5k stars, deprecated) - in GUI or Utilities
7. **Pillow** (~12k stars) - new Libraries > Python section
8. **GIFLIB** (foundational since 1989) - new Libraries > C section
9. **Tenor** - in Hosting or Community
10. **agg** (~1.6k stars) - in Utilities (modern tty2gif replacement)
11. **r/HighQualityGifs** - in Community
12. **r/perfectloops** - in Community

**Good (worth considering):**
13. **SDWebImage** (~25k stars) - in Libraries > Objective-C/Swift
14. **Glide** (~35k stars) - in Libraries > Java
15. **Coil** (~11k stars) - new Libraries > Kotlin section
16. **image-gif** (Rust crate) - new Libraries > Rust section
17. **sharp** (~29k stars) - in Libraries > JavaScript
18. **GIF89a Specification** - in Miscellaneous

#### Structural changes:
1. Merge **GUI** into **Utilities** (or expand GUI with ScreenToGif/LICEcap/Peek)?
2. Merge **Hosting** into **Community** (or expand with Tenor)?
3. Add **Libraries > Python** section?
4. Add **Libraries > Go** section?
5. Move **Scripts** section to a separate file to keep README focused on curated links?
6. Alphabetize entries within all sections?

### Questions for You

1. **Stale but popular projects**: Several entries have high stars but haven't been updated in 2-4 years (gif.js, Ccapture.js, FLAnimatedImage, Gifcurry, Screengif). These are "complete" tools that still work - keep all, keep selectively, or add a note?
2. **Scripts section**: The inline bash/python scripts are unusual for an awesome list. Keep as-is, move to separate file, or remove?
3. **Scope of "GIF"**: Should the list include modern alternatives to GIF (WebP, AVIF animation, Lottie) or stay strictly GIF-focused?
4. **`davison.io` credit link**: The CI whitelist notes SSL cert hostname mismatch. Should the Credits link be updated or removed?
5. **Depth of library coverage**: Should we add libraries for every major language (Python, Go, Rust, Kotlin, Ruby, etc.) or keep it focused on the most common use cases?
