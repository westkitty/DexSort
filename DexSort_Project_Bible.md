# DexSort Project Bible

**Project:** DexSort  
**Canonical repository:** `westkitty/DexSort`  
**Repository URL:** https://github.com/westkitty/DexSort  
**Default branch:** `main`  
**Document purpose:** Source-ready project bible / build walkthrough / successor-AI handoff  
**Canonical status:** Working project bible, additive source document  
**Created:** 2026-06-13  
**Primary owner:** Andrew Dolby  
**Default build target:** Android tablet  
**Default builder stack:** Google AI Studio for initial Android scaffolding, Antigravity for agentic codebase iteration, Android Studio/Gemini for canonical Android validation and testing  
**Runtime privacy rule:** Build tools may help create DexSort. They must not process the real private image archive.


---

# Canonical Repository

The canonical GitHub repository for this project is:

```text
https://github.com/westkitty/DexSort
```

Repository facts verified in this session:

- Owner/repo: `westkitty/DexSort`
- Default branch: `main`
- Visibility: public
- Initial state before seeding: empty repository
- Intended source-of-truth files:
  - `DexSort_Project_Bible.md`
  - `README.md`
  - `docs/DexSort_AI_Studio_Phases_1_to_5_Prompt.md`
  - `docs/build-phase-ai-firewall.md`
  - `docs/phase-roadmap.md`

All generated Android code, AI Studio exports, Antigravity edits, and future build artifacts should be reconciled against this repository. The repo is the durable source of truth. AI Studio and Antigravity are builders, not the canonical memory.

## Bootstrap Prompt for Successor AI

You are continuing work on **DexSort**, a private, local-first Android image sorting system. Before doing any work, read this file from the canonical repository `westkitty/DexSort`: `DexSort_Project_Bible.md`.

Treat this file as the authoritative project state unless the actual repository or user-provided artifacts prove drift. If this file and the repository disagree, do not rewrite history. Append a reconciliation note.

Your job is to continue the project from the current state while preserving these laws:

1. DexSort is Android-first.
2. The Android tablet is the source archive.
3. DexSort must work without BigMac/Mac by default.
4. AI proposes; the human approves.
5. DexSort must not silently delete, move, upload, rename, strip metadata, or alter originals.
6. Existing user meaning must be preserved: favorites, albums, folders, paths, timestamps, source app clues, tags, projects, concept packs, and provenance.
7. Runtime sorting must be local/private by default.
8. External AI tools may help during the build phase only.
9. Real archive images, real filenames, real folder paths, real manifests, favorites, albums, or private concept packs must not be uploaded to build tools unless the user explicitly approves.
10. Every future meaningful work unit must append to this bible additively.

When implementing, work in small packets. Each packet must include:

- goal,
- scope,
- files/modules,
- assumptions,
- acceptance criteria,
- tests,
- privacy check,
- rollback/recovery note,
- next handoff.

Do not build shiny nonsense. Build the boring safe spine first.

---

# Project Goal

DexSort is a private, local-first Android app for sorting, tagging, searching, and preserving large image archives that live mostly on an Android tablet.

The app should help organize thousands to hundreds of thousands of images without sending the archive to cloud services. Its role is not to autonomously rearrange a user’s life. It is a controlled archive assistant.

DexSort should:

- scan tablet images,
- preserve existing organization,
- detect duplicates and near-duplicates,
- preserve favorites and original folder/album provenance where possible,
- create thumbnails and local indexes,
- support no-AI sorting first,
- optionally add local AI embeddings later,
- support user-defined concept packs,
- support Starsilk-aware and project-aware tagging,
- provide evidence for every generated tag,
- support batch-first review,
- export only through manifest-first, reversible workflows,
- help the user understand what will happen before anything changes.

Final operating principle:

> DexSort preserves meaning first, proposes organization second, and changes files last.

---

# Project Scope

## In scope

DexSort should eventually include:

- Android-native app, Kotlin + Jetpack Compose.
- Local Room/SQLite database.
- Android MediaStore scanner.
- Storage Access Framework support for selected folders and external drives.
- Optional Android Photo Picker for small selected batches.
- Provenance capture.
- Favorites detection where possible.
- Manual favorites import fallback.
- Album/folder/bucket preservation.
- Local thumbnail cache.
- Exact duplicate detection.
- Near-duplicate detection.
- No-AI sorting queues.
- Multi-tag system.
- User-defined concept packs.
- Starsilk/Dexter/project-specific concept packs.
- Tag confidence and evidence.
- Positive and negative example sets.
- Batch review UI.
- Priority queues.
- Progressive indexing.
- Manifest-first export engine.
- Backup-before-cleanup doctrine.
- Operation preview before commit.
- Recovery / “Oh No” mode.
- Local model install/update policy.
- Optional local AI embeddings only after the safe spine works.
- Build-phase AI workflow using AI Studio, Antigravity, Android Studio/Gemini, ChatGPT, Codex, Claude Code, Gemini, Grok, or similar tools.

