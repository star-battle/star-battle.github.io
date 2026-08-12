---
version: "5.2"
published: null
updated: null
buildId: null
status: dev
tags: [game-balance, bugfixes]
---

# Star Battle Reloaded 5.2 - Patch Notes

## Ships & Balance

### Battlecruiser

- **Defensive Shield** no longer adds shield regeneration. The buff was granting **50/s** on top of the Battlecruiser's own **50/s**, so shields recovered at double rate while it was active — they now regenerate at the ship's normal rate. Hull regeneration is untouched. The Defensive Shield and shield-upgrade tooltips no longer mention shield restoration.

### Carrier

- **Warp In Tempest** is cheaper and off cooldown for everyone — energy **125 → 100**, cooldown **10 → 0**. Those two discounts used to be locked behind **Warp Technology**; they're now folded into the base ability, and the upgrade keeps its Warp and Warp In cooldown effects.
- **Tempest** damage **30 (+30 vs. Massive) → 40 (+40)**, while damage per upgrade level drops **10 → 8**.
- **Vortex** now telegraphs its cast — a charge-up effect on the Carrier plus an always-visible danger marker at the target point for the duration of the 2s cast. Previously it gave no warning at all.
- **Plasma Barrage** now telegraphs its **1.5s** wind-up with a cast bar and a charge-up effect on the hull, instead of firing out of a silent pause.

### Colossus

- **Quantum Reactor** in-combat shield regeneration reverted **50% → 33%**. As before, the share stays flat across every shield upgrade level — the per-level term moved alongside the base so the ratio holds at 33% from level 0 to 20.

### Dreadnought

- **Gauss Cannon** base damage **100 → 150** (+300 vs. Massive and structures, unchanged), and its damage is now reduced by **5** armor instead of **10**.
- **Bombardment** range **11 → 10**.
- **Siege Mode** energy cost **150 → 125**.
- **Siege Mode** movement speed raised to **33%** of normal (was 25%). The slow builds up in stacks across the 4s wind-up, so the whole transition is a little less punishing, not just the end state.

### Guardian

- **Brood Lord** acceleration **1.5 → 1.25**.
- **Corruptor** health regeneration per upgrade level **0.6 → 0.5**.

### Overlord

- Base hull armor **2 → 3**.
- **Psi Blast** now deals **+200 damage vs. Biological** on top of its 800 base.
- **Contaminate** base damage **100 → 125** over its full duration — it now reads **125 (+375 vs. Massive)** where it was **100 (+400)**. Total damage against Massive targets is unchanged; it simply hits the increasingly common non-Massive minions harder.

### Queen

- **Parasitic Bomb** spread no longer restarts the debuff. A ship caught by the spread used to receive a fresh full-duration bomb rather than inheriting whatever was left of the original, so the infection could keep renewing itself. It now expires alongside the primary. Damage is raised to compensate: **90 (+1310 vs. Massive)**, up from **90 (+1200)**.

> The **Healing Symbiote** and **Protective Brood** changes listed in the patch preview are held back for a later patch — the numbers need another pass before they can ship.

### Void Ray

- **Energy Nova** radius **6 → 5**, bringing its effective reach from **7 → 6** once the ship's own size is counted. The hover ring matches the new radius.
- **Fusion Torpedo** is no longer destroyed by Energy Nova. The torpedo was already meant to be exempt, but a faulty check let it through anyway.

## Bugfixes

- **Premade teams** — the post-game rating change was applied to the wrong side in games with preset teams, so the winning team could be charged for a loss while the losing team gained. Ratings now follow the team you actually played on.
- **Gas clouds** no longer shield their occupants from **Plague**, **Contaminate** and **Neural Parasite**. A target standing in a cloud was being treated the same as an undetected cloaked unit, so those spells whiffed. Genuinely cloaked and undetected units still dodge them, as before.
- **Plasma Barrage** no longer leaks impact effects — casting the upgraded, infinite version piled up orphaned effects on the Carrier for the rest of the match.
- **Warp In Tempest** tooltip corrected: the Carrier must have fewer than **6** Tempests, not 4. The limit itself was always 6.

## Profile & Rewards

### Classic tournament stars now follow you across regions

If you won stars in the old Star Battle tournaments but now play on a different server than the one you won them on, your profile was showing nothing. That's fixed.

Classic results are filed against a StarCraft II account handle, and a handle belongs to a single region — your NA profile and your EU profile are different handles even though they're the same Battle.net account. The game looks your rewards up using the handle for whichever region the game is running on, so if your results sat under a handle you no longer play, the lookup simply missed and you fell through to an empty record. No error, no warning — just a profile with zero stars on it.

All **1,634** classic entries were cross-checked against Battle.net account id and BattleTag — never by name, which would never have found these; the two profiles in the case that surfaced it shared neither a name nor a discriminator. That turned up **131** handles filed somewhere the game could never reach, plus **18** players holding two separate classic records that had drifted apart, so they saw different stars and different skins depending on which region they logged in from.

- **120 players** get their stars and Tournament Finals skins back — **96** of them were rendering a completely empty profile.
- **302 stars** and **212 Tournament Finals skins** restored.
- **Nobody lost a star or a skin.** The sweep was verified by regenerating the reward catalog before and after and diffing it handle by handle: no handle stopped resolving, and none lost anything. The change is strictly additive.

### Legacy star counts corrected

Separately from the sweep above, the pre-SBR records store cumulative *thresholds* rather than plain counts, and a negative entry in them is meaningful — it lowers the running threshold, which is how a legacy row records stars it should not display. Those entries were previously being discarded as import noise, which credited some profiles with stars that were never earned. Read as stored, **61** older profiles come back in line with their original records, and will show fewer legacy stars than they did in 5.1.

## Credits

- **DaveTheSpectre** joins the in-game asset contributors list.

<!-- TODO(finalize): fill frontmatter once v5.2 is promoted — published, buildId
     (`git describe --tags --always --match 'v*' <published-commit>`), status: live. -->

- [TODO] Taldarim Carrier animation pack — new spell animations and matching red Plasma Barrage effects. Wiring is still in the working tree and has not landed; confirm before publishing, and add `new-content` to `tags` if it ships in 5.2.
