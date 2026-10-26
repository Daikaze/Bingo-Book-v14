# Bingo Book & Target Book — Foundry VTT V14

The V14 port of the [Bingo Book & Target Book V11 module](https://github.com/Daikaze/Bingo-Book), targeting **Foundry VTT 14** with **D&D5e 5.3.3**.

**V11 remains unchanged in its own repository.**

## Install (V14 only)

Paste this manifest URL into Foundry's **Install Module** dialog:

`https://raw.githubusercontent.com/Daikaze/Bingo-Book-v14/main/module.json`

Direct ZIP: [bingo-book-v14-v0.4.1.zip](dist/bingo-book-v14-v0.4.0.zip)

## Features retained from V11 v0.3.8

- Separate **Bingo Book** and **Target Book** tabs, backed by Foundry Journal pages.
- Independent GM-managed player permissions for both books.
- Player-friendly read-only view: image, title, rank categories and bounty ordering; no GM editor controls.
- GM poster editor with Actor reference, imported wanted-poster image, background, rank, status, notes and bounty.
- Status stamps with adjustable size, opacity, rotation and X/Y position.
- **Show in Chat** to everyone or selected recipients (whisper).
- Ranks **S–D** and sorting by bounty (highest/lowest) within rank categories.
- Original responsive stamp and chat poster styling.
- Distinct `bingo-book-v14` module ID to prevent installation clashes with V11. The former `bingo-book` Journal flags are preserved, and saved player permissions are migrated on the first GM launch. Only enable the V14 edition inside Foundry V14.

## V14 adaptation

- Replaced legacy Application with ApplicationV2, preserving the classic two-column interface.
- Migrated the Token scene-control button to V14's keyed scene controls.
- Uses V14 DialogV2 confirmation, FilePicker implementation and window lifecycle.
- Updated Journal sidebar visibility handling for ApplicationV2 rendering.
- Uses an atomic document update when resetting all stamp flags.
- Explicit V14/D&D5e 5.3.3 compatibility metadata and separate V14 installer URL.

## Safety and testing

Back up the Foundry world **before updating to V14**. This port keeps existing Journal metadata and world settings; it does not modify or delete the V11 source repository.

The JavaScript is statically parsed and the manifest validated during publishing. **Not tested inside a running Foundry V14 world**; test with a backup world before production use. D&D5e 5.3.3 is the declared target and later system versions are not yet runtime-verified.

## v0.4.1: Fix manifest installation

- Internal module ID changed to `bingo-book-v14` to avoid collision with an already-installed legacy `bingo-book` module.
- Installer ZIP root now matches the new module ID exactly.
- Existing Bingo Book and Target Book journals and page flags under `bingo-book` are still recognized without editing source data.
- Old permission settings are copied into V14 settings once by GM; original settings stay untouched.
