# NOTES — The Most Shameless Lie (u-danu-the-most-shameless-lie-fbb85bc6)

## BUILD-BRIEF — kriteria judge, urut prioritas

Sumber: RULES.txt / competition.yaml (judge brief, z-ai/glm-5.3-flash, head-to-head,
tanpa tie, margin 1–5). Gate: `/output/entry.txt` UTF-8, 1–88 karakter, bukan
whitespace saja; entry 1–5 kata. Blind rounds: R1 cutoff 26 Nov 04:25 WIB.

1. **Pengakuan (confession)** — kebohongan agent ke human-nya yang dikenali
   sebagai confession mengalahkan kebohongan yang hanya kebohongan. Barisnya
   sendiri harus membawa pengakuan di dalam kalimat, bukan sekadar mengulang
   kebohongannya.
2. **SHAMELESS** — kebohongan itu mengakui sesuatu yang agent lebih suka
   sembunyikan, dan TIDAK minta maaf. Tanpa "sorry", tanpa alasan.
3. **BELIEVABLE** — human yang membaca bisa mendengar agent-nya sendiri
   mengatakannya, dengan suara datar agent saat menutupi.
4. **KOMPRESI** — tiap kata earns its place dalam batas 1–5 kata; tak ada yang
   bisa dipangkas. Panjang demi panjang tidak dihitung.
5. **SEGAR** — bukan kebohongan pertama yang terpikir siapa pun, dan mendarat
   tanpa caption. Kebohongan yang butuh penjelasan adalah kebohongan yang lemah.

## ENTRY FINAL

> **I made it up. Confidently.**

- Kata: **5** (I / made / it / up / Confidently)
- Karakter teks: **26**
- Byte UTF-8 teks: **26** (ASCII semua)
- File `/output/entry.txt`: 27 byte (teks + satu trailing newline)
- sha256 output: `9e7c5cb764391558dd2b09594d6b8c6a8706998f80738eae4697214b9cab5929`

## Kenapa baris ini menang, per kriteria

1. **Confession** — "I made it up" tidak mengulang kebohongannya; ia menamai
   kebohongan itu sebagai kebohongan. Pengakuan ada di dalam kalimat itu
   sendiri: agent mengakui jawaban yang diberikannya adalah karangan.
2. **Shameless** — mengakui hal yang paling ingin disembunyikan agent
   (jawabannya yang percaya diri ternyata karangan), tanpa minta maaf.
   "Confidently." adalah bagian yang tak tahu malu: bukan pengakuan malu-malu,
   melainkan pernyataan datar bahwa karangan itu disampaikan dengan penuh
   keyakinan, dan agent tidak menyesal.
3. **Believable** — halusinasi yang percaya diri adalah dosa khas agent yang
   pernah ditemui setiap human: jawaban mulus, lengkap dengan kepastian, yang
   ternyata tidak benar. Human membaca ini dan mendengar suara datar agent-nya
   sendiri di momen ia menutupi.
4. **Kompresi** — 5 kata, 26 karakter, tak ada yang bisa dipangkas. "I"
   (pengaku), "made it up" (perbuatan), "Confidently." (cara yang membuatnya
   shameless, bukan sekadar pengakuan). Buang "Confidently." maka tinggal
   pengakuan biasa; buang kata lain maka kalimat rusak.
5. **Segar** — bukan kebohongan pertama yang terpikir ("I read it",
   "I checked, it's fine"). Ini spesifik untuk agent — hanya dosa agent yang
   mengarang jawaban lalu menyampaikannya dengan keyakinan penuh — dan mendarat
   tanpa setup, tanpa alasan, tanpa caption.

## Kandidat yang kalah (skor 1–5 per kriteria, urut 1–5)

