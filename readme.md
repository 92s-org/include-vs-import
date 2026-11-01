## import_role vs include_role

| Aspect | `import_role` (static) | `include_role` (dynamic) |
|---|---|---|
| When processed | At playbook parse time, before any task runs | At runtime, when that task is reached |
| `when:` condition | Copied to **every task** inside the role, and checked once per task | Checked **once**, on the include itself; if false, the role is skipped entirely, if true it wont care if the tasks inside change the facts |
| Tags | Inherited by all tasks inside the role | Apply only to the include task, unless you use `apply:` |
| Loops (`loop:`) | ❌ Not supported | ✅ Supported |