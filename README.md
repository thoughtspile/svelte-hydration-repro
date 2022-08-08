## Reproduction: svelte-kit clears `<input bind:value>` on hydration

This repository demonstrates input reset on hydration when using svelte-kit

1. `npm run build`
2. `npm run preview -- --open`
3. Project (single input) opens in the browser 
4. Open devtools -> network
5. Check "disable cache" and set throttling to "Slow 3G" fro better reproducibility
6. Reload page
7. Once the HTML has loaded, but before JS in run, type into the input
8. JS arrives

Expected outcome: user input from step 6 is preserved 
Actual outcome: input is empty after JS hydrates, causing poor UX on slow network.