## Out of scope for the first MVP

Do not build these first:

- cloud sync,
- account system,
- public web service,
- BigMac/Mac server dependency,
- destructive duplicate deletion,
- face recognition,
- identity recognition,
- adult/sensitive-content classification by default,
- full captioning pipeline,
- heavy local vision-language model runtime,
- NDK/Rust implementation,
- Play Store production release,
- multi-device collaboration,
- background secret network calls,
- automatic uploads,
- autonomous reorganization of originals.

## Possible later scope

Later versions may include:

- local CLIP-like embeddings,
- OCR,
- captioning,
- optional external helper mode,
- Rust/JNI high-performance hashing,
- XMP sidecar export,
- browsable HTML archive reports,
- advanced archive timelines,
- local classifier trained on user examples,
- concept-pack marketplace or sharing, only if privacy-safe.

---

# Hard Constraints

## Runtime constraints

- Android-first.
- Tablet-first.
- Local-first.
- No cloud AI dependency.
- No BigMac/Mac dependency.
- No silent upload.
- No telemetry.
- No analytics.
- No automatic crash uploads.
- No destructive edits by default.
- No delete from swipe.
- No move/delete until backup state is known.
- Copy before move.
- Manifest before operation.
- Verify copied files with hashes.
- Preserve provenance before any operation.

## Build-phase constraints

External AI tools may help build DexSort, but:

- do not upload real images,
- do not upload private screenshots unless explicitly approved,
- do not upload real filenames unless sanitized,
- do not upload real folder paths unless sanitized,
- do not upload real manifests unless redacted,
- do not upload real favorites/albums data unless sanitized,
- use synthetic fixtures by default,
- use schema-only examples by default,
- use fake paths and fake filenames,
- keep real concept packs local unless explicitly approved,
- review generated code for telemetry, analytics, remote logging, broad permissions, hidden network calls, unsafe deletion, and overbroad storage access.

## Privacy posture

DexSort protects the archive. It does not judge it.

The app may encounter private, adult, medical, legal, political, queer, financial, emotionally sensitive, or personally identifying images. DexSort must not moralize, shame, upload, expose, or externally classify them.

---

# Current Strategic Decision

## Do we agree AI Studio is the best starting point?

**Yes, with a leash.**

Google AI Studio currently supports building native Android apps from natural language prompts. It can generate a Kotlin + Jetpack Compose project, preview it in a browser-based Android emulator, install it on a physical Android device through WebUSB, and export a Gradle-based project ZIP. That makes it a strong first-pass builder for DexSort’s Android shell and early MVP.

But AI Studio has limits that matter:

- Android apps in AI Studio are client-side only.
- It supports single-activity, single-module projects.
- It uses Kotlin + Jetpack Compose.
- It does not support NDK/native C/C++ code in its Android builder.
- Browser emulator lacks some hardware features.
- GitHub export for Android projects is not available from AI Studio; project export is ZIP-based.

So the correct division of labor is:

| Tool | Best role |
|---|---|
| **Google AI Studio** | First Android scaffold, Compose UI, local Room-style architecture, early APK/device test, prompt-to-project generation. |
| **Antigravity** | Larger agentic build passes, multi-file refactors, implementation packets, test loops, QA artifacts, codebase iteration. |
| **Android Studio + Gemini** | Canonical Android validation, Gradle sanity, emulator/device debugging, profiling, permissions, build/test correctness. |
| **ChatGPT** | Project bible, prompts, architecture, packet slicing, QA ledgers, product decisions. |
| **Codex / Claude Code** | Focused code edits, tests, refactors, diff review, repo-grounded implementation work. |
| **Grok** | Alternate ideation and assumption-breaking, not source of truth. |

AI Studio can do the first major build pass. Antigravity should probably do most of the later codebase surgery. Android Studio remains the adult in the room for real Android validation. Annoying, but true.

---

# Architecture / Design

## MVP architecture

DexSort should start as a native Android app:

- Kotlin.
- Jetpack Compose.
- Material 3.
- Single Activity.
- ViewModels.
- Room/SQLite.
- WorkManager.
- MediaStore.
- Storage Access Framework.
- Android Photo Picker for small batch import.
- Local-only database.
- Local thumbnail cache.
- Manifest-first export engine.
- No AI required for MVP.

## Core modules

