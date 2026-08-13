---
version: "5.2"
published: "2026-08-14T00:00Z"
updated: null
buildId: "v5.2"
status: live
tags: [game-balance, bugfixes, new-content, ui]
---

# Star Battle Reloaded 5.2 - Patch Notes

## Ships & Balance

### Battlecruiser

- **Defensive Shield** no longer adds shield regeneration. The buff was granting **50/s** on top of the Battlecruiser's own **50/s**, so shields recovered at double rate while it was active — they now regenerate at the ship's normal rate. Hull regeneration is untouched. The Defensive Shield and shield-upgrade tooltips no longer mention shield restoration.

### Carrier

- **Warp In Tempest** is cheaper and off cooldown for everyone — energy **125 → 100**, cooldown **10 → 0**. Those two discounts used to be locked behind **Warp Technology**; they're now folded into the base ability, and the upgrade keeps its Warp and Warp In cooldown effects.
- **Tempest** damage **30 (+30 vs. Massive) → 40 (+40)**, while damage per upgrade level drops **10 → 8**.
- **Plasma Barrage** now telegraphs its **1.5s** wind-up with a cast bar and a charge-up effect on the hull, instead of firing out of a silent pause.

> A lot of words to simply say "Tempests no longer rely on the Carrier having Warp Technology to be usable". Smoothening numbers (5 to 1, base damage to upgrade damage ratio), making it more efficient for the Carrier to start using Tempests, making Tempests a little less overwhelming as the game goes on.
>
> — **OG**

### Colossus

- **Quantum Reactor** in-combat shield regeneration reverted **50% → 33%**. As before, the share stays flat across every shield upgrade level — the per-level term moved alongside the base so the ratio holds at 33% from level 0 to 20.

The 50% was never a value anyone set. It's a ratio between two separate numbers — how fast the Colossus regenerates shields, and how much of that combat takes away — and the 5.0 pass raised base shield regeneration and retuned the other side of the ratio in the same edit, which moved the share from 33% to 50% as a side effect. The 5.0 note covered the regeneration change but not the ratio, and the tooltip calculates its percentage live from the game data, so it has been showing 50% in-game to everyone all patch. 33% had been the value since before SBR existed, so this is a revert rather than a new nerf. Concretely, at 8 shield upgrades in-combat regeneration goes **72/s → 48/s**, while out of combat it is unchanged at 144/s.

> Quantum Reactor easily gives much value, for little play around — or even compensates for mistakes.
>
> — **OG**

### Dreadnought

- **Gauss Cannon** base damage **100 → 150** (+300 vs. Massive and structures, unchanged), and its damage is now reduced by **5** armor instead of **10**.
- **Bombardment** range **11 → 10**.
- **Siege Mode** energy cost **150 → 125**.
- **Siege Mode** movement speed raised to **33%** of normal (was 25%). The slow builds up in stacks across the 4s wind-up, so the whole transition is a little less punishing, not just the end state.

> Bombard is very present in the meta. While I don't think it is that strong, its state compared to other versions is stronger on many aspects. This one change might just be enough to play more efficiently against it, without changing too much of its functioning.
>
> Follow-up changes to siege, still in the same spirit of trying to render its use more tactical and less of a "we already won" or "we need to finish the game". Base damage raise and energy cost redux are here to ease its use, knowing going siege is an expensive build, including upgrades that are completely different from what it otherwise would buy/has bought.
>
> — **OG**

### Guardian

- **Brood Lord** acceleration **1.5 → 1.25**.
- **Corruptor** health regeneration per upgrade level **0.6 → 0.5**.

> From my perspective, Brood Lords are a little too easy to manoeuvre for players that kite consistently with them. Brood Lords should be a little less relentless in our hands.
>
> While we haven't seen many Corruptors used, these minions scale pretty well, even against ships that are supposed to clear them more easily (F, C, L).
>
> — **OG**

### Overlord

- **Hull armor** 2 → 3.
- **Psi Blast** now deals **+200 damage vs. Biological** on top of its 800 base.
- **Contaminate** base damage **100 → 125** over its full duration — it now reads **125 (+375 vs. Massive)** where it was **100 (+400)**. Total damage against Massive targets is unchanged; it simply hits the increasingly common non-Massive minions harder.

> Small quality of life changes. Overlord hasn't been played much in organized play lately, even less as a carry ship. I think it sits in a fine spot — maybe this Psi Blast change gives an incentive to play more carry ovies.
>
> — **OG**

### Queen

- **Healing Symbiote** now heals by target type instead of a flat amount. Over its full 10s channel it restores **1000** to Zerg allies — Queen, Overlord, Leviathan and Guardian — and **400** to everyone else, where it previously gave a flat **600**. Per upgrade level that's **100** on Zerg allies and **40** elsewhere, from a flat 150.
- **Protective Brood** splits the same way. Capital ships now gain **30** hull armor (was 25), while the fighters and summons caught in the same cast gain **15**. Per upgrade level: **3.0** on capital ships and **1.5** on the smaller units, from a flat 2.5.
- **Parasitic Bomb** spread no longer restarts the debuff. A ship caught by the spread used to receive a fresh full-duration bomb rather than inheriting whatever was left of the original, so the infection could keep renewing itself. It now expires alongside the primary. Damage is raised to compensate: **90 (+1310 vs. Massive)**, up from **90 (+1200)**.

