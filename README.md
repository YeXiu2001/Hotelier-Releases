# Hotelier Database Handoff

Use this when passing an existing Hotelier NativePHP desktop database to another Windows computer.

## On Your Computer

1. Close the Hotelier desktop app.
2. Open a terminal in the project folder:

```bash
cd /Users/raymart/Herd/hotelier
```

3. Make sure SQLite writes any pending data into the main database file:

```bash
sqlite3 database/nativephp.sqlite "PRAGMA wal_checkpoint(FULL);"
```

4. Send this file to the other computer:

```text
database/nativephp.sqlite
```

5. Rename the sent file to:

```text
database.sqlite
```

## On The Other Windows Computer

1. Install Hotelier.
2. Open Hotelier once, then close it.
3. Press:

```text
Win + R
```

4. Paste this path:

```text
%APPDATA%\Hotelier\database
```

5. Press Enter.
6. Replace the existing file:

```text
database.sqlite
```

with the `database.sqlite` file you received.

7. Open Hotelier again.

The app should now use the passed database.
