# Integration Plan — Humanize Skill

## New Reference Files Added

| File | Source | Key Value |
|------|--------|-----------|
| source-4-blader-humanizer.md | github.com/blader/humanizer v2.5.1 | Voice calibration, 2nd-pass audit, 9 extra patterns |
| source-5-clawhub-skills.md | 6 ClawHub skills comparison | Platform-style adaptation (zhihu/xiaohongshu/wechat), n-gram approach |
| source-6-web-research.md | Surfer SEO, cnblogs, Tencent Cloud | Perplexity/burstiness theory, Chinese-specific AI tells, prompt templates |

## Changes to SKILL.md

### P0 (must do)

1. **Add Voice Calibration section** — from blader/humanizer. Let user provide writing sample, analyze rhythm/vocabulary/punctuation/quirks, then match in rewrite. Unique among Chinese humanizer skills.

2. **Add 2nd-pass audit** — After rewrite, self-prompt "What remaining AI tells exist?" then revise again. Significantly improves quality.

3. **Add Chinese-specific AI patterns** (not in current 24):
   - Cheng-yu overload (四字成语堆砌)
   - Internet buzzword abuse (赋能/抓手/闭环/沉淀)
   - Excessive "的" usage
   - Exclamation mark overuse
   - Over-polite formulaic closings (感谢阅读/希望对您有帮助)
   - Parallel sentence structures (排比句)

4. **Add missing English patterns** from blader (not in current 24):
   - Synonym cycling (elegant variation)
   - False ranges ("from X to Y")
   - Hyphenated word-pair overuse
   - Signposting announcements ("Let's dive in")
   - Fragmented headers
   - Passive voice / subjectless fragments
   - Cutoff disclaimers ("While details are limited...")

5. **Add perplexity/burstiness awareness** — Brief section explaining the theory so the agent understands WHY varying sentence length and replacing predictable words matters.

### P1 (should do)

6. **Add Chinese examples** to "注入灵魂" section (currently English-only)

7. **Simplify output format** — Default: just the rewritten text + brief change notes. Scoring table as optional, not default.

### P2 (nice to have)

8. **Platform style presets** — casual/zhihu/xiaohongshu/wechat/academic (from humanize-chinese skill)
9. **Prompt template library** in references/ for different scenarios

## What NOT to do

- No code implementation (keep instruction-only)
- No "bypass detector" framing (position as "make writing natural")
- Do not reference moltbro/humanize-ai-text (ethical risk)
- Do not add academic ghost-writing features

## Files to modify

1. `SKILL.md` — add voice calibration, 2nd-pass, perplexity awareness, simplify output
2. `references/full-patterns.md` — expand from 24 to ~32 patterns with Chinese-specific ones

## Next step

Await your confirmation, then I rewrite both files.
