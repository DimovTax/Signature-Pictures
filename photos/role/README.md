# Role / sales inbox images

Brand-scoped so each role inbox uses **its own** image.

## Why subfolders
Role names repeat across brands — `hello@` exists on dimovtax, dimovaudit and
richmondstreetadvisors; `info@` exists on six brands. A flat `photos/hello.png`
would let one brand's logo overwrite another's, which is exactly how
**Richmond's logo ended up on a Dimov Tax signature**. Scoping by brand makes
that impossible.

## Layout

```
photos/role/<brand>/<inbox>.png          <- the photo (e.g. George Dimov headshot)
photos/role/<brand>/<inbox>-banner.png   <- the brand banner/logo for that inbox
```

## Example URLs

```
https://cdn.jsdelivr.net/gh/DimovTax/Signature-Pictures@main/photos/role/dimovtax/hello.png
https://cdn.jsdelivr.net/gh/DimovTax/Signature-Pictures@main/photos/role/dimovtax/hello-banner.png
https://cdn.jsdelivr.net/gh/DimovTax/Signature-Pictures@main/photos/role/richmondstreetadvisors/hello-banner.png
```

`_MAP.csv` lists every file with its brand, inbox, size and type.

## Rules
- **Never** reference a role image from a different brand's folder.
- **Never** put a role-inbox image in the flat `photos/` directory.
- Role-inbox signatures are managed by hand and are deliberately excluded from
  the bulk signature tooling.
