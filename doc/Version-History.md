### 1.1 (2013-10-06)

Bug fix:

- Panic due to out of memory on several 32-bit machines.
- Fix several incorrect HTTP API content type.

Improvements:

- Remove per-collection padding buffer and replace it by a shared string buffer, to reduce memory consumption.
- Creation of data file no longer creates a giant empty buffer beforehand, therefore reducing memory consumption.
- Documents may now have optional persistent IDs (called UID) which will never change during its life time.
- API version 3 (New!) supports document operations based on UIDs.

### 1.0 (2013-09-21)

Another maintenance release to address all outstanding issues, with feature improvements and new APIs.

Bug fix:

- Scalability problem on a model of laptop has been resolved.
- Collection update will no longer panic under a rare data corruption situation.

Improvements:

- Data file IO now uses more granular locks (RWlock-per-bucket and RWlock-per-document) instead of giant RW file lock.
- API version 2 (New!)
- New HTTP endpoints to report server runtime performance.
- New query syntax - easier and more efficient, together with a new query processor.
- A specific type of range query (integer lookup in a range) is now supported.

Known issues: None

### beta (2013-07-12)

A maintenance release to address outstanding issues discovered in alpha.

Bug fixes:

- Data durability is greatly enhanced by periodically (every minute) synchronising file buffers with storage device.
- Support durable write operations which flush all buffers immediately after collection operation.
- Fix wrong content type returned by several HTTP API endpoints.

Improvements:

- tiedot can now run on Windows platform.
- tiedot now has a web control panel for managing collections/indexes/documents and run queries.

Known issue:

- Under a rare and specific data corruption situation, document update may panic.

### alpha (2013-06-28)

Initial release.

Known issues:

- Under a rare and specific data corruption situation, document update may panic.
- Several HTTP API endpoints return incorrect content type.
- File buffers in memory are not periodically synchronised with underlying storage device, thus reducing data durability.