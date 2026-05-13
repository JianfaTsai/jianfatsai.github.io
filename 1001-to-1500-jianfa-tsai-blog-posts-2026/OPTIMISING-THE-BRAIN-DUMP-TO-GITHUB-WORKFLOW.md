# OPTIMISING THE BRAIN-DUMP-TO-GITHUB WORKFLOW

### **Date**

Wednesday, May 13, 2026, 6:05 PM AEST

### **Authors**

Authored by Jianfa Tsai in collaboration with Gemini AI

### **Jianfa Tsai's Input**

> My current workflow for taking down my thoughts as notes and sharing them via GitHub to the public is: 1. Brain dump raw thoughts into iPhone via various iCloud sync note-taking apps, 2. Review the notes on macOS in Finder app, folder view, preview contents by pressing the spacebar key on each note, and edit the note via TextEdit app only when the note has typos and needs to be reworded for better comprehension. Grammar and fancy formatting are omitted to save time. Only commas and punctuation marks are used. The rule is to keep it short and simple without losing the essence or the meaning of the idea. The markdown notes are later uploaded to GitHub via GitHub Desktop sync. What are the pros and cons of this workflow, and how can it be improved?

### **Executive Summary (ELI5)**

Your system is like using a fast-moving conveyor belt: you catch ideas quickly on your phone, check them briefly on your computer, and put them in a public library (GitHub) for everyone to see. It is great because it is simple and uses tools you already have, but it can be a bit clunky since you have to switch between different apps to fix and save your work.

### **Workflow Analysis: Pros and Cons**

Your workflow leans heavily into the **"Plain Text" philosophy**, which is highly regarded in library and information science for its longevity and interoperability (Bhalerao, 2022).

|Feature|Pros (The "Wins")|Cons (The "Friction")|
|---|---|---|
|**Capture**|**High Velocity:** Using mobile apps for "brain dumps" minimizes cognitive load and ensures ideas aren't lost.|**Fragmentation:** Using "various apps" can lead to inconsistent file naming or "digital hoarding" where notes are hard to find later.|
|**Review**|**Quick Look:** macOS "Quick Look" (Spacebar) is the fastest way to browse local files without overhead.|**Format Risk:** TextEdit defaults to `.rtf` (Rich Text). If not manually set to "Plain Text," it can corrupt Markdown syntax.|
|**Editing**|**Minimalist Focus:** Omitting fancy formatting prevents "procrastination via styling," keeping the focus on the idea's essence.|**No Syntax Highlighting:** TextEdit doesn't show Markdown links or bolding, making it harder to spot structural errors in more complex notes.|
|**Publishing**|**Version Control:** GitHub provides a "time machine" for your thoughts and a free public hosting platform.|**Manual Sync:** GitHub Desktop requires a conscious "Commit and Push" step, which can lead to a backlog of unshared notes.|

### **Detailed Improvements & Edge Cases**

#### **1. Structural Consistency**

While you use only commas and punctuation, adding a **YAML Frontmatter** (a simple block at the top of a note) can improve how GitHub displays your notes.

- **Example:**
    
    ```markdown
    ---
    date: 2026-05-13
    tags: [productivity, workflow]
    ---
    Note content starts here...
    ```
    

#### **2. Tool Consolidation**

Instead of TextEdit, consider a **dedicated Markdown editor** that still feels lightweight but handles the "sync" more elegantly.

- **Obsidian (Local-first):** It works directly on your local folders (Vaults). You can point it at your GitHub repository folder. It allows for "Backlinking," which helps you see how a note from today relates to one from 2024 (Tsukie, 2026).
    
- **iA Writer / Byword:** These apps are designed for the "Plain Text" purist. They offer a much cleaner writing environment than TextEdit while maintaining the "short and simple" rule.
    

#### **3. Automating the "Push"**

The most common point of failure in this workflow is forgetting to sync. You can use a simple **Cron Job** or a **Git-Auto-Sync** script that automatically commits and pushes any changes in that folder to GitHub every hour, removing the need to open GitHub Desktop manually.

### **Visualizing the Workflow**

#### **ASCII Art Flow Chart**

```text
[ iPhone ] ----(iCloud)----> [ macOS Finder ]
    |                              |
(Brain Dump)                 (Quick Look/Space)
    |                              |
    |                        [ TextEdit/Obsidian ]
    |                              |
    |                       (Edit for Clarity)
    |                              |
    +------------------------> [ GitHub Desktop ] ----> [ Public GitHub ]
                                     |
                                (Manual Sync)
```

#### **ASCII Art Decision Tree**

```text
Should I edit this note?
|
|-- Does it have typos? ----> YES ----> Edit in TextEdit
|-- Is it unclear? ---------> YES ----> Reword for essence
|-- Need fancy formatting? -> YES ----> IGNORE (Keep it simple)
|-- Is it ready? -----------> YES ----> Sync to GitHub
```

### **Counter-Argument**

One could argue that by focusing strictly on "short and simple," you may be stripping away the **necessary context** required for future-Jianfa (or the public) to understand the note years later. Studies suggest that while concise notes improve retrieval efficiency, "extreme" brevity can lead to "information decay" where the original nuance is lost because the brain no longer has the environmental cues present during the original brain dump (SuperAGI, 2025).

### **Action Steps**

1. **Switch TextEdit to Plain Text Mode:** In TextEdit Preferences, ensure "Plain Text" is selected for New Documents to avoid accidentally saving as `.rtf`.
    
2. **Standardise Folder Structure:** Use a `YYYY-MM-DD-Title.md` naming convention to keep your GitHub repo chronologically organized.
    
3. **Audit GitHub Settings:** Ensure your repository has a `README.md` that explains your "short and simple" philosophy to the public so they understand the lack of formatting.
    

### **Thought-Provoking Question**

If your notes are meant for the public, does the "short and simple" rule serve the reader's understanding, or does it primarily serve the speed of your personal capture?

### **References**

- Bhalerao, V. (2022, January 28). _Why I am writing my book using Markdown + Github + Agile & how you can too_. Medium. [https://medium.com/@vinbhalerao/why-i-am-writing-my-book-using-markdown-github-agile-how-you-can-too-373bfac0fc7d](https://medium.com/@vinbhalerao/why-i-am-writing-my-book-using-markdown-github-agile-how-you-can-too-373bfac0fc7d)
    
- SuperAGI. (2025, July 4). _AI note-taking vs traditional methods: Which reigns supreme in the digital age?_ [https://web.superagi.com/ai-note-taking-vs-traditional-methods-which-reigns-supreme-in-the-digital-age/](https://web.superagi.com/ai-note-taking-vs-traditional-methods-which-reigns-supreme-in-the-digital-age/)
    
- The CTO Club. (2025, December 22). _GitHub Desktop review: Pros, cons, features and pricing_. [https://thectoclub.com/tools/github-desktop-review/](https://thectoclub.com/tools/github-desktop-review/)
    
- Tsukie. (2026, March 21). _I ditched Notion for Obsidian and never looked back_. [https://tsukie.com/en/technologies/i-ditched-notion-for-obsidian-and-never-looked-back/](https://tsukie.com/en/technologies/i-ditched-notion-for-obsidian-and-never-looked-back/)