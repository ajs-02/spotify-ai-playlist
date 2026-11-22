# Retrieve review passages and sequence verified recordings

Merge keyword and semantic search results over review passages, retaining the artist, album, and song references. An open-source model hosted on AWS interprets the prompt and ranks verified candidate IDs. Deterministic code uses those judgments, duration, tempo, and key to order whole recordings. The Spotify MCP server saves the resulting sequence.

Reserve the five evaluation prompts for a blind comparison after fixing the baseline and candidate systems. Use separate prompts for development and training. Aim for 30 minutes per playlist, accept 28–32 minutes, and report duration misses while preserving explicit listener constraints.

Before serving requests, build a versioned index of review passages, resolve reviewed releases against an independent recording catalog, and attach available audio features to their recordings. Use the reviewed release’s track list to generate candidates. A comparison to another artist can trigger further retrieval. Keep the 100-recording provider coverage test separate from the development catalog.

For an underspecified prompt, generate a playlist and show the interpretation in one sentence. Ask for clarification when explicit constraints conflict or the catalog cannot satisfy them.

Evaluate proposed sequences before saving them to Spotify. Test the save operation separately, including recovery from an interrupted write.

Benchmark keyword, semantic, and hybrid search on identical passages and development prompts. Inspect ten results per method for passages supporting suitable recordings and record relevant albums missed by each method.

Generate candidates from verified release editions. If a previewed recording is unavailable at save time, propose a replacement, check both neighboring transitions where applicable, and show the change before saving. Offer a shorter playlist when no suitable replacement exists.
