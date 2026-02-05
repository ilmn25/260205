====================================================
A. SPA GENERATION INSTRUCTIONS
====================================================

1. MAIN.txt  
   - Contains all SPA routes  
   - Contains website accent colors  
   - Contains website icon path for index.html  
   - All /assets paths become:  
       {ASSETS_URL} + "/assets/filename.ext"  
   - Any icon or image NOT in /assets uses the lucide icon library  
   - Add a universal constant for:  
       • ASSETS_URL prefix  
       • Accent colors array

2. ROUTE CREATION  
   - Create each route EXACTLY in the order listed in MAIN.txt  
   - DO NOT place tsx files inside /PAGES  
   - Use folder: pages/  
   - Route → file mapping:  
       "/" → PLAN/PAGES/root.txt  
       "/staff/jim-smith" → PLAN/PAGES/staff/jim-smith.txt  
   - If a route is already completed, skip it  
   - After finishing a route file, WAIT for user to say **"continue"**

3. PAGE CONTENT RULES  
   - Raw text inside route txt files may be in any language  
   - Translate all text into:  
       • English  
       • Traditional Chinese
   - Proper nouns must be evaluated carefully  
       • Example: “ChatGPT” should NOT be translated  
   - Preserve tone and meaning (professional, fun, etc.)
   - Take note of whether a asset is a banner, background, and its resolution to decide how to add it

4. SUPPORTED EMBED TYPES
   The SPA must support embedding the following external content:
   - YouTube videos
   - Google Maps
   - Any iframe‑based embed (Vimeo, Spotify, custom widgets)

====================================================
B. OUTPUT TARGET
====================================================

Generate a tsx at pages/[route].tsx
Generate only one page/route before waiting for further instruction
