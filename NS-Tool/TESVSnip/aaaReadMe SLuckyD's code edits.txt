=== AssemblyInfo.cs
- changed the AssemblyDescriptionAttribute, AssemblyTitleAttribute, and Assembly FileVersionAttribute (to reflect version difference)


=== HeaderEditor.resx
- changed most of the "cb*.Text" entries
- this is the location of record headers' flags1 data, which is displayed when d-clicking a record's name ("headerEditor" window)


=== TESsnipParser.cs

- added a line to force-close the app (when the sizeTag doesn't match the decompressed actual size), commenting out the original error-handling (which would allow the app to continue running)

; start (under "public static BinaryReader Decompress")
if (decompressedSize != outsize) // Check the size of the uncompressed data against what we expected
	{
		System.Windows.Forms.Application.Exit();
		//throw new Exception(String.Format("Unexpected Decompressed data size! CompressedSize={2:D} DecompressedSize={0:D} Expected Size={1:D}", decompressedSize, outsize, size));
	}
; end

- changed several of the descriptions for record headers' flags1 (this is the location of what's displayed in the main "Report" window)
- commented out the original labels, added numbering comments

; start (under "internal static class FlagDefs")
	public static readonly string[] RecFlags1 = {
			"ESM File",
			null,
			null,
			//null,
			"Has Current",
			//5
			null,
			"Marked Deleted",
			//null,
			"HasTreeLOD-AddonLODObject",
			"Localized-IsPerch",
			//null,
			"Must Update Anims",
			//10
			//"Casts shadows",
			"HidFromLocMap-CastShad-StartDead",
			"QuestItem-Persistent",
			"Initially Disabled",
			"Ignored",
			null,
			//15
			null,
			"Visible When Distant",
			"Is full LOD-Random Anim Start",
			"Danger-OffLimits-IsRadSt-PortalStrict",
			"Compressed",
			//20
			"Can't Wait",
			null,
			null,
			null,
			//null,
			"Is Marker",
			//25
			//null,
			"IgnoreObjInteract",
			//null,
			"Obstacle-NoAIAcquire",
			//null,
			"NavMeshFilter",
			//null,
			"NavMeshBoundBox-Respawns",
			//null,
			"Reflect-MustExitToTalk",
			//30
			//null,
			"ChildCanUse-NoHavokSettle",
			//null,
			"NavMeshGround-NoRespawn",
			null,
		};
; end


=== Record.cs
- added one line, which forces app to exit when sizeTag is smaller than actual size
- commented out error handler, which would allow the app to continue running

; start, under "public sealed class Record" then "internal Record(string name, uint Size, BinaryReader br, bool Oblivion)"
if (AmountRead != Size)
	{
		System.Windows.Forms.Application.Exit();
	   // throw new TESParserException(
	   //  String.Format("Subrecord block did not match the size specified in the record header. Name={3} Header size={0:D} Subrecord Size={1:D} CompressedRecord={2:G}", Size, AmountRead, compressedRecord, name));
	}
; end


=== tesvsnip Project
- compiled without ClickOnce security enabled



