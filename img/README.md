# Images

LaTeX has no `object-fit: cover`, so every photo slot in `main.tex` uses a
pre-cropped file (the `*_crop.jpg` files) sized to exactly the box it fills.
If you swap in a different source photo, re-crop it to the same pixel size
so it doesn't distort or need re-measuring in the .tex file. The pattern
(needs ImageMagick's `convert`):

```bash
# resize to *cover* WxH, then crop from the centre to exactly WxH
convert source.jpg -resize "<W>x<H>^" -gravity center -extent "<W>x<H>" out_crop.jpg
```

Used in `main.tex`, and the source photo each came from:

| File                  | Box size (mm) | Used as                  | Source photo         |
|------------------------|---------------|---------------------------|------------------------|
| `hero_crop.jpg`         | 210 x 140     | Page 1 hero                | `hero.jpg`             |
| `hero_gradient.png`     | 210 x 140     | Fade over the hero (regenerate with `make_gradient.py` if you resize the hero) | — |
| `detail_crop.jpg`       | 182 x 30      | Page 1 detail banner       | `teahouse2.jpg` (cropped higher up, so the performers' heads are in frame) |
| `riderwide_crop.jpg`    | 47 x 30       | Page 2 rider, wide photo   | `machine-detail.jpg`  |
| `ridernarrow_crop.jpg`  | 25.5 x 30     | Page 2 rider, tall photo (springs in flame) | `springs-fire.jpg` (TrorkMV2)    |
| `strip1_crop.jpg`       | 57 x 28       | Page 2 photo row 1, 1st (robotic slide bass) | `bass-picks.jpg` |
| `strip2_crop.jpg`       | 66 x 28       | Page 2 photo row 1, 2nd (springs, live)      | `springs-live.jpg` |
| `strip3_crop.jpg`       | 57 x 28       | Page 2 photo row 1, 3rd (autonomous xylophone) | `xylo-detail.jpg` |
| `strip4_crop.jpg`       | 57 x 28       | Page 2 photo row 2, 1st (Byggefestivalen)    | `bygge-005.jpg` |
| `strip5_crop.jpg`       | 66 x 28       | Page 2 photo row 2, 2nd (Byggefestivalen)    | `bygge-022.jpg` |
| `strip6_crop.jpg`       | 57 x 28       | Page 2 photo row 2, 3rd (Byggefestivalen)    | `bygge-023.jpg` |

At 200dpi, mm-to-pixels is `px = mm * 7.874`.

To regenerate `hero_gradient.png` after re-cropping the hero (it must match
`hero_crop.jpg`'s pixel size exactly), run `python3 make_gradient.py`.

A few extra source photos (`teahouse.jpg`, `crowd-alt.jpg`, `audience.jpg`,
`performer-crowd.jpg`, `wide-duo.jpg`) are included but not currently used —
handy if you want to swap one of the photos later.
