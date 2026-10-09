# kuutti-app-demo-photos

Test and demo pictures for [Kuutti](https://github.com/kuutti-ry/kuutti-app), a free, non-commercial dating app for Finland: the faces of the demo personas, the pictures the moderation queue is meant to refuse, and later a pool of faces for the synthetic population.

> **Every picture here is AI-generated, and nobody in them is a real person.** They are test data. Never use them as anybody's profile, on any service, nor in marketing or a store listing. `PROVENANCE.md` names the model, the prompt and the date of each file; the pictures were made with Google's Gemini API, which marks its images with an invisible SynthID watermark.

## The personas

The key is the persona's id: the folder of its pictures (`faces/<key>/`), the login at the app's mock bank, and the key of its story. A key is never renamed and never reused. The app's `packages/db/src/seed/personas.ts` and `histories.ts` are the source of this table; the codes are those of the test persons of Telia's pre-production bed, artificial by the population register's rule (individual number 900 to 999).

| key | name | born | test bank | in the demo | pictures |
|---|---|---|---|---|---|
| `aino` | Aino Virtanen | 29.12.1992 | Nordea `DEMOUSER2` | newcomer: the walkthrough | 5 |
| `mikael` | Mikael Lindqvist | 1.1.1970 | Ålandsbanken `12345678` | newcomer, in Swedish | 4 |
| `sanna` | Sanna Korhonen | 17.6.1977 | Nordea `DEMOUSER4` | a complete profile | 5 |
| `onni` | Onni Korhonen | 1.2.2000 | Nordea `DEMOUSER1` | registered, never onboarded | 8 |
| `noa` | Noa Salmi | 3.8.1983 | Nordea `DEMOUSER3` | a profile with two photos, and the moderation queue | 2, and `negatives/exif-location.jpg` |
| `kerttu` | Kerttu Åkerlund | 1.2.1980 | Säästöpankki `22222222` | accepted an older wording of the terms | 4 |
| `tapio` | Tapio Heikkinen | 7.7.1970 | OP, prefilled | banned | 3 |
| `ilona` | Ilona Öhman | 1.1.1970 | Aktia, prefilled | deleted her account | 3 |

## Rules

1. **Generated pictures only**, from a generator whose terms allow this use. Never a stock photo, never a picture scraped from anywhere, never a photo of a real person, a team member included.
2. **Every file has its row in `PROVENANCE.md`**: where it came from, when, under which terms. A picture without one is removed.
3. **Nothing personal, nothing secret.** No location in EXIF other than the one test file that shows the upload pipeline strips it, which carries an invented place at sea.
4. **A release is a tag**, and a tag is never moved or deleted: a changed set is a new tag. The app pins one by tag and by the SHA-256 of every file (`packages/db/src/seed/photos-manifest.ts`, the same list as `manifest.json` here) and fetches `https://github.com/kuutti-ry/kuutti-app-demo-photos/archive/refs/tags/<tag>.tar.gz`; a file whose checksum differs is refused.

## Layout

```
faces/<key>/*.jpg     a persona's pictures, 1200x1600 JPEG without metadata
negatives/*.jpg       what moderation refuses: no face, several people, text; and the EXIF test file
manifest.json         every file with its SHA-256 and what it is for
PROVENANCE.md         every file with its source and terms
LICENSE               the terms the pictures are held under
```

## Who

The same people as the app's repository: the owners and the `contributors` team.
