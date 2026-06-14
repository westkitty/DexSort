# DexSort

DexSort is a private, local-first Android image archive assistant.

The Android tablet is the source archive. DexSort is designed to scan, map, tag, review, and eventually help sort large image libraries without uploading images to cloud services and without silently changing originals.

## Canonical project rules

- Android-first.
- Tablet-first.
- Local-first.
- No BigMac/Mac dependency by default.
- No cloud AI dependency.
- No telemetry, analytics, remote logging, or automatic crash uploads.
- No silent upload.
- No silent delete, move, rename, metadata stripping, or original alteration.
- AI proposes; the human approves.
- Preserve provenance before proposing organization.
- Build the no-AI safety spine first.

Read the project Bible first:

```text
DexSort_Project_Bible.md
```

## Current repository purpose

This repository has been seeded with the project Bible and initial build prompts. The first app-code commit should come from Google AI Studio Phases 1–5, then be hardened in Antigravity and validated in Android Studio/Gemini.

## First build target

Use:

```text
docs/DexSort_AI_Studio_Phases_1_to_5_Prompt.md
```

That prompt intentionally builds only the first MVP spine:

1. Android shell and onboarding.
2. MediaStore scan and Room database.
3. Provenance capture and device profiler.
4. Favorites/manual import and exact duplicate skeleton.
5. Multi-tag engine, concept pack skeleton, and batch review UI.

Do not add local AI embeddings, cloud features, face recognition, delete/move operations, or network permissions in the first build.

## Builder workflow

1. Use AI Studio to generate the Android scaffold.
2. Export the generated project ZIP.
3. Unpack it into this repository.
4. Use Antigravity to harden Phases 1–5.
5. Use Android Studio/Gemini for real Android validation.
6. Append each meaningful work unit to `DexSort_Project_Bible.md`.

## Privacy warning

Do not commit real private images, real archive manifests, private screenshots, real filenames, or personal folder paths. Use synthetic fixtures unless Andrew explicitly approves otherwise.
