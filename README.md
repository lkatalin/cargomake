# cargomake

| Command               | Expected result                    | Actual result                    |
| ----------------------|:----------------------------------:|---------------------------------:|
| `cargo make test`     | skips tests in `topleveltestcrate` | runs all tests in all crates     |
| `cargo make test-flow`| skips top level then runs it       | runs test and post in all crates |

Running with `--no-workspace` runs zero tests.
Probably some nesting and forking are in order, ex:
```
[tasks.workspace-task]
condition = { channels = ["beta", "stable"] }
env = { "CARGO_MAKE_WORKSPACE_SKIP_MEMBERS" = ["member3", "member4"] }
run_task = { name = "member-task", fork = true }
```

But is there any simpler way?
