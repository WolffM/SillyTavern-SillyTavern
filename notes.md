## Steps to reproduce
1. Start SillyTavern from this branch with `npm start -- --disableCsrf --listen`.
2. Open `http://127.0.0.1:8000` in a desktop browser window with limited vertical height (or with a browser status bar visible).
3. Open API Connections, choose NanoGPT as the source, and open the **NanoGPT Model** selector.
4. Ensure the selector has many model entries (the repro script used a long generated model list), then open the dropdown near the lower part of the panel.

## Observed
The model dropdown can extend beyond the visible viewport and the lower part becomes covered by the browser status area, matching the user report/screenshot (`https://github.com/user-attachments/assets/38c22aab-95e4-4586-96e5-091af3ebef92`). In local verification, the post-fix capture is available at `/tmp/nanogpt-dropdown-after-fix.png`, showing the dropdown constrained to remain visible.

## Expected
When the NanoGPT model selector opens, the results area should stay within the visible page area so the bottom of the list is not hidden by browser chrome/status UI. Users should be able to scroll and select models without the dropdown overflowing below the viewable boundary.
