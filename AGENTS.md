# Agent Instructions

## Project Wiki Workflow

- Use the project-wiki-query skill for wiki-backed questions and lightweight project knowledge lookups.
- Use the project-wiki-research skill for ad-hoc topic research when docs/wiki does not already answer the request; save any sourced report under raw for later ingest.
- Check docs/wiki first when answering questions about this project, then verify the answer against authoritative project files before replying. The wiki is a synthesis layer, not the source of truth.
- When reviewing project files reveals durable project knowledge that is not captured in the wiki, create a raw wiki fragment under raw before synthesizing it into docs/wiki.
- Raw wiki fragments should name the source file, record the extracted facts, and note the wiki page or topic that should receive the synthesis.
- Respect federation boundaries. Keep local practice, workflow, governance, adoption, and implementation knowledge in this wiki, and route broad ecosystem entity background to the upstream AI wiki when it owns that scope.
- Keep fragments out of raw/processed until the knowledge has been synthesized into docs/wiki and wiki lint has passed.
- After wiki edits, raw research, raw ingest, or workflow guidance updates are verified, commit the coherent wiki work before finishing unless the user explicitly says not to commit.