| Module | Responsibility | MVP priority |
|---|---|---|
| App Shell | Navigation, theme, settings, top-level screens | Phase 1 |
| Permission Flow | Explain and request safe Android access | Phase 1 |
| Storage Access Layer | MediaStore, SAF, Photo Picker abstraction | Phase 1–2 |
| Provenance Scanner | Capture original folder, bucket, timestamps, source clues | Phase 2 |
| Local Database | Store image records, provenance, tags, decisions | Phase 2 |
| Thumbnail Cache | Generate/store review thumbnails | Phase 2 |
| Device Profiler | Detect storage, battery, thermal, device capability | Phase 3 |
| No-AI Rule Engine | Sort by folder, date, screenshot, filename, dimensions | Phase 3 |
| Duplicate Engine | Exact hash groups, later perceptual hash groups | Phase 4 |
| Tag Engine | Multi-tags, evidence, tag sources | Phase 4 |
| Concept Pack Engine | Starsilk/Dexter/project packs | Phase 5 |
| Review UI | Batch-first review, pile review, tag review | Phase 5 |
| Manifest Engine | Export/copy/undo records | Phase 5+ |
| Recovery Mode | Repair, resume, rollback, manifest replay | Phase 5+ |
| Local AI Engine | Embeddings/OCR/captioning, optional later | Later |

---

# Data Model

## Core entities

DexSort needs a many-to-many archive model, not a folder-only model.

### `MediaItem`

Stores one known image/media item.

Fields:

- `id`
- `androidUri`
- `mediaStoreId`
- `displayName`
- `mimeType`
- `sizeBytes`
- `width`
- `height`
- `dateTaken`
- `dateModified`
- `dateAdded`
- `sourceVolume`
- `bucketId`
- `bucketDisplayName`
- `originalRelativePath`
- `originalAbsolutePathIfAvailable`
- `sourceAppInference`
- `favoriteState`
- `favoriteSource`
- `favoriteConfidence`
- `sha256`
- `perceptualHash`
- `thumbnailPath`
- `scanStatus`
- `lastSeenAt`
- `missingSince`
- `privacyRiskFlags`

### `Tag`

Stores a reusable tag.

Fields:

- `id`
- `name`
- `kind`
- `parentId`
- `description`
- `privacyLevel`
- `createdBy`
- `isSystem`
- `isArchived`

Tag kinds:

- system,
- manual,
- imported,
- provenance,
- concept,
- project,
- review_state,
- privacy,
- export_state.

### `MediaTag`

Many-to-many bridge between media and tags.

Fields:

- `mediaId`
- `tagId`
- `confidence`
- `source`
- `evidenceSummary`
- `evidenceId`
- `approvedByUser`
- `rejectedByUser`
- `createdAt`
- `updatedAt`

### `TagEvidence`

Explains why a tag exists.

Sources:

- original folder,
- original album,
- favorite status,
- filename,
- OCR,
- visual similarity,
- user example,
- user rule,
- manual correction,
- import manifest,
- previous DexSort decision.

### `ConceptPack`

User-defined project/canon/category pack.

Fields:

- `id`
- `name`
- `description`
- `privacyLevel`
- `aliases`
- `forbiddenAliases`
- `ocrKeywords`
- `filenameKeywords`
- `folderKeywords`
- `positiveExampleIds`
- `negativeExampleIds`
- `tagHierarchy`
- `reviewRules`
- `exportRules`

### `ManifestOperation`

Every file operation starts here.

Fields:

- `id`
- `operationType`
- `sourceMediaId`
- `sourceUri`
- `sourceHash`
- `destinationUri`
- `destinationPath`
- `metadataMode`
- `tagsPreserved`
- `favoritesPreserved`
- `albumsPreserved`
- `provenanceSidecarPath`
- `userApprovalRecord`
- `status`
- `error`
- `createdAt`
- `completedAt`
- `undoPlan`

---

# Source Preservation Rules

Before DexSort proposes sorting, it must capture:

- original URI,
- MediaStore ID,
- original bucket/folder,
- original display name,
- original timestamps,
- original MIME type,
- file size,
- dimensions,
- source app/folder inference,
- favorite state if available,
- album membership if available,
- cryptographic hash if computed,
- perceptual hash if computed,
- any existing user meaning.

Favorites are not guaranteed to be accessible across all Android devices/gallery apps. DexSort must provide manual fallback:

1. User opens their gallery.
2. User selects favorites.
3. User shares selected favorites into DexSort.
4. DexSort marks those items as `Favorite` internally.
5. DexSort preserves this state in database and manifests.

Original folder/path preservation is mandatory. Even if DexSort later exports files into new structures, users must be able to search:

- “used to be in Downloads,”
- “used to be in Screenshots,”
- “was favorited,”
- “came from messaging app folder,”
- “was in this album,”
- “was tagged Starsilk but originally from Downloads.”

