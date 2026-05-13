# Comprehensive Guide to Uninstalling Witch on macOS
### Jianfa Tsai's Input
> how to thoroughly uninstall witch pref macOS app
### Authors
Authored by Jianfa Tsai in collaboration with Gemini AI
### Summary: Complete Removal of Many Tricks Witch
To thoroughly remove Witch from macOS, you must first disable its background process in System Settings, delete the Preference Pane itself, and then manually purge specific library folders to eliminate residual configuration and support files.
### 1. The Disablement and Primary Removal
Witch operates primarily as a background task. If you delete the interface without stopping the task, the process may continue to capture keystrokes until the next reboot (Many Tricks Support, 2026).
- **Step A: Disable the Background Task**Step A: Disable the Background Task
	1. Open System Settings (or System Preferences).**System Settings**
	2. Locate the Witch pane at the bottom of the sidebar.**Witch**
	3. Uncheck the box next to Enable Witch.**Enable Witch** This kills the background listener.
- **Step B: Remove the Preference Pane**
	1. Return to the main list of System Settings.
	2. **Control-click**Control-click (or right-click) the Witch icon.Control-click (or right-click) the Witch icon.
	3. Select **Remove "Witch" Settings Pane**.
### 2. Manual Purge of Leftover Files
Mac applications often store data in hidden Library folders. To ensure a "clean slate" uninstall, you must delete these directories (iBoostUp, 2026).
**Table: File Paths for Manual Deletion**

| Category                | File Path                                                  | Action        |
| ----------------------- | ---------------------------------------------------------- | ------------- |
| **Application Support** | `~/Library/Application Support/Witch`                      | Delete Folder |
| **Preferences**         | `~/Library/Preferences/com.manytricks.Witch.plist`         | Delete File   |
| **Caches**              | `~/Library/Caches/com.manytricks.witchwrapper`             | Delete Folder |
| **Caches (System)**     | `~/Library/Caches/[Unique ID].com.manytricks.witchwrapper` | Delete Folder |

### 3. Removal Workflow Flow Chart
	[ Start: Uninstall Witch ]
	          |
	          v
	[ Open System Settings ]
	          |
	          v
	[ Uncheck "Enable Witch" ] ----> (Stops Background Process)
	          |
	          v
	[ Right-click Witch Icon ] ----> (Select "Remove Settings Pane")
	          |
	          v
	[ Open Finder: Go to Folder ]
	          |
	          v
	[ Delete ~/Library/Application Support/Witch ]
	          |
	          v
	[ Delete ~/Library/Preferences/com.manytricks.Witch.plist ]
	          |
	          v
	[ Empty Trash & Restart ] ----> [ Finish: Thoroughly Removed ]
### ELI5 Summary
Think of Witch like a TV: first, you have to turn it off (Disable), then you take the TV out of the room (Remove Pane), and finally, you have to vacuum up the dust it left behind in the corners (Delete Library files).
### Counter-Arguments & Considerations
- **Convenience vs. Thoroughness:** Most users only need to remove the Preference Pane; manual file deletion is only strictly necessary if you are troubleshooting a corrupt installation or want to reclaim every kilobyte of space.
- **Third-Party Uninstallers:** While tools like AppCleaner or iBoostUp can automate this, they sometimes miss the background process if it isn't disabled first, potentially leaving "zombie" processes running.
### Action Steps for Improvement
1. **Personal:** Use a password manager to store any license keys for Many Tricks apps before uninstalling, in case you wish to reinstall later.
2. **Academic:** When researching software removal, always prioritize the developer's official "Knowledge Base" (KB) as they provide the most accurate file paths for their specific builds.
3. **Work:**Work: Regularly audit your "Login Items" in System Settings \> General to ensure uninstalled apps haven't left background helpers that slow down your startup.
### Thought-Provoking Question
If macOS is designed to be user-friendly, should third-party apps be required to include a "One-Click Uninstall" button within their own interface, or is the current manual "Library" system a necessary security barrier?
### References
- Many Tricks Support. (2026, January 3). _How do I uninstall Witch?_ Many Tricks. [https://manytricks.com/osticket/kb/faq.php?id=28][1]
- iBoostUp. (2026). _How to uninstall Witch by Manytricks from your Mac._ iBoostUp. [https://www.iboostup.com/how-to-uninstall/com.manytricks.witchwrapper][2]
- MacRumors. (2018, March 29). _How to Hide and Remove System Preference Panes in macOS._ [https://www.macrumors.com/how-to/hide-remove-system-preference-panes-macos/][3]

[1]:	https://manytricks.com/osticket/kb/faq.php?id=28
[2]:	https://www.iboostup.com/how-to-uninstall/com.manytricks.witchwrapper
[3]:	https://www.macrumors.com/how-to/hide-remove-system-preference-panes-macos/