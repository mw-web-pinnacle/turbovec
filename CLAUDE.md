## Handoffs list
I keep one list of open tasks across all my chats and code sessions, split by whether the next move is mine or Claude's: https://claude.ai/artifact/Co2ywvWkRt3tpd1rLkPy1b (ArtifactData tool, collection `tasks`). Keep it current without being asked, using the /handoff skill when it's available:

* You start work I handed you that outlives your reply (background agent, long build, PR waiting on tests): add a record, owner `claude`.
* The next move becomes mine (review or merge a PR, answer a question, run a test, a manual step, a decision): set owner `matt` and rewrite the sentence as what I do next.
* Finished or dropped: status `done`.

Record fields: `text` (one sentence, the next action), `owner` (`matt`|`claude`), `status` (`open`|`done`), `session` (2–5 words, same on every record from this session), `repo` (`owner/repo` or ""), `link` (your Claude-Session URL), `source` (`code`), `created`/`updated`/`closed` (ISO UTC; `closed` null until done). Find this session's records by querying `status == open` and `link == <your Claude-Session URL>`, and pass each record's `version` as `if_version` when updating. The detail stays in the session. If you can't reach the list, tell me in one line.
