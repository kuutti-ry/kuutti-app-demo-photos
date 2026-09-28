# kuutti-app-demo-photos

Pictures for the demo mode of [Kuutti](https://github.com/kuutti-fi/kuutti-app) (issue #73, ADR-014): the photos of the personas of the mock bank, the pictures the moderation queue is meant to refuse, and later a pool of faces for the synthetic population.

**Nobody in here is a person.** And nothing in here is published: the repository is private, and its pictures appear in no public material, no store listing and no screenshot that leaves the team.

## Rules

1. **Generated faces only**, from a generator whose terms allow this use. Never a stock photo, never a picture scraped from anywhere, never a photo of a real person, a team member included.
2. **Every file has its line in `PROVENANCE.md`**: where it came from, when, under which terms. A picture without one is removed.
3. **Nothing personal, nothing secret.** No photo from anybody's phone, no screenshot of a real account, no location in EXIF other than the one test file that exists to show that the pipeline strips it, which carries an invented place.
4. **The app's repository never holds the pictures.** It holds a manifest with the tag of a release here and the checksum of every file, and a command downloads the release and verifies it.

## Layout

```
faces/<set>/*.jpg     a persona's photos, or a pool for the population
negatives/*           what moderation refuses: no face, several people, text, and the files that test the pipeline
manifest.json         every file with its SHA-256 and what it is for
PROVENANCE.md         every file with its source and terms
LICENSE               the terms the pictures are held under; written with the first pictures
```

A release is a tag. The app's repository pins one.

## Who

The same people as the app's repository: the owners and the `contributors` team.
