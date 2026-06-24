From the video:
https://www.youtube.com/watch?v=RQckIBzOCsA&list=PLdVLOietcHTD3OjLupQ6oEQWEeKXLVozO&index=1

The video proposes a specific folder structure designed to provide **context-aware guidance** for AI agents, preventing them from guessing or forgetting project decisions. The core components of this architecture are as follows (2:47 - 7:53):

- **The Router (claude.md):** A single, thin file at the root of the project (maximum 200 lines). Its purpose is to **route** the AI to the correct documentation for a specific task rather than containing all the information itself. This prevents the AI from becoming overwhelmed by too much data (3:10 - 4:16).
- **Rules Layer (.claude folder):** Contains conventions such as build rules, design system standards, and reusable component catalogs. This ensures the AI follows consistent standards instead of reinventing existing components (4:29 - 4:58).
- **Knowledge Layer:** A single reference file containing the technical facts of the project. It provides a source of truth so the AI does not have to rederive basic facts in every session (5:00 - 5:21).
- **Documentation Layer:** Organized by **lifespan** rather than topic, consisting of four subfolders:
    1. **Active:** Living plans for work currently in progress (5:39 - 5:42).
    2. **Decisions:** A record of choices made (e.g., picking a library or database) and the reasons behind them. This prevents re-litigating settled decisions later (6:48 - 7:39).
    3. **Reference:** Stable documents like runbooks, registries, and integration guides (5:49 - 5:55).
    4. **Archive:** Finished work marked as "do not follow," preserving history without misleading the AI into thinking old plans are still valid (5:56 - 6:46).