# cargomake

| Command               | Expected result                    | Actual result                    |
| ----------------------|:----------------------------------:|---------------------------------:|
| `cargo make test`     | skips tests in `topleveltestcrate` | runs all tests in all crates     |
| `cargo make test-flow`| skips top level then runs it       | runs test and post in all crates |
