Horizon adds automated policy-driven tiering with hooks to Tundra 



<!-- 
a killer feature:

Real-time per-project usage
Metadata heatmaps
Quota + tier insight without crawling
Works at zettabyte scale
No one has built this cleanly. Build it into Stratum or a side module.
Every HPC admin will want it.

BeeGFS (and most HPC FS) don’t track usage live, they rely on:
Daily cronjobs
Full FS crawls
Manual parsing of du/find
It’s brittle, slow, and error-prone.
You build real-time project-level tracking?
That’s another enterprise-grade product right there.

Plasma:

interactive treemap support/module  visual/reporting module of Horizon via a separate Horizon-querying daemon, like treewiz/baobab does. as fast as that. 
and simple reports to users that show them usage. they can go log in if htey want full analysis. real-time storage heatmaps

**1. Real-time, large-scale introspection**
Cluster-wide, near-instant file usage views (à la WizTree) using in-memory metadata maps, not periodic scans. Needed for responsive admin UIs.

**2. Intelligent cross-cluster tiering**
Data moves between sites based on usage, latency, or project—e.g., idle data migrates to cheaper site. Needs policy engine + remote fetch support (Floe).

**3. Semantic data placement**
Files stored based on content tags, user role, or workflow phase (e.g., genomics → SSD, logs → HDD). Needs metadata classification.

**4. FS-level zero-trust integration**
Embed authz checks per file access, verifying identity at read/open time—not mount time. Requires per-request identity validation (e.g., with mutual TLS/Kerberos).

**5. Universal stub-based lazy recall**
StubFS-like logic that works across all backends (local, cloud, remote clusters), abstracted into a pluggable system. Enables global HSM.

Confidence: 95–99% depending on item.


--> 
