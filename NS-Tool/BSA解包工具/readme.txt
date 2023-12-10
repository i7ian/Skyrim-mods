B.A.E. - Bethesda Archive Extractor v0.06

B.A.E. can extract BA2 and BSA files.

Version History
---------------
0.01 - Initial Commit
0.02 - Significantly faster open times on all BA2s, especially Fallout4 - MeshesExtra.ba2
	which took several minutes (now takes ~1s).
0.03 - Width/Height were actually listed as Height/Width in the BA2 so non-square textures were
    incorrectly extracted.
     - Gave window a minimum width/height as Windows 10 users complained of the window being too small.
     - Can open multiple archives via the file dialog, or by dragging to the executable.
0.04 - Cube maps were being extracted incorrectly.
0.05 - Skyrim SE BSA support
0.06 - Added drag and drop to main window
     - Added application icon
	 - Added About window
	 
Credits
-------
Special thanks to ianpatt and behippo for helping with my understanding of the new BA2 formats.