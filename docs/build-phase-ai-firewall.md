# DexSort Build-Phase AI Firewall

External AI tools may help build DexSort. They must not process the real private image archive.

## Allowed build-phase uses

- Generate Android scaffold code.
- Draft Jetpack Compose screens.
- Propose Room schemas.
- Review architecture.
- Generate synthetic fixtures.
- Write tests.
- Review code for safety.
- Produce documentation.
- Create implementation packets.

## Forbidden without explicit approval

- Uploading real images.
- Uploading private screenshots.
- Uploading real filenames.
- Uploading real folder paths.
- Uploading real manifests.
- Uploading real favorites/albums data.
- Uploading real concept packs if they contain private canon/project material.
- Letting an external tool classify the real archive.

## Default fixture policy

Use synthetic fixtures:

- fake MediaStore records,
- fake folder names,
- fake image filenames,
- fake favorites,
- fake albums,
- fake Starsilk/Dexter examples,
- fake duplicate groups,
- fake low-storage conditions.

## Code audit checklist

Before accepting generated code, search for:

- `INTERNET`
- Firebase
- analytics
- crash reporting
- remote logging
- network clients
- upload code
- delete/move/rename operations
- broad storage permissions
- unsafe background services
- face/identity recognition logic

If any appear, stop and explain why they are present before continuing.
