# Hkka-audio

Audio for the Hakka (Sixian / Hailu) course [Hkka](https://github.com/tbrapor-arch/Hkka). The course app's build
(`tools/build_app.py`, workflow `pages.yml`) checks out this repository and copies the files it uses.
The two folders come from different sources and are under **different licences**. Neither is under the course's
content licence.

## `clips/`: real recordings, 客家委員會
One clip per word (`<unit>-<n>.m4a`) and one per word's example sentence(s) (`<unit>-<n>.ex.m4a`) of the
客語能力認證詞彙 115年度 lists. Sixian: 基礎級 to 高級; Hailu: 基礎級 to 中級. AAC, mono.
`clips/index.json` maps a list entry (`<accent>|<level>:<unit>-<n>`, the `src_id` of `kaga115` in the course
database) to its files.

Cut from the Council's official recordings (Hkka-private, `tools/audio_cut.py`). A small share of the clips were
placed by a duration model rather than by the number heard on the recording; report any clip that says the wrong word.

Licence: 政府資料開放授權條款-第1版 (Open Government Data License, Taiwan, version 1.0).
資料來源：客家委員會（政府資料開放平臺），依政府資料開放授權條款-第1版使用。

## `tts/`: synthetic voice, VoxHakka
The course's titles (`<L>-00`), dialogue lines (`<L>-<nn>`), exercise answers (`ex/<L>-f01` fill, `ex/<L>-t01`
translate) and the new words that have no Council recording (`words/`), in Sixian and Hailu. `L` = lesson 001–100
(進修: P01–P70). `tts/manifest.json` gives, for each file, the text, the spoken pinyin (with tone sandhi), the IPA
sent to the model, the voice and the character speaking.

Generated with VoxHakka, model `formospeech/yourtts-htia-240704` (United Link and National United University),
voices of its training speakers.
Licence: [CC BY-NC 4.0](https://creativecommons.org/licenses/by-nc/4.0/), the model's licence: free,
non-commercial use, with attribution. These are synthetic voices, not native speakers' recordings.