---

# User Experience Walkthrough

## First launch

DexSort opens with a plain explanation:

> DexSort will scan and organize images locally. It will not upload images. It will not move, delete, rename, or edit originals unless you explicitly approve an operation later.

Then the app asks:

1. What do you want to do first?
   - Map my archive.
   - Find duplicates.
   - Preserve favorites.
   - Sort screenshots.
   - Build Starsilk/Dexter concept packs.
   - Review Downloads.
2. Scope:
   - Whole library.
   - Selected folder.
   - Selected batch.
3. Access:
   - MediaStore access.
   - Folder picker.
   - Photo Picker batch.
4. Mode:
   - No-AI safe mode.
   - Charging-only indexing.
   - Low-storage mode.
5. Backup:
   - Choose export/backup folder now.
   - Skip backup for now, but destructive actions remain locked.

## First useful result

DexSort should show something useful quickly:

| Time | Result |
|---|---|
| 1 minute | Count of images, source folders, rough library map, recent screenshots/downloads. |
| 5 minutes | Folder/bucket explorer, favorites import prompt, first thumbnail grids. |
| 30 minutes | No-AI piles: screenshots, downloads, camera, documents by filename/size/dimensions, obvious duplicates if hashing has begun. |
| Overnight | deeper hashes, near-duplicates, larger indexes, optional embeddings later. |

## Main screens

- Home / Scan Status.
- First Useful Results.
- Inbox.
- Source Folders.
- Favorites.
- Duplicates.
- Near Duplicates.
- Tags.
- Concept Packs.
- Starsilk Review.
- Dexter Review.
- Batch Review.
- Export Queue.
- Manifest Preview.
- Timeline.
- Recovery / Oh No Mode.
- Settings.

## Review gestures

- Swipe right: approve proposal.
- Swipe left: reject proposal.
- Swipe up: show similar.
- Swipe down: send to Needs Review.
- Long press: compare.
- Multi-select: bulk tag/export/approve.
- Tap tag: show evidence.
- Tap source: show original folder.
- Tap warning: explain conflict.

No gesture should delete, move, or destructively alter originals.

---

# Implementation Walkthrough: Phases 1–5

These are the first phases to build. Do not skip ahead to AI embeddings until these work.

## Phase 1 — Android shell and permission-safe onboarding

### Goal

Create the initial Android app shell with a safe onboarding flow.

### Build target

AI Studio can start this phase.

### Features

- Kotlin + Jetpack Compose app.
- Material 3 theme.
- Single-activity architecture.
- Top-level navigation.
- Home screen.
- Onboarding wizard.
- Permission explanation screens.
- Settings screen.
- Privacy promise screen.
- Placeholder screens for:
  - Source Folders,
  - Favorites,
  - Duplicates,
  - Tags,
  - Concept Packs,
  - Export Queue,
  - Recovery.

### Acceptance criteria

- App runs in AI Studio emulator.
- App can install on physical Android device.
- No internet permission in manifest.
- No analytics/crash SDKs.
- No file deletion code.
- Onboarding clearly says no files will be moved/deleted.
- The project exports as a ZIP.

### Privacy check

Search generated code for:

- `INTERNET`
- analytics dependencies,
- crash reporting dependencies,
- remote logging,
- delete operations,
- broad storage permissions beyond what the phase needs.

## Phase 2 — MediaStore scan and local database

### Goal

Index the tablet image library without changing any files.

### Features

- Room database.
- `MediaItem` table.
- MediaStore scan.
- Basic fields:
  - URI,
  - display name,
  - MIME type,
  - size,
  - width/height,
  - date added,
  - date modified,
  - bucket ID,
  - bucket display name.
- Scan status screen.
- Source folder explorer.
- Pause/resume scan state.
- No-AI first useful results.

### Acceptance criteria

- Can scan 100 synthetic/test images.
- Can scan 1,000 images without crashing.
- Can list source folders.
- Can search/filter by bucket/folder.
- App restart preserves database.
- Does not move, delete, rename, or edit files.

## Phase 3 — Provenance capture and device profiler

### Goal

Make DexSort aware of where files came from and what the device can safely do.

### Features

- Provenance fields.
- Source app/folder inference.
- Device profiler:
  - Android version,
  - device model,
  - RAM class,
  - free storage,
  - battery state,
  - charging state,
  - thermal state where available.
- Adaptive mode recommendation:
  - Light,
  - Normal,
  - Charging-only,
  - Low-storage,
  - No-AI.

### Acceptance criteria

- Every scanned item has provenance fields where available.
- App can show “original folder” and “source bucket.”
- App can show device mode recommendation.
- App warns before heavy work if low battery or low storage.

