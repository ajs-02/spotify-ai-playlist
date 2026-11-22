# Give the listener’s activity priority in playlist ranking

Rank recordings using genre and related genres, similarity, themes, and tempo. Use Pitchfork reviews to retrieve cultural context and give descriptions of the individual song precedence over album-wide descriptions. Tempo and harmonic compatibility guide sequencing, but a smoother transition cannot justify a track that conflicts with the requested activity.

Evaluate both the picks and their order through listening tests. Track skips and their reasons so an irrelevant recording and a jarring transition can lead to different corrections.

The prompt determines the relative importance of ranking signals. A recording with missing BPM or key remains eligible unless that measurement is needed to verify an explicit constraint. Unknown measurements earn no transition credit.

Evaluate retrieval, candidate selection, and sequencing separately using five listener-supplied prompts, each targeting a 30-minute playlist. The listener will supply the prompts after the design interview. For fine-tuning, capture evidence-backed preferences between candidates and compare the trained ranker with the initial retrieval-based system on held-out prompts.
## Baseline and sequencing

Compare a non-generative ranker with the AWS-hosted model using the same passages, candidates, explicit constraints, and sequencer. The baseline scores retrieval relevance and available genre and tempo evidence. Later comparisons can substitute a fine-tuned ranker.

Use deterministic beam search to retain several promising partial playlists at each step. Score prompt fit, requested progression, adjacent transitions, and duration. Use a stable tie-breaker.

## Listening outcome

For each blind comparison ask, “Which playlist would you put on again for this activity?” Allow a tie. Report each prompt’s preference, first skip and reason if any, constraint violations, duration, and generation time.
