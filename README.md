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
  <a href="https://raw.githubusercontent.com/Anto426-Project/UniappUpstream/main/src/release/beta/androidApp-release.apk"><img alt="APK beta" src="https://img.shields.io/static/v1?label=&message=BETA%20APK&color=d97706&style=for-the-badge"></a>
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
| Versione corrente | `1.5.2-beta` |
| Canale release | `beta` |
| Version code | `9` |
| Pubblicata il | `2026-03-12` |
| Versione minima supportata | `1.5.0-beta` |
| Aggiornamento obbligatorio | `true` |
| App abilitata | `true` |
| Package name | `com.anto426.uniapp` |
| Min SDK | `29` |
| File APK | `src/release/beta/androidApp-release.apk` |
| Dimensione APK | `100.3 MB` |

## Link Rapidi

- [Scarica APK corrente](https://raw.githubusercontent.com/Anto426-Project/UniappUpstream/main/src/release/beta/androidApp-release.apk)
- [Metadati del canale corrente](./src/release/beta/output-metadata.json)
- [Percorso APK del canale corrente](./src/release/beta/androidApp-release.apk)
- [APK stabile](https://raw.githubusercontent.com/Anto426-Project/UniappUpstream/main/src/release/androidApp-release.apk)
- [APK beta](https://raw.githubusercontent.com/Anto426-Project/UniappUpstream/main/src/release/beta/androidApp-release.apk)
- [Apri il manifest aggiornamenti](./update.json)

## Note Di Rilascio

Changelog 12 Mar 2026:
- Architettura: migrazione del layer `presentation` verso `domain/logic` con rinomina moduli e test correlati.
- Dati backend: introdotte policy di accesso/cache (`CACHE_FIRST`, `REMOTE_FIRST`, `STALE_WHILE_REVALIDATE`, `NETWORK_ONLY`) con merge e integrity check.
- Sicurezza: aggiunta migrazione dati utente verso cifratura applicativa e migliorata gestione persistenza sicura.
- Stato app: refactor del coordinamento globale con transizioni animate e gestione loading unificata.
- UI/Auth: aggiornate schermate Login, AppLock, AppBlocked, ForcedUpdate e Beta enrollment con fallback null-safe e UX migliorata.
- Navigazione/UI: introdotti `AppSceneContainer`, `AppMotion`, miglioramenti AppTopBar e BottomBar per animazioni piu fluide.
- Localizzazione: conversione estesa di stringhe hardcoded in `stringResource` + aggiornamento `strings.xml`.
- API remote: uniformati messaggi di errore e fallback localizzati su didattica, feature, survey, transport e update.
- Notifiche/background: migliorati coordinator notifiche, worker sync e gestione canali Android.
- Multi-piattaforma: aggiunti `AppScreenControl` e `RuntimeLogcatRecorder` per Android/iOS.

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

`https://raw.githubusercontent.com/Anto426-Project/UniappUpstream/main/src/release/beta/androidApp-release.apk`

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
