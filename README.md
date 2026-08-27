# Dimov Tax — Email Signature Assets

Public asset repo for all email-signature images (staff photos, brand banners, contact/social icons).

Hosting these ourselves means they can never be purged by a third party again — the previous
hosts (WiseStamp CDN and gifyu) deleted our images, which broke ~200 signatures.

## Folder structure

```
photos/     staff profile photos   — filename = email local-part, e.g. kirill.png
banners/    brand logos            — filename = brand, e.g. wattercpa.png
icons/      contact + social icons — e.g. phone.png, linkedin.png
```

## How to reference an image in a signature

Use the **jsDelivr CDN** URL (free, global CDN, built for this — preferred):

```
https://cdn.jsdelivr.net/gh/<OWNER>/<REPO>@main/photos/kirill.png
https://cdn.jsdelivr.net/gh/<OWNER>/<REPO>@main/banners/wattercpa.png
https://cdn.jsdelivr.net/gh/<OWNER>/<REPO>@main/icons/phone.png
```

The direct GitHub URL also works, but GitHub discourages hot-linking it for production
assets and applies soft rate limits, so prefer jsDelivr above:

```
https://raw.githubusercontent.com/<OWNER>/<REPO>/main/photos/kirill.png
```

## Requirements

- The repository must be **public** (signature images are fetched by recipients' mail
  clients with no login, so they must be publicly reachable — this is true of every
  signature image host).
- No build step, no deploy, no Vercel/Pages needed. Push a file and it is live.

## Adding or replacing a photo

1. Add/replace the file in `photos/` using the person's email local-part as the filename
   (e.g. `jane.doe@dimovtax.com` -> `photos/jane.doe.png`).
2. Commit and push.
3. jsDelivr caches for up to 7 days. To force a refresh immediately, either use a
   version/commit-pinned URL, or purge via `https://purge.jsdelivr.net/gh/<OWNER>/<REPO>@main/photos/jane.doe.png`.

## Notes

- Photos are 400x400 (displayed at 200x200 in signatures — 2x for retina).
- Brand banners keep each brand's own logo; never use one brand's logo/mainline on another.
