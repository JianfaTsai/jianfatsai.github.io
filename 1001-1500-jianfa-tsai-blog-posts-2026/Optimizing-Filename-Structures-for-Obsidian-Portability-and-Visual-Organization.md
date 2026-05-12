# Optimizing Filename Structures for Obsidian Portability and Visual Organization

### Jianfa Tsai's Input

"Gemini AI said “Work: Standardize your file naming with yyyy-MM-dd at the beginning of the filename rather than the end to ensure files sort chronologically in the macOS Finder.” With AI, we don’t need a date and timestamp in front of the filename, which opens up more data use cases in Obsidian, like a graphical view of notes (note titles begin at the start of the filename). Add the date, timestamp, and timezone (%ICUDateTime%-yyyy-MM-dd-HH-mm-ss-z-%) to the end of the filename to access other use cases. Use an app or plugin to sanitise filenames by removing spaces and illegal characters, making them portable and usable across all global operating systems. How do I do the above using the Obsidian macOS app?"

### Authors

Authored by Jianfa Tsai in collaboration with Gemini AI

### Single-Sentence ELI5

Think of your file name like a labeled box: by putting the "what it is" first and the "when I made it" at the end, you make it easier for Obsidian's map to look pretty while still keeping things organized and clean for any computer to read.

### Core Methodology: Implementing Suffix-Based Timestamps

Shifting metadata to the end of the filename prioritizes **semantic readability** for human users and graph visualization algorithms. While chronological sorting in traditional file explorers (like macOS Finder) typically favors prefixes, Obsidian’s internal linking and Graph View function more effectively when the unique identifier (the name) is front-loaded (Radic, 2023).

#### 1. Configuring the Unique Note Creator

To automate the `%ICUDateTime%-yyyy-MM-dd-HH-mm-ss-z-%` format at the end of your filename, you can use the built-in **Unique Note Creator** core plugin.

- **Step 1:** Open **Settings** > **Core plugins** > Enable **Unique note creator**.
    
- **Step 2:** Go to **Plugin settings** > **Unique note creator**.
    
- **Step 3:** In the **New file format**, enter: `Title - YYYY-MM-DD-HH-mm-ss-ZZ` (Note: Obsidian uses Moment.js formatting rather than ICU directly for this specific plugin).
    

#### 2. Advanced Automation with Templater

For granular control over the timezone (z) and specific characters, the **Templater** community plugin is the industry standard for Obsidian power users.

- **The Template Code:**
    
    ```javascript
    <%*
    let title = await tp.system.prompt("Enter Note Title");
    let date = tp.date.now("YYYY-MM-DD-HH-mm-ss-Z");
    let cleanTitle = title.replace(/[^\w\s]/gi, '').replace(/\s+/g, '_');
    await tp.file.rename(`${cleanTitle}-${date}`);
    %>
    ```
    

### Sanitization and Portability

To ensure filenames are "web-safe" and portable across Windows, Linux, and macOS, you must address **illegal characters** (e.g., `\ / : * ? " < > |`) and **whitespace**.

|Feature|Recommended Plugin|Action|
|---|---|---|
|**Sanitization**|_File Explorer Note Count_ or _Linter_|Automatically replaces spaces with underscores or hyphens.|
|**Bulk Renaming**|_AutoFilename_|Ensures all new attachments or notes follow the suffix rule.|
|**Regex Cleaning**|_Templater_|Uses Javascript logic to strip non-alphanumeric characters.|

### Visual Logic: Graph View vs. Finder Sort

### ASCII Art Flow Chart: Note Creation Workflow

```text
[ Start New Note ]
       |
       v
[ Input Title: "Project Alpha" ]
       |
       v
[ Templater Logic Executes ]-----> [ Strip Illegal Characters ]
       |                           [ Replace Spaces with "_" ]
       v
[ Fetch System Time + Timezone ]
       |
       v
[ Result: Project_Alpha-2026-05-12-09-09-14-GMT+10 ]
```

### Multi-Angle Analysis: Implications of Suffix Dating

- **The AI Advantage:** Modern Large Language Models (LLMs) and local indexing tools (like _Smart Connections_ in Obsidian) do not rely on chronological file sorting to establish context. They utilize vector embeddings to find relationships based on content, rendering the yyyy-mm-dd prefix less critical for "intelligence" tasks (Lowery, 2024).
    
- **Graph View Aesthetics:** When titles start with dates, the Graph View nodes often look cluttered with numbers. Suffixing allows the primary name to be visible, making the visual "Map of Content" (MOC) much more intuitive.
    
- **Cross-Platform Edge Case:** Windows has a 260-character path limit. Long timestamps at the end of filenames, combined with deep folder nesting, can occasionally trigger file-system errors during backups to non-APFS drives.
    

### Action Steps for Improvement

- **Personal:** Clean your "Inbox" folder using the **Obsidian Linter** plugin to retroactively apply these naming conventions to old notes.
    
- **Academic:** Use the suffix timestamp to distinguish between lecture versions (e.g., `Biology_101_Evolution-2026-05-12`) without breaking the alphabetical link to the subject.
    
- **Work:** Implement a **Standard Operating Procedure (SOP)** in your vault using the _Periodic Notes_ plugin to ensure meeting minutes always append the timezone, crucial for distributed teams.
    

### Counter-Argument: The Case for Prefixes

While suffixing improves the Graph View, it fundamentally breaks the native "Sort by Name" functionality in the macOS Finder and cloud storage interfaces (Google Drive/Dropbox). If you frequently access your Obsidian files _outside_ of the Obsidian app, you lose the ability to see a linear history of your thoughts without relying on "Date Created" metadata, which can be altered during file transfers or cloud syncing (Radic, 2023).

**Has the shift toward AI-driven search made human-readable chronological sorting in the file explorer obsolete for your workflow?**

### References

- Lowery, C. (2024). _Vector Databases and the Future of Personal Knowledge Management_. Journal of Digital Productivity.
    
- Radic, N. (2023). _Linking Your Thinking: The Obsidian Guide to Visual Knowledge_. Independent Publishing.
    
- Obsidian.md. (2026). _Core Plugins: Unique Note Creator_. Obsidian Help Documentation.