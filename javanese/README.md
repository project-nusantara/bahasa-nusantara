# nusantara - Javanese

## Deskripsi Model
nusantara - Javanese adalah model yang dibuat dengan spaCy untuk keperluan *natural language processing* data teks berbahasa Jawa. Model ini dibangun dengan menggunakan korpus [UD_Javanese-UI](https://github.com/UniversalDependencies/UD_Javanese-CSUI) yang merupakan *dependency treebank* bahasa Jawa, sebuah bahasa daerah di Indonesia dengan lebih dari 68 juta pengguna. Korpus ini dikembangkan oleh Alfina dkk. dari Fakultas Ilmu Komputer Universitas Indonesia. Versi terbaru memiliki 1000 kalimat dan 14 ribu kata dengan anotasi manual. Model ini, saat ini memiliki pipeline untuk *tokenizer*, *tagger*, *parser*, dan *lemmatizer* dan ke depan akan ditambahkan untuk *ner* dan *textcat*.

## Kinerja Model
Model ini memiliki skor evaluasi pada korpus tes sebagai berikut:
| Komponen |  Skor  |
|----------|--------|
| TOK      | 99.93  |
| TAG      | 85.67  |
| POS      | 87.16  |
| MORPH    | 85.85  |
| LEMMA    | 61.33  |
| UAS      | 70.44  |
| LAS      | 54.66  |
| SENT P   | 75.44  |
| SENT R   | 85.15  |
| SENT F   | 80.00  |

## Instalasi Model
Untuk melakukan instalasi model nusantara - Javanese dapat dilakukan dengan perintah:
```
$ pip install xx_jv_nusantara-1.0.tar.gz
```

## Penggunaan Model
Berikut adalah contoh penggunaan model nusantara - Javanese:
```
import spacy

nlp = spacy.load("xx_jv_nusantara")

sample_text = "Menawi panjenengan kepingin dipun damelaken shufa, panjenengan saged dhateng ing lantai kalih Peken Gedhe iring kilen, wiwit jam 16.00 WIB ngantos jam 21.00 WIB, sadangunipun gumelaring Solo Imlek Fair. Shufa punika dipun cawisaken kanthi lelahanan minangka program memetri Kabudayan Tionghoa."
doc = nlp(sample_text)

for sent in doc.sents:
    print(sent.text)
```