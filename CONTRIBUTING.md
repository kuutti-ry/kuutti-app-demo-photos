# Contributing

A picture gets here only through the prompt sheet of the app's repository, [`docs/demo/photo-prompts.md`](https://github.com/kuutti-ry/kuutti-app/blob/main/docs/demo/photo-prompts.md): the model, its settings and one prompt per picture.

1. **Generate** with the sheet's model and settings. Never a real person, a stock photo or a scraped picture, and no prompt that names a real person or asks for a likeness.
2. **Look at every picture** before it comes in: one adult, face visible, nobody who could be read as under 18, nothing suggestive, and no text, logo, brand, licence plate or house number anywhere. Zoom in on clothes, packaging and backgrounds; fix what you find with an edit of the same model, and say so in the provenance row.
3. **Lay it out** as 1200x1600 JPEG without metadata, in `faces/<key>/` or `negatives/`. A new persona needs its key in the app's `packages/db/src/seed/personas.ts` first; a key is never renamed or reused.
4. **Add its row** to `PROVENANCE.md`: what it is, the model, the prompt id, any edit, the terms and the date.
5. **Write the manifest** in the app's repository with `pnpm demo:assets -- --manifest <this checkout>`, and copy the same list here as `manifest.json`.
6. **Open two pull requests**, here and in the app's repository. After both are reviewed the maintainer tags the release here, and then the app's pull request merges.

Every commit carries a `Signed-off-by` line certifying the [Developer Certificate of Origin](https://github.com/kuutti-ry/kuutti-app/blob/main/DCO), as in the app's repository. By contributing you dedicate your contribution to the public domain under [CC0 1.0](LICENSE).

The app's [Code of Conduct](https://github.com/kuutti-ry/kuutti-app/blob/main/CODE_OF_CONDUCT.md) applies here.
