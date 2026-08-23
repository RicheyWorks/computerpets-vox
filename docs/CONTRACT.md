# Vox contract

Do not implement against folklore. Implement against this file.

## Identity

- Product: **Vox**
- Repo: `computerpets-vox`
- Category: AI & GPU
- Idea: TTS Voice Synth
- Port / surface: `8092`

## Must

- Stay canon with 210 species. No illegal hybrids. No swapped voices.
- Treat the desktop overlay as the main quest. This organ is optional until wired.
- Fail soft: the overlay keeps walking if this service is down, unless this *is* the overlay.
- No PII in public artifacts (Steam id, wallet, home path, webcam frames).

## Data

VoiceBank(speciesId, f0, formants, grain) · UtteranceAudio(id, ogg, durationMs)

## Surface

- POST /v1/utter — {petId, text, emotion} → audio/ogg stream
- GET /v1/voicebank/{speciesId} — pitch, speed, phoneme map
- POST /v1/preview — 2-second sample for Creator Studio

## Neighbors

- computerpets-cortex (text in)
- computerpets desktop (audio out)
- computerpets-babel (locale voice packs)

## Failure doctrine

GPU missing → CPU Piper, slower, still works. Unknown glyph → skip, do not crash. Queue overflow → drop oldest, keep newest line.

## Stack

Python 3.12 · Piper / Coqui XTTS · CUDA when present · FastAPI audio stream · species voice banks
