# timestamps
```sql
CREATE TABLE test (
  id INTEGER NOT NULL PRIMARY KEY AUTOINCREMENT,
  create_at INTEGER DEFAULT (strftime('%s','now')),
  update_at INTEGER DEFAULT (strftime('%s','now'))
);

CREATE TRIGGER test_update
  AFTER UPDATE ON test
BEGIN
  UPDATE test
  SET update_at = (strftime('%s','now'))
  WHERE id = OLD.id;
END;
```

# logs
```sql
CREATE TABLE test (
  id INTEGER NOT NULL PRIMARY KEY AUTOINCREMENT,
  value TEXT NOT NULL
);

CREATE TRIGGER test_update
  AFTER UPDATE ON test
  WHEN OLD.value <> NEW.value
BEGIN
  INSERT INTO test_log (time, id, old, new)
  VALUES (strftime('%s','now'), OLD.id, OLD.value, NEW.value);
END;
```
