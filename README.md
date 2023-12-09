# robocopy
server migration using robocopy Lab
Robocopy - to backup files sytem - ENSURE THAT DESTINATION IS EMPTY!!!! (Unless performin a differential backup.)

Robocopy "Source" "Destination" /MIR /XJD /R:5 /W:15 /MT:32 /V /NP /LOG:Backup.log;exit!

#
Below is a PowerShell script that utilizes `robocopy` to copy files from a source folder to a destination and then removes the content from the original folder:

```powershell
# Define the source and destination folders
$sourceFolder = "C:\Path\To\Source\Folder"
$destinationFolder = "D:\Path\To\Destination\Folder"

# Run robocopy to copy files from source to destination
robocopy $sourceFolder $destinationFolder /E

# Remove content from the original folder
Remove-Item $sourceFolder\* -Recurse -Force
```

Please ensure to replace `C:\Path\To\Source\Folder` and `D:\Path\To\Destination\Folder` with the actual paths of your source and destination folders.

**Note:** Be extremely cautious when using `Remove-Item` with `-Force` and `-Recurse` flags, as it will permanently delete all files and subfolders in the specified source folder. Always double-check paths and test the script with non-critical data to ensure it behaves as expected before using it with important files or folders.


\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\
This is a second version in place of the one above.
Robocopy mirror all files:
Robocopy "Source" "Destination" /MIR /XJD /R:5 /W:15 /MT:32 /V /NP /LOG:Backup.log;exit
