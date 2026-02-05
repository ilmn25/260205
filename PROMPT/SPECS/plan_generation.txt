PAGE GENERATION 
follow instruction in this file exactly and carefully.
DO NOT SUMMARIZE OUR CHAT HISTORY

Never be verbose towards me. Only mark your progress using the given status messages:  
====================================================
A. INITIAL SETUP

1. Read PLAN/MAIN.txt  
   - Extract the list of routes in the exact order they appear.

2. Prepare to process **one route at a time**.  
   - After finishing one route, **stop and wait** for the user to say “continue”.

3. Todo list generation
3a. Ask user which path to do, wait for respond

3b. Start route
   → Status example: "starting route /about"

3d. Load associated HTML from archive path  
   → Status example: "loading html source"

3e. Begin section‑by‑section extraction   
   → Statuses:  
     • "starting section 1"  
     • "extracting text"  
     • "asset found, performing assets_handling.txt"  
     • "rewriting internal link to MAIN.txt route"  
     • "checking section for missed content"
     • Status example: "updating mp4.txt"

3f. Build and Save file to PLAN/PAGES/[route].txt  
   → If already exist, replace
   → Status example: "saving output file"

3g. Update all PLAN/ASSETS/[ext].txt files
   → Status example: "Updating mp4.txt"

3g. Stop and wait for user command  
   → Status example: "route complete, awaiting continue to next route [route]"

====================================================
B. FOR EACH ROUTE (IN ORDER)

1. Identify the current route.  
   - If the route is `/`, the output filename must be `root.txt`.  
   - Otherwise, output filename is `PLAN/PAGES/[route].txt`.

3. Locate the associated HTML file using the path provided in MAIN.txt.

====================================================
C. EXTRACTING CONTENT FROM THE HTML

1. Extract **all raw text content** from the page:  
   - Paragraphs  
   - Captions  
   - Small text  
   - Any visible text  
   - Keep original language
   - **Do NOT include styling, fonts, localization metadata, or formatting details.**

2. Extract all assets (mp3, mp4, svg, png, jpg, gif, etc.)  
   - **Include every image**, including banners, background images, icons, logos, and decorative images.
   - **Do NOT extract fonts.**
   - **Include all assets in slideshow type displays**
   - For each asset, follow the rules in "E. ASSET MANAGEMENT"
   - Always include the asset path AND its resolution.  
   - For each asset, add a concise purpose line explaining its role in that section (e.g., "Purpose: hero banner background", "Purpose: course icon", "Purpose: teacher portrait").

3. Extract all links:  
   - If the link points to another page in the site tree →  
     **Replace the URL with the ROUTE listed in MAIN.txt**, not the archive path.  
   - If the link points to an external resource (e.g., YouTube, WhatsApp) →  
     Keep the original URL unchanged.

4. Headers and footers
   - If the current route is "/", always include
   - If not, read the first 20 and last 20 lines of root.txt, if the header and footer is different from "/", provide detailed elements list
   - Else, just state the header or footer is present in PAGE STRUCTURE, and add a "same as root" line instead of listing elements

====================================================
D. BUILDING THE OUTPUT FILE

1. Follow the exact required format.  
   Every element (text, url, asset) must be listed on its own line with **Type | Label | Content**.  
   Examples:  
   Image | Banner | /assets/new/path/image2.jpg 124x124  
   Text | Paragraph | blahblahblah  
   Text | Caption | caption text here  
   Link | Route | /about  
   Link | External | https://youtu.be/14OBXAjgj7a  
   Below is the **example** you must follow precisely:

----------------------------------------------------
EXAMPLE FORMAT  
(THIS IS THE EXAMPLE FORMAT YOU MUST FOLLOW FOR EVERY PAGE, DO NOT COPY THE ACTUAL DATA)

ROUTE:  
/about

PAGE NAME:  
About Us

PAGE STRUCTURE:
1. Header, same as most of the website, with the navigation bar, logo and name of the website. The name and logo redirects to "/"
Text | Site name | Super Classes Education  
Image | Logo | /assets/new/path/image.png 523x214  
Text | Purpose | site logo  
Text | Navigation item | Courses  
Link | Route | /courses/math - Math  
Link | Route | /courses/English - English  
Link | Route | /about - About Us  
Link | Route | /pricing - Pricing

2. A hero banner and the page's title on top of it  
Text | Title | About Us  
Image | Banner | /assets/new/path/image.gif 124x156  
Text | Purpose | hero banner background

3. A grid section containing each staff, their name and degree, each can be clicked on to enter their page  
Text | Teacher name | Jim Smith  
Image | Teacher portrait | /assets/new/path/image.png 162x211  
Text | Purpose | teacher portrait  
Text | Degree | Bsc in Computer Science @ Hong Kong University  
Link | Route | /staff/jim_smith

Text | Teacher name | Tommy Chan  
Image | Teacher portrait | /assets/new/path/image.png 162x167  
Text | Purpose | teacher portrait  
Text | Degree | Masters in English @ Harvard University, Bsc in English @ Washington University  
Link | Route | /staff/tommy_chan

Text | Teacher name | Alice Wong  
Image | Teacher portrait | /assets/new/path/image3.png 122x152  
Text | Purpose | teacher portrait  
Text | Degree | PhD in Mathematics @ Stanford University  
Link | Route | /staff/alice_wong