The two splits above follow the ship roster exactly: every capital ship counts as Massive, and only the four Zerg hulls count as Biological. So Protective Brood is a straight buff on the ships you actually cast it on, and Healing Symbiote becomes a Zerg-ally heal — noticeably stronger on the four Zerg hulls, weaker on the other eight.

> Ship is under refinement. Symbiote will probably need follow-up adjusts. Protective Brood isn't used much, if at all, although for those who have an eye for details, its stats against lasers (which are main attack sources against light units) are pretty strong. Pre-emptive change, that may or may not be enough.
>
> Parasitic Bomb changed to make it match other AoE damages, and compensate for the bugfix that is a direct nerf.
>
> — **OG**

### Void Ray

- **Energy Nova** radius **6 → 5**, bringing its effective reach from **7 → 6** once the ship's own size is counted. The hover ring matches the new radius.
- **Energy Nova** no longer destroys the projectiles it was meant to spare. The exemption list has been there since 5.0, but the check behind it was written in a form the engine doesn't apply reliably, so protected projectiles were being cleared out of the air anyway — including a Nuclear Missile inbound on the Void Ray itself. All seven are now correctly spared: **Fusion Torpedo, Seeker Missile, Nuclear Missile, EMP, Lockdown, Siphon Energy and Parasite**.

> Nova is able to deny a lot of farm, and Void Ray has an easy time flying in and out to use Nova on ships. This change shouldn't change much when it comes to blink-nova or nova-blink.
>
> — **OG**

## Bugfixes

- **Premade teams** — the post-game rating change was applied to the wrong side in games with preset teams, so the winning team could be charged for a loss while the losing team gained. Ratings now follow the team you actually played on.
- **Gas clouds** no longer shield their occupants from **Plague**, **Contaminate** and **Neural Parasite**. A target standing in a cloud was being treated the same as an undetected cloaked unit, so those spells whiffed. Genuinely cloaked and undetected units still dodge them, as before.
- **Plasma Barrage** no longer leaks impact effects — casting the upgraded, infinite version piled up orphaned effects on the Carrier for the rest of the match.
- **Corruptor** projectiles now grow with the Corruptors upgrade. The upgrade was scaling the wrong actor, so your own Corruptor's missile stayed at its base size no matter how many levels you bought, while the Swarm Command version could grow from two upgrades at once. Visual only — damage and behaviour were never affected.
- **Warp In Tempest** tooltip corrected: the Carrier must have fewer than **6** Tempests, not 4. The limit itself was always 6.

## Profile & Rewards

### Classic tournament stars now follow you across regions

If you won stars in the old Star Battle tournaments but now play on a different server than the one you won them on, your profile was showing nothing. That's fixed.

Classic results are filed against a StarCraft II account handle, and a handle belongs to a single region — your NA profile and your EU profile are different handles even though they're the same Battle.net account. The game looks your rewards up using the handle for whichever region the game is running on, so if your results sat under a handle you no longer play, the lookup simply missed and you fell through to an empty record. No error, no warning — just a profile with zero stars on it.

All **1,634** classic entries were cross-checked against Battle.net account id and BattleTag — never by name, which would never have found these; the two profiles in the case that surfaced it shared neither a name nor a discriminator. That turned up **131** handles filed somewhere the game could never reach, plus **18** players holding two separate classic records that had drifted apart, so they saw different stars and different skins depending on which region they logged in from.

- **120 players** get their stars and Tournament Finals skins back — **96** of them were rendering a completely empty profile.
- **302 stars** and **212 Tournament Finals skins** restored.
- **Nobody lost a star or a skin.** The sweep was verified by regenerating the reward catalog before and after and diffing it handle by handle: no handle stopped resolving, and none lost anything. The change is strictly additive.

### SBR Monthly Championship #1 — rewards granted

The first tournament of the SBR Monthly Championship Series was played on **8 August 2026** and won by **Legacy Reborn**, who went 5–0 through the group stage and 2–0 in the Grand Final.

- The eight Legacy Reborn players who took the field receive the **Green Frigate** skin.
- Everyone else who played collects their placement and participation stars toward the series rewards.

As the ruleset requires, only players who played **at least two games** are credited. Third and fourth place are still open — that Bo3 could not be scheduled on the day and has been moved to **21 August** — so those two teams collect their credit once it is played. Nothing granted here changes when it does.

### Legacy star counts corrected

Separately from the sweep above, the pre-SBR records store cumulative *thresholds* rather than plain counts, and a negative entry in them is meaningful — it lowers the running threshold, which is how a legacy row records stars it should not display. Those entries were previously being discarded as import noise, which credited some profiles with stars that were never earned. Read as stored, **61** older profiles come back in line with their original records, and will show fewer legacy stars than they did in 5.1.

## Credits

- **DaveTheSpectre** joins the in-game asset contributors list, for a pack of re-animated Carrier models. The **Tal'darim Carrier** skin is the first to use it: it now plays a proper spell animation when casting, where before it fired Plasma Barrage from a completely static pose, and its Plasma Barrage projectiles are tinted to match the skin's red effect set.

