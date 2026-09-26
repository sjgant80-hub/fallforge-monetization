# FallForge — Growth Rails: Affiliate · White-Label · NFT · Crypto (deep dive)

**Kar, 2026-09-26.** Extends the monetization ladder (sjgant80-hub/fallforge-monetization). The core
thesis holds — sell the proof, never the code — and these are the *channels* that put it in front of more
payers. The unlock: **the estate already owns the crypto-native primitives NFT/web3 promised and mostly
failed to deliver** — an ownable capability wallet, a signed provenance-royalty cascade, transferable
credentials, Merkle anchoring, and a p2p mesh — all sovereign, MIT, and provable. So the play is to use the
conventional rails for reach and lean on the native primitives as the moat.

---

## 1 · AFFILIATE — two layers: a conventional program on top, a signed royalty cascade underneath

**The conventional layer (do first, it's plumbing):** an affiliate/reseller program on FirstPromoter or
PartnerStack (PartnerStack alone fronts 100k+ B2B partners). The 2026 shape that works:
- **Affiliates (dev influencers, newsletters, "own-your-AI" creators):** 30% *lifetime recurring* on Sovereign
  Care, plus a flat bounty per done-for-you mint. Recurring-on-the-retainer is what makes it passive and
  sticky — a one-off bounty gets a post; a lifetime cut gets a channel.
- **Resellers (agencies who own the account):** up to 100% of month one + 20–30% recurring, they keep the
  client relationship (this bleeds straight into white-label, §2).
- **The viral artifact is the signed scorecard.** Every mint ends in a downloadable, tamper-evident receipt
  that can say *you LOST*. That's the hook no competitor has — a proof that can fail is more shareable than a
  brag. Put a referral handle in the scorecard's metadata so a scorecard that gets passed to a boss is a
  tracked referral.

**The native layer (the moat — already built): `the-wallet` + `lineageSplit`.** The estate's wallet kernel
already carries a **signed, bounded provenance-royalty cascade**: when value V is realized downstream, it
mints upstream credit V·(decay)^level, with the total payout bounded so **provenance appreciates but payout
can never run away**. That is an affiliate/royalty network *enforced by cryptography in the kernel*, not by a
SaaS honour system — a partner who mints a model that another partner builds on gets a signed, verifiable,
capped cut, forever, with no platform in the middle. `attenuates` lets a partner delegate only a subset of
their capability + budget to *their* sub-partner. This is the thing to demo to a serious channel partner:
"your referrals are signed and un-forgeable, and the split is math, not our promise."

**Sequence:** stand up FirstPromoter for the conventional cut now (weeks), wire the scorecard referral handle,
and position `lineageSplit` as the "signed affiliate rail" for the marketplace tier.

## 2 · WHITE-LABEL — the strongest channel, and the fastest scale

This is where the estate's architecture is already the product. Everything is **mint → prove → run**, and it
is **already re-skinnable per brand**: a `kard` carries a `skinRef`, and konomi-skins / konomi-design-kit are
the theming layer. An agency doesn't integrate anything — they drop their brand on a working proof-and-mint
stack and resell it. The GoHighLevel / Vendasta model, applied to provable AI.

**Packaging:**
- **Skin (light white-label) — £500–£1,500/mo + rev-share.** Their logo, colours and domain on the mint +
  own-vs-rent calculator + scorecard. The estate runs underneath; you handle infra, they handle clients.
- **OEM (full white-label) — £2,500–£6,000/mo license + their own pricing.** Their brand end-to-end, their
  price to their clients, they run first-line onboarding/support; you keep the engine, the gate and the
  updates. Optionally per-seat above a floor.
- **Foundry-in-their-box (white-label Tier 2):** an agency ships the air-gapped foundry to *their* enterprise
  clients under their name — the highest-ticket reseller motion, and the write-off argument travels with it.

**Why this scales faster than direct sales:** every AI agency and dev-shop is looking for a sovereign/proof
story to sell to clients spooked by cloud lock-in and (from Dec 2027) the AI Act. You give them a finished
one with a gate no one else has. One good white-label partner is a sales team you don't pay a salary.

**Build needed:** a brandable config (logo/colour/domain/pricing pulled from a `kard` skinRef) + a partner
runbook. The skin kernel exists; this is packaging, not invention.

## 3 · "NFT" — ownable proof, not collectibles (reframe hard; the substance is already built)

NFT-as-JPEG is dead and toxic; don't touch it. But the *real* primitive underneath NFTs — a **signed,
ownable, verifiable, transferable-or-soulbound credential** — is exactly what the estate already mints:

- A **`kard`** is a signed capability token: ownable, its scope enforced by `canOpen`, its spend by
  `spendGate` — a transferable (or soulbound) credential, done sovereign.
- A **scorecard / proof-of-play receipt** is a **Verifiable Credential**: an issuer (the gate) attests that a
  model beat its baseline, checkable without a central database — the SBT/VC pattern (cf. Ethereum
  Attestation Service, Galxe, POAP), but MIT and re-runnable.
- **`kcc-mint`** already mints provenance bundles with real conformance levels **L1 sovereign → L2 anchored →
  L3 attested → L4 canonical**, Ed25519-signed (1,410 live), and **`kar-anchor`** is a Merkle content anchor —
  so a credential can be **optionally anchored to a public chain/timestamp** for third-party provenance
  *without* putting anything sensitive on-chain.

**The offer:** "own your proof." A minted model, its scorecard, and its lineage are credentials the buyer
*holds* and can verify or hand to an auditor — anchored on-chain only when public provenance is wanted. This
is the **Kard Marketplace** (ladder Tier 4): pre-minted, proven organs and boot-keys trade as verifiable
credentials, with the `lineageSplit` royalty flowing to their origin on every resale — the one legitimate
"NFT royalty" mechanic, done right and capped.

**The privacy answer (the estate already has it):** the web3 credential world's unsolved problem is that a
permanent public token can leak sensitive data. The estate's `perimeter` (confidentiality) and `chaff`
(decoys) mean disclosure is selective and anchoring is opt-in — you anchor a *hash*, never the content.

**Recommendation:** build the credential substance (you're ~90% there), ship it as "ownable, verifiable
proof," and stay out of speculative NFT drops entirely — the substance is the moat, the collectible is the
liability.

## 4 · CRYPTO — a payment rail, a settlement/anchor rail, and a native distribution rail. Not a coin.

- **Payment:** accept stablecoin (USDC/EUR-C) alongside Stripe for mints, kards and white-label licenses —
  global, instant, low-friction, and it fits the sovereign buyer's worldview. Fiat off-ramp is where KYC and
  counsel enter; the on-ramp (accepting stablecoin) is the easy, high-value first step.
- **Settlement / anchoring:** `kcc` is the internal credit for the marketplace/fork-tree economy, and
  `kcc-mesh` is deliberately **"no money out"** — a closed credit/points economy, not a security. On-chain
  anchoring (`kcc-mint` L2, `kar-anchor`) gives public, timestamped provenance for a proof without a token.
- **Native distribution:** the mesh (`r7` + `webrtc`, `fallroom`) is already crypto-native — p2p, no server,
  identity-as-address, kards as **bearer credentials**. That is how a marketplace of proven organs moves
  without a platform in the middle.

**The wall, stated as strategy not caution:** a speculative token / coin launch is off-thesis and a securities
minefield — it would turn "provable AI you can trust" into "another crypto project," and it's the one move
that invites regulators before you have a single enterprise reference. **Don't.** Keep `kcc` as closed credit,
take stablecoin as payment, anchor hashes for provenance, and let the mesh be the distribution. If a real
token economy is ever wanted, it goes through counsel as its own decision — and only after the boring revenue
(mint, foundry, care) is real.

---

## The one insight that ties it together

**FallForge is web3's substance without web3's baggage.** the-wallet (ownable capability + signed, bounded
royalties), kard (transferable credential), kcc-mint (provenance mint), kar-anchor (Merkle anchor), and the
mesh (p2p bearer credentials) are the ownable / verifiable / royalty-bearing / decentralized primitives that
NFTs and tokens promised and mostly failed to deliver — here they're sovereign, MIT, and *provable*. So the
growth strategy writes itself:

1. **White-label is the scale channel** — every agency becomes a reseller of the proof rail (skin + OEM). Do
   this first; it multiplies reach without headcount.
2. **Affiliate is the reach channel** — conventional program now (FirstPromoter, 30% lifetime recurring on
   Care), the signed `lineageSplit` royalty cascade as the native, un-forgeable version underneath.
3. **"NFT" = ownable proof** — ship the credential substance (kard + scorecard + kcc + anchor) as the Kard
   Marketplace; skip speculative drops.
4. **Crypto = payment + anchor + mesh** — take stablecoin, anchor hashes, distribute p2p; no coin.

Every one of these sells the same one thing the ladder already sells: **proof you own and anyone can re-run.**

Sources on the 2026 market shape: SaaS reseller/affiliate commission models (PartnerStack, FirstPromoter,
GoHighLevel/Vendasta white-label); web3 credential formats (NFT vs SBT vs Verifiable Credential; Ethereum
Attestation Service, Galxe, POAP, Gitcoin Passport) and the public-token privacy paradox.