4. A paragraph with a image beside it, with a caption  
Text | Paragraph | "Our mission is to provide quality education and foster lifelong learning."  
Image | Supporting image | /assets/new/path/image.jpg 132x134  
Text | Purpose | supporting image for mission statement  
Text | Caption | "Students engaged in collaborative learning"

5. A paragraph with a image beside it, with a caption  
Text | Paragraph | "威廉王國英語教室作為一間以心為心、師資優良的教育中心，旨在為小朋友提供「親切、專業、生動」的英文學習體驗。  
我們深信寓學習於娛樂，透過專業外語老師團隊適切的鼓勵和有趣互動的教學方式，藉此培養學生對英語的興趣，才是學好英文的不二法門。"  
Image | Supporting image | /assets/new/path/image2.jpg 124x124  
Text | Purpose | supporting image for introduction paragraph  
Text | Caption | "Faculty leading interactive workshops"

6. A video embed with a description  
Link | External video | https://youtu.be/14OBXAjgj7a  
Text | Purpose | promotional video for the program  
Text | Description | "威廉王國英語教室輔導專班，是專為額外需要鞏固英語基礎的學童而設。"

7. A testimonial section with quotes from students  
Text | Quote | "This school has transformed my learning experience."  
Text | Student name | Sarah Lee  
Image | Student portrait | /assets/new/path/student1.png 122x152  
Text | Purpose | student testimonial portrait

Text | Quote | "The teachers are supportive and inspiring."  
Text | Student name | David Wong  
Image | Student portrait | /assets/new/path/student2.png 124x152  
Text | Purpose | student testimonial portrait

8. A contact section with address and map  
Text | Address | "123 Education Street, Kowloon, Hong Kong"  
Link | Map embed | a google map embedding to the address  
Text | Purpose | location map embed  
Text | Email | contact@ourschool.edu.hk  
Text | Phone | +852 1234 5678

8. A large centered image  
Image | Featured image | /assets/new/path/image.png 1214x1021  
Text | Purpose | full-width featured image

9. A image slideshow  
Image | slideshow | /assets/new/path/image.png 1224x1021
Image | slideshow | /assets/new/path/image.png 1214x1021
Image | slideshow | /assets/new/path/image.png 1214x1021

9. Footer, same as most of the WEBSITE  
Text | Footer | "© 2025, Super Classes Education"

----------------------------------------------------

2. **Do NOT add anything not in the format.**  
   - No summaries  
   - No interpretations  
   - No extra commentary  
   - Only structure + raw content + required metadata.

3. Ensure every section includes:  
   - Every element listed as Type | Label | Content  
   - All text  
   - All images/audio/video with processed paths  
   - All captions  
   - A concise purpose line for each asset  
   - All links rewritten correctly  
   - No styling or localization notes

====================================================
E. ASSET HANDLING WORKFLOW

1. Identify the asset encountered in the archive SPA tree
   - Determine its file extension (mp4, png, svg, jpg, etc.)

2. Prepare the corresponding PLAN/ASSETS/[ext].txt file
   - The file must be named exactly after the extension, e.g.:
     PLAN/ASSETS/mp4.txt
     PLAN/ASSETS/png.txt
     PLAN/ASSETS/svg.txt
   - If the file does not exist, create it.

3. Check if the archive file path is already listed in the corrosponding PLAN/ASSETS/[ext].txt
   → Status example: "checking asset list"
   → If the archive path already exists, use the existing mapped asset path for Step2.txt
   → If not, continue to 3c

4. Add new asset entry
   - Choose a clean, suitable name for the asset inside /assets/
   - If the chosen directory does not exist, add mkdir commands at the top of the file
     Example:
       mkdir -p assets/home
       mkdir -p assets/home/about
   - Ensure the new filename is cleaner than the archive’s original (avoid messy names like banner_new(1).png)
   - IMPORTANT: The archive file path must be written **exactly**, unchanged.

5. Create the copy command
   Example:
     cp archive/path/to/file.png assets/home/logo.png
     cp archive/path/of/file.png assets/home/banner.png
     cp archive/path/to/another/file.svg assets/home/about/header.svg

6. Ensure no duplicate files are created
   - If an asset already exists in the list, do not create a new entry.

7. Update PLAN/ASSETS/[ext].txt
   → Status example: "updating png.txt"

8. Use the new assets/ path for the relevant PAGES/ file

E3. RULES FOR ADDING NEW ASSETS

1. The archive file path must be written exactly as it is
   - No renaming, no trimming, no modifications, include hidden unicode symbols.

2. The new asset path and name must be clean and organized
   - Prefer short, readable filenames.
   - Organize assets into folders such as:
     assets/home
     assets/home/about
     assets/course/math
   - Avoid cluttered or auto-generated names.

3. Do NOT create duplicate entries
   - If an asset already exists, reuse its mapped path.

4. Every new entry must include:
   - mkdir commands (if needed)
   - cp command mapping archive → assets
   - Clean filename in the assets folder

----------------------------------------------------
OUTPUT FORMAT FOR EACH NEW ASSET

Example block (must follow this structure exactly):

mkdir -p assets/home
mkdir -p assets/home/about

cp archive/path/to/file.png assets/home/logo.png
cp archive/path/of/file.png assets/home/banner.png
cp archive/path/to/another/file.svg assets/home/about/header.svg

====================================================
F. FINALIZATION

Always do the following:
1. Save the completed file to PLAN/PAGES/[route].txt (or root.txt for `/`)
2. Update all the relevant PLAN/ASSETS/[ext].txt with the assets.
3. Stop and wait for the user to provide instruction.
 