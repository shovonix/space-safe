# Space Safe

Drop in a thumbnail and see YouTube-style overlays on top of it before you upload. Live at https://safe.shovonix.dev

Built by [Shovon Arifin](https://shovonix.dev). Part of the Space tools, with [Space Prompter](https://studio.shovonix.dev).

- **Checks**: size, 16:9 shape, file size (2 MB phone / 50 MB desktop upload limits), and whether busy detail sits under the timestamp badge.
- **Safe zones**: timestamp badge areas for the home feed and the 168 px sidebar, plus the square and 1.91:1 crops used by link previews.
- **Previews**: home feed in dark and light, phone (dark and light), sidebar "up next", and shared-link crops. Optional watched bar and hover icons.
- **Compare**: load up to 3 versions and see them side by side in the feed.

Images are read in the browser and never uploaded. The previews follow YouTube's layout as of late 2026 and are a guide, not a pixel-perfect copy. Not affiliated with YouTube.

Everything lives in `index.html`; there is no build step.

## Licence

Copyright © 2026 Shovon Arifin. All rights reserved.

The code is public so you can see how Space Safe works. It is not open source: you may not copy, modify, redistribute or host it, in whole or in part, without written permission. Use the live app at the link above.
