# Models related to SALDO analyses

## saldom.xml

SALDOs morphological Lexicon, development version

- Format: XML
- Encoding: UTF8
- Retrieved from: https://svn.spraakdata.gu.se/sb-arkiv/pub/Lexicon/saldom/saldom.xml


## saldo.pickle

SALDOs morphological Lexicon as pickle file

- Format: Python pickle
- Encoding: UTF8
- Created with: sparv.modules.saldo.saldo_model, from saldom.xml


## nst_comp_pos.pickle

NST compound model:probabilities of compound parts of speech

- Trained by: Anne Schumacher
- Trained on: [NST Lexikon](https://svn.spraakdata.gu.se/sb-arkiv/lexikon/NST_svensk_leksikon/nst_utf8.txt)
- Format: Python pickle
- Encoding: UTF8
- Created with: sparv.modules.saldo.nst_comp_model

```
import sparv.modules.saldo.nst_comp_model as train_nst
train_nst.make_model("nst_utf8.txt", "nst_comp_pos.pickle")
```

## stats.pickle

Frequency model with probabilities of word forms and their parts of speech

- Trained on: [stats_all.txt](https://svn.spraakdata.gu.se/sb-arkiv/pub/frekvens/stats_all.txt)
- Format: Python pickle
- Encoding: UTF8
- Created with: sparv.modules.saldo.stats_model


## saldo.baseform.pickle (removed)

SALDO, mapping from word form to base form (lemma)

- Format: Python pickle
- Encoding: UTF8
- Created with: sparv.modules.saldo.saldo_model, from saldom.xml

```
import sparv.modules.saldo.saldo_model as saldo
lex = saldo.read_lmf("saldom.xml", "gf")
saldo.SaldoLexicon.save_to_picklefile("saldo.baseform.pickle", lex)
```

## saldo.lemgram.pickle (removed)

SALDO, mapping from word form to Saldo lemgram

- Format: Python pickle
- Encoding: UTF8
- Created with: sparv.modules.saldo.saldo_model, from saldom.xml

```
import sparv.modules.saldo.saldo_model as saldo
lex = saldo.read_lmf("saldom.xml", "lem")
saldo.SaldoLexicon.save_to_picklefile("saldo.lemgram.pickle", lex)
```

##  saldo.saldoid.pickle (removed)

SALDO, mapping from word form to Saldo-ID

- Format: Python pickle
- Encoding: UTF8
- Created with: sparv.modules.saldo.saldo_model, from saldom.xml

```
import sparv.modules.saldo.saldo_model as saldo
lex = saldo.read_lmf("saldom.xml", "zlem")
saldo.SaldoLexicon.save_to_picklefile("saldo.lemgram.pickle", lex)
```