## Phase 4 — Favorites/manual import and exact duplicate skeleton

### Goal

Preserve high-value user meaning and begin safe duplicate detection.

### Features

- Query favorite state if available.
- Manual Favorites import flow:
  - receive shared images,
  - match by URI/hash/metadata where possible,
  - tag as Favorite.
- Exact duplicate scan using hash.
- Duplicate groups screen.
- “No delete” duplicate review.

### Acceptance criteria

- Favorited items can be represented internally even if Android/OEM favorite access fails.
- User can manually import favorite selections.
- Exact duplicates are grouped.
- Duplicate review never deletes.
- Duplicate group shows source folders and favorite state.

## Phase 5 — Multi-tag engine, concept pack skeleton, and batch review UI

### Goal

Build the real DexSort brain: tags, evidence, concept packs, and batch review.

### Features

- Tag table.
- MediaTag table.
- TagEvidence table.
- ConceptPack table.
- Built-in tags:
  - Favorite,
  - Screenshot,
  - Downloads,
  - Camera,
  - Duplicate Review,
  - Needs Review,
  - Metadata Risk,
  - Starsilk,
  - Dexter,
  - UI Reference,
  - Documents.
- Tag evidence panel.
- Batch review screen.
- Concept pack editor skeleton.
- Starsilk concept pack stub.
- Dexter concept pack stub.
- Negative example placeholder.
- “This is not Starsilk” action.

### Acceptance criteria

- One image can have multiple tags.
- Each non-manual tag has evidence.
- User can approve/reject tag.
- User can bulk tag items.
- User can open a concept pack.
- No AI model required yet.
- Concept packs work as rule/manual structures before embeddings.

---

# AI Studio Build Prompt: Phases 1–5

Paste this into Google AI Studio Build mode for the first Android pass.

```text
Build an Android app called DexSort.

DexSort is a private, local-first image archive sorting assistant for Android tablets. The tablet is the source archive. The app must not upload images, must not use cloud inference, must not move/delete/rename/edit originals, and must not include telemetry, analytics, remote logging, or automatic crash uploads.

Build only the first MVP spine: Phases 1–5. Do not add local AI embeddings yet. Do not add cloud features. Do not add face recognition. Do not add delete/move operations.

Tech requirements:
- Kotlin.
- Jetpack Compose.
- Material 3.
- Single-activity architecture.
- ViewModels.
- Room database.
- WorkManager only if needed for scan jobs.
- No server.
- No Firebase.
- No analytics.
- No crash reporting.
- No INTERNET permission.
- No NDK/native code.
- No destructive file operations.

Create these screens:
1. Home / Scan Status
2. Onboarding
3. Permission Explanation
4. Source Folders
5. Favorites
6. Duplicates
7. Tags
8. Concept Packs
9. Batch Review
10. Export Queue placeholder
11. Recovery / Oh No Mode placeholder
12. Settings

Onboarding copy:
- Explain that DexSort scans locally.
- Explain that DexSort will not upload images.
- Explain that DexSort will not move, delete, rename, or edit originals.
- Explain that AI is not required for the first version.
- Ask whether the user wants to scan the whole image library or selected folders later.

Phase 1:
Create the app shell, navigation, onboarding wizard, privacy promise screen, and placeholder screens.

Phase 2:
Implement a MediaStore image scan that reads image metadata without modifying files.
Store results in Room.

MediaItem fields:
- id
- androidUri
- mediaStoreId
- displayName
- mimeType
- sizeBytes
- width
- height
- dateTaken
- dateAdded
- dateModified
- bucketId
- bucketDisplayName
- sourceVolume
- originalRelativePath if available
- favoriteState as UNKNOWN/FAVORITE/NOT_FAVORITE
- favoriteSource
- scanStatus
- lastSeenAt

Phase 3:
Add provenance display and device profile.
Device profile should show:
- Android version
- device model
- available storage
- charging state
- battery percent if available
- recommended mode: Light, Normal, Charging Only, Low Storage, No AI

Phase 4:
Add a Favorites screen and manual favorite tagging support.
If Android favorite state is not available, allow the user to mark selected items as Favorite inside DexSort.
Add an exact duplicate skeleton:
- Create placeholder hash field.
- Create Duplicate Groups screen.
- Do not implement deletion.
- Duplicate actions are review-only.

Phase 5:
Implement multi-tag basics:
Tables:
- Tag
- MediaTag
- TagEvidence
- ConceptPack

Built-in tags:
- Favorite
- Screenshot
- Downloads
- Camera
- Duplicate Review
- Needs Review
- Metadata Risk
- Starsilk
- Dexter
- UI Reference
- Documents

Implement:
- Add/remove tag from an item.
- Bulk tag selected items.
- Tag evidence panel.
- Concept Pack list.
- Concept Pack detail/edit skeleton.
- Starsilk concept pack stub.
- Dexter concept pack stub.
- “This is not Starsilk” negative example action as a stored user correction, no AI required.

Batch Review:
- Display image cards from scanned MediaStore results.
- Multi-select.
- Bulk tag.
- Mark as Needs Review.
- Mark as Favorite.
- Show original folder/bucket on each item.
- Show tags on each item.
- Show evidence for tags when tapped.

Safety:
- No delete button.
- No move button.
- No rename button.
- Export Queue must be placeholder only.
- Every screen that might imply file changes must say “Preview only. Originals remain untouched.”

Add sample fake data mode for emulator testing if MediaStore has no images.

Deliver:
- A working Android app project.
- Clear code comments.
- Clean package structure.
- No internet permission.
- A short README inside the project explaining what is implemented and what is intentionally not implemented.
```

