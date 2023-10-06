# Migration (timestamp: 1696610684902)
## Added Columns:
- Added `verification_date` column with type DateTime and index set to True.
- Added `verification_status` column with type Enum Nullable set to False index set to True.

## Removed Columns:
- Removed `ref` column with type ARRAY(String).

## SQL Commands:
```
ALTER TABLE bulletin DROP COLUMN ref;

ALTER TABLE bulletin ADD COLUMN verification_date TIMESTAMP;

CREATE TYPE verification_status_enum as ENUM ('VERIFIED','UNVERIFIED','FALSE_FAKE');

ALTER TABLE bulletin ADD COLUMN verification_status verification_status_enum NOT NULL DEFAULT 'Unverified';

```