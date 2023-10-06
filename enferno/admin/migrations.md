# Migration (timestamp: 1696610684902)
## Added Columns:
- Added `verification_date` column with type DateTime and index set to True.
- Added `verification_status` column with type String index set to True default set to 'Unverified'.

## Removed Columns:
- Removed `ref` column with type ARRAY(String).

## SQL Commands:
```
ALTER TABLE bulletin DROP COLUMN ref;

ALTER TABLE bulletin ADD COLUMN verification_date TIMESTAMP;

ALTER TABLE bulletin ADD COLUMN verification_status VARCHAR(16) DEFAULT 'Unverified';

```