---

# Antigravity Follow-Up Build Prompt

Use this after exporting the AI Studio ZIP and opening it in Antigravity.

```text
You are continuing the DexSort Android project generated by AI Studio.

Read `DexSort_Project_Bible.md` first. Treat it as the source of truth.

Your task is not to redesign the app. Your task is to harden the first MVP spine.

Validate and improve Phases 1–5 only:
1. Android shell and onboarding
2. MediaStore scan and Room database
3. Provenance capture and device profiler
4. Favorites/manual import and exact duplicate skeleton
5. Multi-tag engine, concept pack skeleton, and batch review UI

Rules:
- Do not add cloud features.
- Do not add Firebase.
- Do not add analytics.
- Do not add crash reporting.
- Do not add INTERNET permission.
- Do not add delete/move/rename operations.
- Do not add local AI embeddings yet.
- Do not add face recognition.
- Do not use real private images.
- Use synthetic fixtures and emulator-safe fake data.

Audit:
- AndroidManifest permissions.
- Gradle dependencies.
- Room schema.
- MediaStore query safety.
- App restart persistence.
- Low/no image library behavior.
- UI copy for privacy clarity.
- Batch review safety.
- Tag evidence consistency.

Produce:
- A task list.
- A diff summary.
- Test plan.
- Risk notes.
- Any required fixes.
- A short append-only ledger entry for `DexSort_Project_Bible.md`.
```

---

# Build-Phase Tool Plan

## AI Studio

Use for:

- first Android scaffold,
- Compose screens,
- Room schema skeleton,
- MediaStore scan proof,
- fake-data emulator mode,
- device install smoke test.

Do not use for:

- final security confidence,
- complex multi-module architecture,
- native Rust/JNI,
- production release,
- real archive processing.

## Antigravity

Use for:

- repo-level iteration,
- implementation packets,
- refactoring,
- test writing,
- artifact generation,
- build validation,
- UI improvements,
- privacy audits.

Do not let it run wild. One packet at a time.

## Android Studio + Gemini

Use for:

- Gradle validation,
- emulator/device tests,
- profiler,
- permissions,
- Android API correctness,
- build errors,
- real device debugging.

## ChatGPT

Use for:

- project bible,
- specs,
- prompts,
- context compression,
- implementation packet slicing,
- QA inspection,
- contradiction ledgers.

## Codex / Claude Code

Use for:

- focused code edits,
- tests,
- refactors,
- schema changes,
- code review.

## Grok

Use for:

- alternative ideas,
- challenge assumptions,
- generate weird but possibly useful workflow variants.

Do not use Grok as source of truth.

---

# Validation Checklist Before Moving Past Phase 5

Do not proceed to local AI embeddings until all are true:

- App runs on physical Android tablet.
- No `INTERNET` permission.
- No telemetry dependencies.
- No destructive operations.
- MediaStore scan works.
- Database persists across restart.
- Source folder/bucket view works.
- Manual Favorite marking works.
- Multi-tag works.
- Tag evidence exists.
- Batch review works.
- Concept pack skeleton works.
- Starsilk/Dexter stubs exist.
- Recovery screen exists.
- README exists.
- Privacy copy is clear.
- Synthetic fixture mode exists.
- At least 100-image test passes.
- At least 1,000-image test is planned or passes.

---

# Open Questions

1. What exact Android tablet model is the first target?
2. What Android version is it running?
3. Are most images in DCIM, Pictures, Downloads, Screenshots, messaging app folders, or mixed?
4. Does the device gallery expose favorites through MediaStore?
5. Is Google Photos involved, and are images fully local or cloud-backed?
6. Is a USB-C external drive available for backup/export tests?
7. Should DexSort be Play Store-bound eventually, or personal APK only?
8. Should the first concept packs be Starsilk + Dexter, or Starsilk only?
9. Should AI Studio produce just the scaffold, or also the initial Room schema?
10. What is the first test collection size: 100, 1,000, or larger?

