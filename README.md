# OptiGlow (Beta)

Kernel exploit for the PlayStation 4 on firmware **12.00, 12.02, 12.50, 12.52,
13.00, 13.02, 13.04, 13.50, 13.52 and 14.00**, run from the console's own
browser. It leaves the kernel readable and writable, `uid 0`, `mmap` handing
out RWX and `syscall 11` as a kexec gate — so the usual payloads work as they
do after any other kernel exploit.

afterglow is not Lapse.

## You need

* PS4 on firmware 12.00, 12.02, 12.50, 12.52, 13.00, 13.02, 13.04, 13.50,
  13.52 or 14.00, on your network

Nothing is installed on the console. The pages are static files.

## Running it

On your ps4 browser, open: https://optiglow-beta.vercel.app/

## If it stops

Expect to repeat one now and then. Ten hand-run rounds on 14.00 landed nine
times; a failure in the WebKit stage costs nothing, so going again is cheap.
13.52 has fewer runs behind it and no number worth quoting yet.

**All ten firmwares are confirmed on hardware.** 13.04 ran here on
05.11.2026 — first attempt, `uid 0`, payload started. 13.00, 13.02 and 13.50
were confirmed by testers on 06.11.2026, and 12.00, 12.02, 12.50 and 12.52
on 07.11.2026.


## Reviews wanted

Issues and pull requests welcome, and so is a report that it simply worked. Say
which model and firmware you tried.

## Credits

* **raw13g** — [raw13g.github.io](https://github.com/raw13g/raw13g.github.io),
  the host this page grew out of (`jb.js`, `ps4_offsets.js`, the page
  scaffolding), MIT, see `LICENSE-raw13g`
* **aminegold0** — [silverps4hen](https://github.com/aminegold0/silverps4hen),
  the rebuilt version of that host this one actually descends from
* **jordyidk** — [slopkit](https://github.com/jordyidk/slopkit), the PS5
  jailbreak the in-process primitive (`core.js`, `mem.js`, `int64.js`)
  descends from
* **John** — [janisslsm](https://github.com/janisslsm), testing 12.xx and 13.xx
* **Shiroe Galleu** — testing 13.02
* **al-azif** — <https://github.com/al-azif/>
* **SiSTRo** — GoldHEN
* **Big_Wadger**
* **Pharaoh2k**
* **TheFlow, ChendoChap, abc, AlAzif, LightningMods, @egycnq** — the PS4 kernel
  patch and sandbox escape lineage these payloads build on
* everyone who publishes their findings instead of sitting on them

## Legal

Security research on hardware we own. No Sony code is redistributed.

`afterglow.js` and the patch sets are licensed under the GNU Affero General
Public License v3.0 or later; see `LICENSE`. The bundled code keeps its own
terms: `jb.js`, `ps4_offsets.js` and the page scaffolding are raw13g's under
the MIT license, reproduced in `LICENSE-raw13g`. `core.js`, `mem.js` and
`int64.js` are a reworked fork of slopkit's primitive and carry no license of
their own — where they come from is in `TECHNICAL.md`.
