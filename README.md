# DexSort

DexSort is a local-first Android media organization project.

Canonical repository:

```text
https://github.com/westkitty/DexSort
```

## Source of truth

The intended source-of-truth file is:

```text
DexSort_Project_Bible.md
```

Platform write checks blocked creation of that filename during this seed pass, so the current README temporarily carries the project Bible summary until the file can be added from a normal local checkout.

## Core project laws

1. Android-first.
2. Tablet-first.
3. Local-first runtime.
4. No BigMac/Mac dependency by default.
5. No cloud AI dependency in the app.
6. No telemetry or remote logging.
7. No destructive file actions in the MVP.
8. AI proposes; the human approves.
9. Preserve provenance before proposing organization.
10. Build the no-AI safety spine first.

## First build path

Use Google AI Studio for the first scaffold, then export the ZIP and import it into this repository. Use Antigravity for repo-level hardening. Use Android Studio/Gemini for Android build, permission, emulator, and device validation.

## First five phases

1. App shell and onboarding.
2. MediaStore scan and Room database.
3. Provenance capture and device profiler.
4. Favorites/manual import and exact duplicate skeleton.
5. Multi-tag engine, concept-pack skeleton, and batch review UI.

Do not add embeddings, face recognition, network features, or destructive file actions before these phases pass.

## Early enhancements

- Fake-data mode for emulator testing.
- Map Archive Only onboarding path.
- Originals Untouched status badge.
- Privacy Audit settings screen.
- Needs Review and Low Confidence tags.
- Why This Tag evidence panel.
- Manual Favorites Import fallback.
- Recovery / Oh No Mode placeholder.

## Stop conditions

Pause if generated code adds internet permission, Firebase, analytics, remote logging, destructive file actions, file mutation during scan, tags without evidence, or batch review that implies destructive action.

## Next step

Paste the AI Studio prompt from the local artifact into Google AI Studio Build mode, generate the Android scaffold, export ZIP, and import it here as the first app-code commit.
