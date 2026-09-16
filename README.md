# HyperOffline

An offline, **text-only** archive of the HyperLab forum (`hyperlab.info/inv/`)
as a SQLite database, with a terminal browser for reading it.

**The archive is on the [Releases page](../../releases/latest).** Download it there.

## Contents of the release archive

| file | what |
|---|---|
| `hyperlab.db` | SQLite database — 4 forums, ~2,900 topics, ~125,000 posts, ~2,300 members, with a full-text search index. Text only; attachments/images are noted in-line but not included. |
| `hyperlab_tui.py` | A [Textual](https://textual.textualize.io/) terminal UI: forum → topic tree, post reader, full-text search. |

## Use

    tar -xf HyperOffline.tar.xz && cd HyperOffline
    pip install textual
    python3 hyperlab_tui.py            # or --db <path>

Keys: `Enter` open · `[` `]` page a long topic · `/` search · `f` forums · `g`/`G` top/bottom · `q` quit.

Or query the database directly with any SQLite client:

    sqlite3 hyperlab.db "SELECT author_name, posted_raw, body
                         FROM posts WHERE topic_id=28456 ORDER BY position"
