# What is Jyutsoeng
Jyutsoeng（粵雙） is a romanization scheme that maps every Chinese character to a combination of two ASCII characters based on its pronunciation in Cantonese.
The original idea dates back to the discussion in 2013 by **Pan DeCaille@pjdkel** on the Chinese Cantonese Forums.
I have come up with this idea indepently but when I searched it on the Internet I found Pan's post.
I think his idea is great but I am reluctant to press the Shift key for input (especially when I want to use the IME on my Android phone), so I developed my own scheme which uses 38 keys (similar to the keys required by 大易 IME) and realized it with help of the RIME framework
Jyutsoeng is based on the existing Jyutping dictionary in RIME, which can be found at github.com/rime/rime-jyutping

# Why Jyutsoeng
Pan has already elucidated the benefits of jyutsoeng in the original post. Just like the quite common double-pinyin schemes in Mandarin Chinese IME, Jyutsoeng reduces the number of keys one has to press to input a character. Compare ngaang(Jyutping) vs. vh(Jyutsoeng) for inputting the character 硬. Just like any other IME it takes some time to learn Jyutsoeng but once one gets familiar with the keyboard layout he would be able to type quite rapidly. Unlike shape-based codes （形碼） which decomposes the characters into parts and requires one to "write" the character in the mind he wants to type before actually typing it, phonetic-based codes（音碼） just requires one to "speak" it in the mind and is usually considered a more natual process for ordinary people. Jyutsoeng is a good way to reduce key strokes while remaining being phonetic, and is just designed for those whose mother tougue is Cantonese.

# What's special about this IME layout
The IME layout is based on the 26-key 小鶴雙拼 scheme for Mandarin Chinese and uses 38 keys, slightly more than Pan's original design, but saves the need to press the Shift key when typing. This is especially important for mobile devices because on mobile devices Shift key are usually pressed before the key to be combined with it (rather than simutaneously), which results in an extra key stroke and, needless to say, it is not what we hope to happen. Replacing Shift with long-press also requires extra time in typing and is not what we hope.

Here are some points to note for the 38-key keyboard layout:
- The syllable rhymes（韻母） are separated into two groups: those containing oe/eo/yu plus ip and im (group 1), and the rest(group 2)
- To type a syllable with group 1 rhymes, you need to use a special set of keys to type the onset（聲母）, i.e. 0-9 plus the q key (group 1).
- Group 1 rhymes goes with group 1 onsets. Group 2 rhymes goes with group 2 onsets. Thus making full use of the 12 extra keys.
- Group 1 rhymes are assigned on keys with similar rhymes in group 2. For example, both the keys assigned to eng (L) and to ong (S) in group 2 can be used to input the rhyme oeng in group 1.
- Like every 雙拼 scheme, redundancy of the syllable table is exploited and multiple rhymes are assigned to the same key. The onset can be used to uniquely determine which rhyme to use. Do not confuse with rhymes in different groups assigned to the same key.
- Syllables ending with -p, -t, and -k are mainly assigned to the top and right borders of the 38-key layout, and are assigned on keys near the P, T, K keys, respectively.
- Syllables with no onset can be typed in either way just as in 小鶴雙拼. For example, ok can be typed with o+ok (O/) or o+k (OK). A special case is the key A. It is always interpreted as aa in the second way described above. For example AT(aa+t) results in the syllable aat, not at. To get at please type A4(aa+at).
- Some syllables are input by striking the same key twice. This include the following syllables with no onsets: AA(aa), EE(e), OO(o), and the two nasal syllables: MM(m), VV(ng). Note that NG(n+eng) cannot be used to input the syllable ng.
- Besides the zero-onset syllables stated above, the rhymes ng and m are only used with the onset h to form syllables hm and hng

# Examples
- 粵語雙拼輸入法 -> qt qu 0l/0s pk 0u j9 f5
- 入實驗室撳緊急掣 -> j9 s4 q0 s4 g0 gf g9 zr

# Repository structure
Besides this readme file that you are reading, there are only 2 files in this repository. Jyutsoeng.schema.yaml is the only file needed for setting up the IME in Windows/Mac, Jyutsoeng.custom.yaml can be used on mobile devices to change the default behavior since on mobile devices the choosing between alternatives is done by tapping on the alternative rather than striking a key on a physical keyboard.

# Keyboard Layout
The keyboard layout for Jyutsoeng can be found at https://upload.wikimedia.org/wikipedia/commons/a/a8/Jyutsoeng.gif.
Where:
- Red: Group 1 rhymes and onsets (rhymes on the 1st line, onsets on the 2nd)
- Blue: Group 2 rhymes and onsets (rhymes on the 3rd line, onsets on the 4th)
- Black: Original key label

# Looks too complicated? Try it out and you'll find that it's easy to learn, and don't forget to leave your comments.
