# valorant-clip-compressor-script
Quick script to automate some video file modifications, so I can share my clips with friends on more platforms.

## Preface:
#### I had a bunch of Valorant gameplay clips, sharing these and moving them were a hassle due to their size (500mb+). I could go into Davinci Resolve and manually compress each, but that would take a while, I have a lot of clips. So I concluded that this would be a nice opportunity to write up a Python script to automate this.
#### I used ffmpeg to work with the mp4 files.

---

Goal of this script is to automate the organization and renaming of video files located in the Valorant folder recorded by Nvidia's Instant Replay.
The parent folder contains subfolders named by dates (e.g., 2024.10.22), and each subfolder contains MP4 video files of varying sizes.
The script will process MP4 videos stored in subfolders (named by date), ensure proper naming conventions, 
move files to the parent directory, and adjust the resolution and size of the videos as per defined criteria.

List of tasks to achieve with the script:
1. **Rename Video Files:**
   - Remove unnecessary punctuations, leaving only the name and date in the format: "Name Date.mp4" (e.g., "Valorant 2024.12.12 - 00.00.55.03.DVR_Try-Defusing.mp4" becomes "Try Defusing 2024.12.12.mp4").
   - If file name doesn't match expected scheme, leave it as is.
 
2. **Move Files to Parent Folder:**
   - Relocate all renamed video files from their dated subfolders into the parent folder (Valorant).
 
3. **Non-Destructive Operations:**
   - Operate on copies of the original files, ensuring that the original data remains unchanged (non-destructive).
 
4. **Ensure Correct Video Resolution:**
   - Ensure all videos have a 16:9 aspect ratio.
   - Resize videos to resolutions between 1280x720p and a minimum of 960x540p.
 
5. **Handle Incorrect Resolution or Size:**
   - Leave videos with resolutions outside the allowed range untouched if their size is under 25 MB.
   - Compress videos larger than 25 MB by adjusting the bitrate to reduce their file size to under 25 MB, while maintaining the resolution.
