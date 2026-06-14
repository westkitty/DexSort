# DexSort AI Studio Build Prompt - Phases 1 through 5

Paste this into Google AI Studio Build mode. Canonical repo after export: https://github.com/westkitty/DexSort

```text
Build an Android app called DexSort.


Repository handoff:
- After generating the project, the code will be exported and committed to https://github.com/westkitty/DexSort.
- Include a README describing that this is Phases 1–5 only.
- Keep the code clean enough for Antigravity and Android Studio to continue.
- Do not treat AI Studio as the permanent source of truth; the GitHub repository is the source of truth.

Extra safety UX requirements:
- Add an always-visible “Originals untouched” badge on review-adjacent screens.
- Add a Privacy Audit screen or Settings section listing what DexSort does not do: no uploads, no cloud AI, no telemetry, no delete/move/rename in MVP.
- Add fake-data mode for emulator testing if no MediaStore images exist.
- Add “Map archive only” as the safest onboarding path.
- Add “Needs Review” and “Low Confidence” as visible review states.

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
