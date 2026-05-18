# Predictions — methodology validation

**Predictions made:** 2026-05-18
**Verification date:** 2026-06-17 (30 days from now)
**Method:** YouTube view counts at verification date, fetched via yt-dlp metadata.

The pitch behind the spot-scorer's Playbook moves is that a spot which
commits cleanly to *either* extreme (brand-color flood OR world-color
cede) outperforms a spot stuck in the muddle. This file commits that
claim to a falsifiable test before knowing the outcome.

## The five spots

| | Spot | Url | Camp (from scoring) | Prediction |
|---|---|---|---|---|
| 1 | Pilsner Urquell — *Alfons* | <https://www.youtube.com/watch?v=dLDHfeOEp38> | Coherent world: gap 102° + 86% music, both signals agree | **TOP performer** |
| 2 | McDonald's — *Fakt si myslíš* | <https://www.youtube.com/watch?v=NecSnK0H3Eo> | Brand-color committed: McD yellow on screen + voice-led, both promotional | **TOP performer** |
| 3 | Lidl — *Vše pro skvělé grilování* | <https://www.youtube.com/watch?v=Oz047619h6U> | Brand-color flood: 5.5° gap, 56% anchor presence | **TOP performer** |
| 4 | Albert — *Objevte nové gourmet receptury* | <https://www.youtube.com/watch?v=Dxbx6r6Jdvg> | Incongruous: 174° world-color + 88% voice (see Albert case study) | **BOTTOM performer** |
| 5 | Vodafone — *Nejlepší pevný internet v Česku* | <https://www.youtube.com/watch?v=dGMa5T3_3N4> | Telecom muddle: 15° gap + 95% voice — neither committed nor distinctive | **BOTTOM performer** |

## The two falsifiable claims

**Claim A — directional.** Across the 30-day window from 2026-05-18 to
2026-06-17, the absolute view-count increment of spots 1, 2 and 3
(coherent commitments) will sum to more than the increment of spots
4 and 5 (muddle / incongruity).

**Claim B — ranking.** When the five spots are ranked by 30-day view
delta, the coherent set (1, 2, 3) will hold the top three positions
in some order, and the muddle set (4, 5) will hold the bottom two.

## Honest caveats

- **View counts are confounded.** Existing total views, channel
  subscriber count, paid promotion budget, current cultural moment,
  and YouTube's algorithm all matter more than creative coherence
  for monthly view growth. With n=5 spots from different channels,
  any "result" here is illustrative, not statistically meaningful.
- **Vodafone's spot is a year-old reupload pattern.** Telecom YT
  channels often re-cycle the same creative; the spot picked here
  may be a "pinned hit" that distorts the delta.
- **The prediction is partly aesthetic.** If view counts contradict
  the prediction, that's a real finding about *what predicts
  YouTube performance* in 2026 (recall, algorithm, subscriber base),
  not necessarily that the methodology is wrong about creative
  coherence. The methodology measures the spot; YouTube measures
  the spot + every other factor.

## Verification procedure

On 2026-06-17, run:

```bash
for url in \
  "https://www.youtube.com/watch?v=dLDHfeOEp38" \
  "https://www.youtube.com/watch?v=NecSnK0H3Eo" \
  "https://www.youtube.com/watch?v=Oz047619h6U" \
  "https://www.youtube.com/watch?v=Dxbx6r6Jdvg" \
  "https://www.youtube.com/watch?v=dGMa5T3_3N4"; do
  yt-dlp --skip-download --print "%(id)s %(view_count)s %(like_count)s %(title)s" "$url"
done
```

Compare to baseline view counts at the time of writing (Bára can
record these by running the same command on 2026-05-18 and committing
the output as `BASELINE_2026-05-18.txt`).

Append the result to this file with a `## Results — 2026-06-17`
section. State plainly which claim held, which didn't, and what that
implies about the methodology's predictive value vs descriptive value.

The point of this file is not to prove the methodology right. It's
to commit it to a check, in public, before the data lands. That's
the part most analytical portfolios skip.
