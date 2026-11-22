# Source tempo and key from an external music library

The prototype will use an external library for recording-level tempo and musical key, and Spotify for playable track identities and playlist creation. Spotify restricts Audio Features access for new integrations, so the playlist builder must match each external measurement to the recording it adds. The choice of library is open. [Spotify endpoint changes](https://developer.spotify.com/blog/2024-11-27-changes-to-the-web-api)

## Coverage test

Compare providers on the same 100 recordings drawn from artists and albums surfaced by review retrieval. Include multiple genres, release periods, and alternate versions. Count a hit when the provider returns both BPM and key for the verified recording. Report ambiguous matches separately and break coverage out by release period. If AcousticBrainz is the only viable source, the prototype may limit its catalog to recordings first released before 2022. Choose the cutoff after the test.
Select the sample from reviewed releases before checking provider availability. Try MusicBrainz as the recording catalog. For each sampled recording, log three outcomes independently: exact version resolved, both BPM and key available from each provider, and exact version matched on Spotify. Report each stage and the end-to-end count against the original 100.
