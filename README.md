# CheatArchiver

> A community-maintained archive of emulator cheats, designed to preserve codes from sites that are disappearing from the internet.
>
> 
> This is all Skillers work

---

## Layout

Everything lives in plain text files under `Database/`, one folder per cheat-device database and one file per game:

```
Database/
├── DBCFG.txt                         ← which patcher each folder uses
├── MEMORY-PS2-GSHI-DB/               ← GameShark Hacking Index (PS2)
│   └── Socom 2 - U.S. Navy Seals (Ntsc-U) - SCUS_972.75.CMP.txt
├── MEMORY-PS2-CODEBREAKER/
├── MEMORY-PS2-CMP/
├── MEMORY-PS2-XPLODER-DB-[EU]/
├── MEMORY-PS1/  MEMORY-GBA/  MEMORY-NDS/  MEMORY-GEN/  MEMORY-WII/
├── PS3-WIP/  PS4-WIP/
└── SAVES-*/                          ← save-game patches
```

File names follow `<Game Title> (<Region>) - <SERIAL>.CMP.txt`. The serial uses the disc's boot-file form (`SCUS_972.75`); use `No` when the serial is unknown.

---

## File format

```
^3 = NAME: Socom II - U.S. Navy Seals (Ntsc-U)
^2 = GameID: SCUS-97275
!Master Codes:
+(M) Must Be On
%Credits: Codejunkies
$F01BD810 001BD813
!!
!ASM Codes:
+Sticky Grenades {<I>Grenades stick to walls, floors and ceilings.</I>}
%Credits: RENEGADE
$203EB2FC 00000000
$203ECA44 00000000
!!
```

| Line | Meaning |
|---|---|
| `^3 = NAME: …` | Game title and region |
| `^2 = GameID: …` | Disc serial |
| `!Folder name:` … `!!` | A folder (section) of cheats |
| `+Cheat name {description}` | Starts a cheat; the optional `{…}` is its description |
| `%Credits: …` | Author |
| `$AAAAAAAA VVVVVVVV` | A code line (as the device expects it — raw or encrypted) |

---

## Adding cheats

1. Find the game's file in the right `Database/` folder, or create one named as above with the `^3` / `^2` header.
2. Add cheats with `+Name`, `%Credits:` and `$` code lines, inside a `!Folder:` … `!!` block.
3. Open a pull request.

---

## Using the archive in CodeDesigner

CodeDesigner imports these text files into its cheat archive (**Cheats editor → Refresh / Import**, or **Import archive** in the sidebar's Cheats tab). Each PS2 folder becomes one cheat list per game (GSHI, CodeBreaker, CMP, Xploder (EU)), and the Cheats tab, Cheat List and Cheat Porter let you pick which list to use.

---

## Contributing

Corrections and new codes are welcome — keep each code exactly as it was published, and credit the original author.
