# KEYBOARD MAESTRO MACRO GROUP SETTINGS INTERFACE
### DATE
May 15, 2026 | 8:42 AM AEST
### AUTHORS
Authored by Jianfa Tsai in collaboration with Gemini AI Pro
### JIANFA TSAI'S INPUT
Show me a youtube video or image on Keyboard Maestro - In the settings on the right, change "Available in all applications" to "Available in these applications:"
### VISUAL REFERENCE: MACRO GROUP SETTINGS
Below is a visual representation of where to find the application scoping settings within Keyboard Maestro.
### STEP-BY-STEP INTERFACE GUIDE
To configure this specific setting in your Keyboard Maestro editor, follow these precise movements:

| Interface Element         | Location        | Action                                                             |
| ------------------------- | --------------- | ------------------------------------------------------------------ |
| **Groups Column**         | Far Left Pane   | Select the Group you created (e.g., "Gemini Automations").         |
| **Settings Pane**         | Right Side Pane | Look for the header "Macro Group Settings."                        |
| **Availability Dropdown** | Top of Settings | Click the blue text that says **"Available in all applications."** |
| **Selection Menu**        | Pop-up Menu     | Select **"Available in these applications"** from the list.        |
| **Add Application**       | Below Dropdown  | Click the **plus (+)** icon to add Gemini to the list.             |

### ASCII ART DECISION TREE: SCOPING YOUR MACRO
This tree explains why choosing "Available in these applications" is critical for your Gemini-to-Ulysses workflow.
	       [ Start: Copy Action ]
	                |
	       Is the Macro Global?
	       /                \
	     [YES]              [NO]
	      |                  |
	Triggers every time   [Check: Front App]
	you copy anything.    /          \
	(Clutters Ulysses)  [Gemini]    [Safari/Other]
	                      |              |
	                RUN MACRO      DO NOTHING
### ELI5 EXPLANATION
Think of this setting like a pair of glasses that only lets Keyboard Maestro see what you are doing when you are inside the Gemini "room," so it doesn't try to help you when you are busy in other apps.
### COUNTER-ARGUMENT
While scoping to "Available in these applications" prevents most accidents, it will still trigger if you copy a small snippet of text within Gemini that you _didn't_ intend to send to Ulysses. If you find this happens often, you might consider changing the trigger from "Clipboard Changes" to a "Hot Key" (like `Control+G`) that you only press when you are ready to export.
### ACTION STEPS
1. **Open the Editor:** Ensure you have the specific Macro Group selected, not just an individual macro.
2. **Select Gemini:** When you click the `+` to add an application, if Gemini isn't running, select "Other..." and find it in your `/Applications` folder.
3. **Check "All Windows":** Ensure the setting "Always Activated" is also selected in that same right-hand pane so the "lookout" is always on duty.
### APA 7 REFERENCES
- Stairways Software. (2026). _Keyboard Maestro Documentation: Macro Groups_. [https://wiki.keyboardmaestro.com/Macro\_Groups][1]
- Keyboard Maestro. (2026). _Conditions for Macro Execution_. [Software Interface].
Would you like me to find a specific video tutorial that walks through the "URL Scheme" method for Ulysses as well?

[1]:	https://wiki.keyboardmaestro.com/Macro_Groups