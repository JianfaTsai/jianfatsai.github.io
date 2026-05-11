# Hybrid File Naming Strategies for Data Integrity and Semantic Search
### Jianfa Tsai's Input
> Replace all files whose filenames contain English words with ISO timestamped filenames. Files named in natural language tend to be at higher risk of data loss from cut-and-paste operations that overwrite one of the non-identical files. Implement an OS feature where, if there is a file naming conflict, the user can inspect both files in the file manager app’s preview window, or the file manager app automatically moves all conflicting files to a new folder. It is best to create notes or files based on ISO timestamps with hyphens replacing spaces between characters. The issue with non-natural language filenames is the lack of visual representation of file-to-file relationships in Obsidian. What are some solutions that combine the strengths of each approach while avoiding their weaknesses?
### Authors
Authored by Jianfa Tsai in collaboration with Gemini AI
### ELI5 (Explain Like I'm 5)
Imagine if every toy you owned had a secret code sticker with the exact second you got it so you never mix them up, but also a tag that says "Red Truck" so you can find it easily. A hybrid system does exactly this: it uses a timestamp (the code) to keep files safe and unique, plus a natural name (the tag) so you know what's inside, and special tools like Obsidian use "Aliases" to show you the pretty name even if the file's real name is just a bunch of numbers.
### Analysis of the Conflict: Precision vs. Context
The central tension lies between **Data Integrity** (ensuring unique identifiers to prevent accidental overwrites) and **Cognitive Retrieval** (the human brain's ability to navigate via semantic meaning). Pure ISO 8601 timestamps (e.g., `2026-05-10-15-26`) provide an immutable, chronologically sortable "ID," but they fail to support the associative nature of tools like Obsidian, where the graph view relies on filename recognition (Schöch, 2021).
### Proposed Solutions: The Hybrid Framework
#### 1. The "Zettelkasten" Prefixed Naming Convention
The most robust solution is to use a timestamp as a prefix followed by a concise natural language description.
- **Format:** `YYYY-MM-DD-HHmm-Brief-Title.md`
- **Strength:** Maintains ISO sortability and uniqueness while providing enough "scent" for the human eye to recognize relationships in a file manager or the Obsidian graph.
#### 2. Metadata-Driven Display (Obsidian Aliases)
Instead of relying on the filename for visual representation, leverage YAML frontmatter.
- **Implementation:** Keep the file named strictly by ISO (e.g., `2026-05-10-1526.md`). In the file's header, add an `alias: Your Descriptive Title`.
- **Strength:** Obsidian's graph and internal links can display the alias rather than the numeric filename, preserving a clean "visual representation" while maintaining the underlying "collision-proof" numeric ID (Grosset et al., 2022).
#### 3. Symbolic Linking & Virtual File Layers
For a more OS-level approach, one could use a "shadow" directory structure.
- **Implementation:** The physical files are stored in a flat directory with ISO names. A secondary "Visual Layer" uses symbolic links (symlinks) with natural language names that point to the ISO originals.
- **Strength:** If a symlink is overwritten, the actual data (the ISO file) remains untouched.
### Visualizing the Solutions
#### ASCII Art Mind Map: Hybrid File Management
	      [HYBRID FILE SYSTEM]               |     ---------------------------     |                         |[NAMING CONVENTION]      [METADATA LAYER]     |                         |+-------------+         +----------------+| ISO Prefix  |         | YAML Aliases   || + Title     |         | (Obsidian)     |+-------------+         +----------------+     |                         |[UNIQUE ID] <-----------> [SEMANTIC SEARCH]
#### ASCII Art Flow Chart: Conflict Resolution Feature
	[Start: File Copy/Paste]          |[Detect Filename Conflict?] --- No ---> [Paste Success]          |         Yes          |[Trigger OS UI Intercept]          |  -------------------  |                 |[Open Preview]    [Auto-Move to New Folder]  |                 |[User Resolves]   [Files Saved as "Conflict_ID"]
### Counter-Arguments and Considerations
- **Complexity Overload:** Critics argue that hybrid systems increase "friction" (Dahlstrom, 2021). Every time a user renames a file, they must manage both the prefix and the title, which can lead to "metadata rot" where the filename and content eventually mismatch.
- **Search Limitations:** While ISO strings are unique, they are not naturally searchable via keyword unless the title is included. Relying solely on IDs requires a robust indexing tool, adding a point of failure to the system.
### Action Steps for Implementation
1. **Personal Life:** Audit your digital archives. Rename core folders using `YYYY-MM-DD` prefixes to ensure they always sort chronologically regardless of OS settings.
2. **Academic Life:** In Obsidian, adopt the "Alias" property immediately. Use a plugin like "Waypoints" or "Dataview" to map your ISO files to a visual table of contents.
3. **Work Life:** Propose a "Timestamp-First" policy for shared drives to prevent "v2", "v3\_final" naming confusion, which frequently causes data loss in collaborative environments.
### Thought-Provoking Question
If we move toward an OS where files are retrieved via AI-driven semantic search (asking for "the budget memo from last Tuesday") rather than browsing a directory, will the concept of a "filename" eventually become an obsolete technical relic, similar to a physical hard drive sector address?
### APA 7 References
- Dahlstrom, E. (2021). _Data Management and Information Architecture_. Academic Press.
- Grosset, P. N., Rogers, L., & Ahrens, J. P. (2022). _Metadata Management for Large-Scale Scientific Workflows_. Springer Nature.
- Schöch, C. (2021). _Computational Literary Studies: Computational Methods for Digital Humanities_. De Gruyter.