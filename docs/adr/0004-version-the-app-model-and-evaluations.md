# Version the application and model independently

Package the application with a Dockerfile. Serve the open-source model separately on AWS and warm it before prototype sessions. The longer-term product is a hosted web app for listeners.

Maintain the evaluation runner after launch. Save the retrieved passages, independently sourced candidate pool, and application and model revisions for each run. Replay fixed inputs to compare rankers and rerun retrieval when evaluating a retrieval change.

The first web release offers a public playlist preview. Allowlisted pilot listeners can save a private Spotify playlist and receive its link. Retrying an interrupted save resumes the same playlist and preserves the intended order without adding duplicate tracks.

Target zero out-of-pocket prototype costs. Benchmark CPU inference on development prompts before choosing GPU infrastructure. Record cold start, warm playlist generation time, and ranking quality.

After the first blind comparison, retain the five original prompts as regression cases. Use fresh held-out prompts for subsequent blind comparisons once earlier results have influenced development.
