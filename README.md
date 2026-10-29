# MovieFlix releases and updates

This public repository is the official MovieFlix Android **release and update-feed repository**. It hosts the public update manifest (`movieflix.json`) and APK assets attached to GitHub Releases. Application source code is maintained separately in the private [`mauricegift/movieflix`](https://github.com/mauricegift/movieflix) repository.

## Download MovieFlix

Download the latest stable APK from [GitHub Releases](https://github.com/mauricegift/movie-flix/releases/latest). The APK asset name must be exactly **`movieflix.apk`** so the in-app updater can retrieve it.

## Update manifest

`movieflix.json` is read by the Android app’s update checker. Its current schema is:

```json
{
  "latestVersion": "1.0.3",
  "minimumVersion": "1.0.0",
  "forceUpdate": false,
  "message": "MovieFlix 1.0.3: improved green theme, automatic update installer FileProvider cache-path failure.",
  "downloadUrl": "https://github.com/mauricegift/movie-flix/releases/latest/download/movieflix.apk"
}
```

For a release, publish a signed APK as a GitHub Release asset named `movieflix.apk`, then set `latestVersion`, `minimumVersion` (normally unchanged), `message`, and `downloadUrl` in `movieflix.json`. App builds must increment both `versionName` and `versionCode`; Android’s updater rejects equal or lower build codes.

## Signing and release security

Do not upload signing keys, passwords, certificates intended to be private, or signing secrets to this public repository or its Releases. All production APKs must use the same private MovieFlix release keystore. The application package is `com.movieflix.app`; it is a new package identity and does not replace the former KeithFlix package. If the signing key is lost or changed, existing MovieFlix installations cannot receive normal in-place updates.

## Maintainer and contact

**Maurice Gift**  
Email: [maurice@gifted.co.ke](mailto:maurice@gifted.co.ke)  
GitHub: [github.com/mauricegift](https://github.com/mauricegift)  
Telegram: [t.me/mauricegift](https://t.me/mauricegift)  
WhatsApp Channel: [Join MovieFlix updates](https://whatsapp.com/channel/0029VbCpYtZLtOj5LDuj7Q1p)

This repository is for app distribution and update metadata only. MovieFlix depends on upstream services; availability and compatibility may change.
