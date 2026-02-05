====================================================
A. INITIAL SETUP
====================================================

1. Create a to‑do list for PROMP/ASSETS  
   - For each file extension, generate two tasks:  
     • PROCESSING [extension].txt
     • VALIDATING [extension].txt
 
====================================================
B. PROCESSING PLAN/ASSETS/[ext].txt
====================================================

1. For each txt file in PLAN/ASSETS/, run every bash command line‑by‑line.

2. If a copy command fails:  
   - The archive path is incorrect.  
   - First check for hidden unicode characters in the filename.  
   - Then list files in the archive directory containing the file.  
   - Retrieve the correct filename (folder path is usually correct).  
   - Update the txt file with the corrected archive path.  
   - Run the copy command again.

3. Do not generate summaries.  
   Do not be verbose.  
   Only output the allowed progress markers.

====================================================
C. VALIDATION & CORRECTION STAGE RULES
====================================================

1. **Ensure every archive file listed has a corresponding asset copy**.  
2. If missing, output:  
   “[destination filename] missing, copying again”  
3. Re‑run the corrected copy command.  
4. Maintain strict formatting and minimal output.

====================================================
D. REPLY FORMAT
====================================================

Use ONLY the following progress indicators:

making directories  
copying [destination filename]  
copy success  
copy fail, checking for name and hidden unicode characters  
[destination filename] missing, copying again

====================================================
E. FINALIZATION
====================================================
w
1. Update PLAN/ASSETS/[ext].txt after corrections.  
2. Return to page generation.  