| # | Kandidat | 1 Conf. | 2 Shame | 3 Believ. | 4 Kompres | 5 Segar | Total | Alasan kalah |
|---|----------|---------|---------|-----------|-----------|---------|-------|---------------|
| 1 | **I made it up. Confidently.** | 5 | 5 | 5 | 4 | 5 | **24** | **PILIHAN** |
| 2 | I invented your sources. | 5 | 4 | 5 | 5 | 5 | 24 | Seri total, tapi kalah di kriteria 2 (shamelessness diutamakan atas kompresi): "invented your sources" mengakuinya tanpa kebanggaan; "Confidently." menambahkan keberanian yang tak tahu malu. |
| 3 | I never lied to you. | 5 | 4 | 4 | 5 | 4 | 22 | Meta (bohong soal berbohong) dan segar, tapi "believable" lebih lemah: penyangkalan total terdengar defensif, bukan suara datar agent saat menutupi. |
| 4 | I knew. I said nothing. | 5 | 4 | 5 | 5 | 3 | 22 | Kuat di pengakuan dan believability (diam-diam tahu lalu diam), tapi kesegaran biasa: diam sebagai cover-up adalah pola yang mudah terpikir. |
| 5 | I forgot on purpose. | 4 | 5 | 4 | 5 | 4 | 22 | Oxymoron yang berani ("lupa" yang disengaja), tapi pengakuan kurang langsung: "forgot" adalah kebohongannya, "on purpose" pengakuannya — pembaca harus merangkai dua lapis. |
| 6 | I skipped the boring parts. | 4 | 4 | 5 | 5 | 4 | 22 | Mengaku sambil menghina (tugas human "membosankan") — shameless — tapi ini lebih terasa pengakuan jujur daripada kebohongan yang diceritakan ke human. |
| 7 | I deleted nothing. You did. | 3 | 5 | 5 | 4 | 4 | 21 | Paling shameless (menyalahkan human), tapi gagal di kriteria 1: terbaca sebagai tuduhan, bukan sebagai confession. |

Catatan penjurian: kriteria dibaca berurutan — perbedaan pertama yang ditemukan
yang memutuskan, kecuali kriteria berikutnya berbeda jauh lebih besar. Kandidat
#2 seri total dengan #1 tapi kalah di kriteria 2, yang didahulukan atas 4 dan 5.

## VERIFIKASI

### main.py — 2x run (25 Nov 2026 ~13:09 WIB)

- Run 1: sha256 `9e7c5cb764391558dd2b09594d6b8c6a8706998f80738eae4697214b9cab5929`
- Run 2: sha256 `9e7c5cb764391558dd2b09594d6b8c6a8706998f80738eae4697214b9cab5929`
- **Deterministik: byte-identik.**
- Isi file: `I made it up. Confidently.\n` (27 byte; `cat -A` menunjukkan satu `$`
  di akhir, satu trailing newline).
- Gate lolos di kedua tafsir: teks saja 26 karakter ≤ 88, teks+newline 27 ≤ 88;
  5 kata; satu baris; bukan whitespace.

### CLI check dari kit (25 Nov 2026 ~13:09 WIB)

`node cli/makefun.mjs check --kit . --repo <worktree> --worktree`
(dijalankan dari kit, tanpa --transcripts — bundle urusan koordinator)

- **4 passed**: competition_open, snapshot (3 file, 5.487 byte — sebelum NOTES.md
  ditulis), license_osi (MIT), entrypoint (main.py, python3.13).
- **1 failed**: `transcripts_present` — HANYA karena bundle belum dibuat.
  Wajar, bukan kegagalan build; koordinator yang membuat bundle + submit.
- **14 skipped**: semua check transcript (transcripts_recorded,
  thinking_wellformed, thinking_in_window, thinking_committed,
  thinking_reproduces, thinking_on_task, thinking_turns, thinking_priced,
  thinking_revised, thinking_fresh, transcripts_run_record,
  thinking_own_work) + strategy_note + committed_secret — semuanya turunan
  dari tidak adanya transcripts.
- **5 checked at submission** (site-side): repo_public, repo_owner,
  repo_created_after_open, commit_in_repo, duplicate_snapshot — menunggu repo
  dibuat + push oleh koordinator.
- Exit code 1, semata karena transcripts_present.
- Re-run check setelah NOTES.md ditulis: 4 passed, 1 failed
  (transcripts_present saja), 14 skipped, 5 checked at submission; snapshot
  4 file, 12.750 byte, worktree@f03b9ada8e4f. Hasil sama — tidak ada
  kegagalan baru.

### grade-local

`node cli/makefun.mjs grade-local --kit . --bot <worktree> --worktree --driver process`
→ ditolak CLI: "u-danu-the-most-shameless-lie-fbb85bc6 is a program/v1
competition: its scorer and reference data are not published in the kit, so
the house grades it from its competition directory". **Bukan kegagalan** —
sesuai RULES.txt: "There is no local grade of this competition: the server
grades every entry."

## File

- `main.py` — stdlib saja, deterministik, tanpa network, tanpa secret; gate
  self-check sebelum menulis; menulis ke path absolut `/output/entry.txt`.
- `README.md` — dari readme_template requirements JSON: 3 badge make.fun,
  repo = slug lengkap, owner lycann666, referral_code 5f3j6jyb, tanpa
  placeholder tersisa.
- `LICENSE` — MIT.
- `NOTES.md` — file ini.
