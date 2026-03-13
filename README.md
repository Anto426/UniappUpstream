<p align="center">
  <img src="./assets/uniapp-icon.webp" alt="UniApp icon" width="120" height="120">
</p>

<h1 align="center">UniApp Upstream</h1>


<p align="center">
  <img alt="Canale beta" src="https://img.shields.io/static/v1?label=&message=CANALE%20BETA&color=d97706&style=for-the-badge">
</p>


<p align="center">
  Repository di distribuzione per il canale release Android di <strong>UniApp</strong>.
  Qui vengono pubblicati l'APK corrente, il manifest degli aggiornamenti usato dall'app e i metadati della release.
</p>

<p align="center">
  <a href="https://raw.githubusercontent.com/Anto426-Project/UniappUpstream/main/src/release/androidApp-release.apk"><img alt="APK stabile" src="https://img.shields.io/static/v1?label=&message=STABILE%20APK&color=1f6f5f&style=for-the-badge"></a>
  <a href="https://github.com/Anto426-Project/UniappUpstream/raw/main/src/release/beta/androidApp-release.apk"><img alt="APK beta" src="https://img.shields.io/static/v1?label=&message=BETA%20APK&color=d97706&style=for-the-badge"></a>
  <a href="./update.json"><img alt="Manifest JSON" src="https://img.shields.io/static/v1?label=&message=MANIFEST%20JSON&color=cb5a2e&style=for-the-badge"></a>
</p>

## Panoramica

Questo e' il repository di deploy delle build Android di UniApp.
E' pensato per restare semplice, stabile e leggibile anche da script:

- `src/release/stable/` contiene APK e metadati stabili
- `src/release/beta/` contiene APK e metadati beta
- `update.json` espone i manifest separati per canale sotto `channels`
- `README.md` riassume la release pubblica corrente

## Release Corrente

| Campo | Valore |
| --- | --- |
| App | UniApp |
| Repository | `Anto426-Project/UniappUpstream` |
| Versione corrente | `1.6.1-beta` |
| Canale release | `beta` |
| Version code | `162` |
| Pubblicata il | `2026-03-13` |
| Versione minima supportata | `1.6.1-beta` |
| Aggiornamento obbligatorio | `true` |
| App abilitata | `true` |
| Package name | `com.anto426.uniapp` |
| Min SDK | `29` |
| File APK | `src/release/beta/androidApp-release.apk` |
| Dimensione APK | `100.5 MB` |

## Link Rapidi

- [Scarica APK corrente](https://github.com/Anto426-Project/UniappUpstream/raw/main/src/release/beta/androidApp-release.apk)
- [Metadati del canale corrente](./src/release/beta/output-metadata.json)
- [Percorso APK del canale corrente](./src/release/beta/androidApp-release.apk)
- [APK stabile](https://raw.githubusercontent.com/Anto426-Project/UniappUpstream/main/src/release/androidApp-release.apk)
- [APK beta](https://github.com/Anto426-Project/UniappUpstream/raw/main/src/release/beta/androidApp-release.apk)
- [Apri il manifest aggiornamenti](./update.json)

## Note Di Rilascio

Changelog 13 Mar 2026:
- Aggiornamento automatico certificati TLS.

## Struttura Repository

```text
assets/
  uniapp-icon.webp
src/
  release/
    stable/
      ...
    beta/
      ...
update.json
README.md
```

## Feed Aggiornamenti

L'app legge `update.json` per capire se esiste una build piu' recente.
I campi principali sono:

- `channels.stable.release`
- `channels.beta.release`
- `latestVersion`
- `downloadUrl`
- `publishedAt`
- `buildCommit`

`downloadUrl` punta attualmente a:

`https://github.com/Anto426-Project/UniappUpstream/raw/main/src/release/beta/androidApp-release.apk`

## Flusso Di Pubblicazione

Questo repository viene aggiornato automaticamente dal workflow GitHub Actions del repository principale di UniApp.
Ogni pubblicazione aggiorna:

1. l'APK sotto `src/release/stable/` oppure `src/release/beta/`
2. il relativo `output-metadata.json`
3. `update.json`
4. questo `README.md`

## Note

- Questo repository e' un endpoint di release, non il repository principale di sviluppo.
- I file pubblicati possono cambiare a ogni nuova release.