---

# Current State Summary

DexSort has completed research and correction passes. The current direction is:

- Build a new native Android app.
- Do not fork an existing gallery app wholesale.
- Salvage ideas from existing tools.
- Build no-AI safe spine first.
- Preserve provenance before sorting.
- Use multi-tags and virtual collections instead of folder-only categorization.
- Add local AI later.
- Use AI Studio for the first Android scaffold.
- Use Antigravity for heavier implementation iteration.
- Use Android Studio/Gemini for validation.
- Keep build tools away from real archive data.

---

# File Map

Recommended eventual repository structure:

```text
DexSort/
  DexSort_Project_Bible.md
  README.md
  app/
    build.gradle.kts
    src/main/
      AndroidManifest.xml
      java/com/dexsort/
        MainActivity.kt
        DexSortApp.kt
        data/
          DexSortDatabase.kt
          MediaItemEntity.kt
          TagEntity.kt
          MediaTagEntity.kt
          TagEvidenceEntity.kt
          ConceptPackEntity.kt
          ManifestOperationEntity.kt
        media/
          MediaStoreScanner.kt
          StorageAccessManager.kt
          ProvenanceMapper.kt
          FavoriteDetector.kt
        device/
          DeviceProfiler.kt
        tags/
          TagEngine.kt
          ConceptPackEngine.kt
        review/
          BatchReviewViewModel.kt
        ui/
          screens/
            HomeScreen.kt
            OnboardingScreen.kt
            SourceFoldersScreen.kt
            FavoritesScreen.kt
            DuplicatesScreen.kt
            TagsScreen.kt
            ConceptPacksScreen.kt
            BatchReviewScreen.kt
            ExportQueueScreen.kt
            RecoveryScreen.kt
            SettingsScreen.kt
  docs/
    privacy-model.md
    build-phase-ai-firewall.md
    test-plan.md
    concept-pack-format.md
```


---

# Added Build Enhancements and Guardrails

These improvements should be carried forward into AI Studio, Antigravity, Android Studio, and any future coding agent workflow.

## Repository-first workflow

1. Seed `westkitty/DexSort` with the Bible and prompts before generating app code.
2. Generate the first scaffold in AI Studio.
3. Export the AI Studio project as a ZIP.
4. Unpack it into the repository.
5. Commit the generated scaffold in a separate commit from the documentation seed when possible.
6. Use Antigravity for controlled implementation packets.
7. Use Android Studio/Gemini for actual Android build, Gradle, emulator, and device validation.
8. Update this Bible after each meaningful work unit.

## First five build packets

The first five packets are deliberately no-AI and no-destruction:

1. **App shell and onboarding:** navigation, privacy promise, placeholder screens.
2. **MediaStore scan and Room database:** read-only image metadata indexing.
3. **Provenance and device profiler:** original bucket/folder/source clues and device mode recommendation.
4. **Favorites/manual import and duplicate skeleton:** preserve favorites and show exact duplicate groups without deletion.
5. **Multi-tag engine and concept-pack skeleton:** tags, evidence, Starsilk/Dexter stubs, batch review.

## Better-than-basic MVP improvements

Add these if they do not destabilize the first build:

- Fake-data mode for emulator and AI Studio preview.
- Sample synthetic MediaStore-like records for testing.
- Privacy audit screen showing app permissions and what DexSort refuses to do.
- Onboarding option: `Map archive only` for users who are anxious about file changes.
- Visible `Originals untouched` status badge on review/export-adjacent screens.
- `Why this tag?` evidence panel from the beginning, even if the first evidence is only folder/rule-based.
- `Not this` correction actions before any AI model exists.
- `Needs Review` and `Low Confidence` tags as first-class states.
- `Manual Favorites Import` as a visible fallback, not a hidden advanced feature.
- `Recovery / Oh No Mode` placeholder early so recovery is treated as core product architecture.

## First real test collections

Use only synthetic or explicitly approved test images.

Recommended test sets:

- 20-image smoke test.
- 100-image emulator/device test.
- 1,000-image performance test.
- Synthetic duplicates set.
- Synthetic folder provenance set.
- Fake favorites import set.
- Fake Starsilk/Dexter concept-pack examples.
- Low/no-media library test.

## Stop conditions

Pause and reassess before proceeding if any of these happen:

- App requests `INTERNET` permission.
- Generated code adds Firebase, analytics, crash reporting, or remote logging.
- App contains delete/move/rename operations before manifest/export safety exists.
- MediaStore scan mutates files.
- Room schema cannot survive restart.
- Tags cannot store evidence.
- Batch review implies destructive action.
- AI Studio produces opaque code that cannot be safely audited.
- Android Studio build fails and the cause is not understood.

## Repository hygiene

The repo should remain clean and source-focused:

- Do not commit real image archives.
- Do not commit private screenshots.
- Do not commit generated APKs unless there is a release reason.
- Do not commit local IDE junk.
- Do not commit secrets, keys, tokens, keystores, or signing configs.
- Do not commit `.gradle/`, `build/`, or generated local caches.
- Keep docs and implementation packets explicit.

---

# Chronological Ledger

## Entry 1 - DexSort project bible created

**Summary:** Created the first DexSort Project Bible as a source-ready Markdown handoff and build walkthrough.

**Reason / Intent:** User requested a complete project bible to place into project sources and guide future ChatGPT/AI Studio/Antigravity work.

**Files Changed:**  
- `DexSort_Project_Bible.md`

**Commands Run:**  
None inside a DexSort repository yet.

**Command Intent:**  
None.

**Outputs Generated:**  
- Project bible.
- AI Studio Phases 1–5 build prompt.
- Antigravity follow-up build prompt.
- Tool division plan.
- Phase 1–5 walkthrough.
- Validation checklist.

**Decisions:**  
- AI Studio is approved as the first scaffold builder, with caveats.
- Antigravity is preferred for later agentic codebase iteration.
- Android Studio/Gemini remains the Android validation authority.
- First build scope is Phases 1–5 only.
- No local AI embeddings until safe no-AI spine works.
- No BigMac/Mac dependency.
- No real archive data in build tools.

**Bugs / Blockers:**  
- First physical Android tablet model/version unknown.
- Favorites behavior on target device unknown.
- Real image distribution unknown.
- No repository exists yet in this context.

**Correction:**  
None.

**State After Completion:**  
DexSort has a source-ready project bible and first builder prompt.

**Next Step / Handoff:**  
Paste the AI Studio Phases 1–5 prompt into Google AI Studio Build mode. Generate the Android project. Export the ZIP. Then open the ZIP in Antigravity and use the Antigravity follow-up prompt.

## Entry 2 - Seed canonical GitHub repository

**Summary:** Updated the DexSort Bible to name `westkitty/DexSort` as the canonical repository and prepared the documentation seed for the repo.

**Reason / Intent:** User selected `https://github.com/westkitty/DexSort` as the repository and requested the updated Bible, phase prompt, enhancements, and repository reference be committed and pushed.

**Files Changed:**  
- `DexSort_Project_Bible.md`  
- `README.md`  
- `docs/DexSort_AI_Studio_Phases_1_to_5_Prompt.md`  
- `docs/build-phase-ai-firewall.md`  
- `docs/phase-roadmap.md`  
- `.gitignore`

**Commands Run:**  
- GitHub connector repository verification for `westkitty/DexSort`  
- GitHub connector file creation commits

**Command Intent:**  
- Verify the repository exists and is writable.  
- Seed the repository with the canonical planning documents before any Android scaffold is generated.

**Outputs Generated:**  
- Repository-aware Project Bible.  
- AI Studio Phases 1–5 prompt.  
- README.  
- Build-phase AI firewall documentation.  
- Phase roadmap.  
- Android-oriented `.gitignore`.

**Decisions:**  
- `westkitty/DexSort` is the canonical source repository.  
- The repository is the durable source of truth; AI Studio and Antigravity are builders only.  
- First implementation remains Phases 1–5 only.  
- No local AI embeddings until the no-AI safety spine works.  
- No real image archive data is allowed in build tools or repository fixtures unless explicitly approved.

**Bugs / Blockers:**  
- Local `gh` CLI was unavailable in the current runtime, so a literal local `git add && git commit && git push` flow could not be used here.  
- Repository seeding used GitHub connector commits instead of local git staging.

**Correction:**  
- Repository metadata has been added to the Bible.  
- The earlier Bible statement that no repository existed is superseded by this entry.

**State After Completion:**  
- DexSort has a canonical GitHub repository.  
- Project documentation seed is committed to `main`.  
- Next step is to use the AI Studio prompt to generate the Android scaffold, export the ZIP, and import it into the repo as the first app-code commit.

**Next Step / Handoff:**  
- Paste `docs/DexSort_AI_Studio_Phases_1_to_5_Prompt.md` into Google AI Studio Build mode.  
- Generate the Android project.  
- Export the ZIP.  
- Unpack into `westkitty/DexSort`.  
- Use Antigravity follow-up prompt from the Bible to harden the scaffold.  
- Append Entry 3 after the AI Studio scaffold is imported.
