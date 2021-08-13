# Hunpos-models and morphtables

## suc3_suc-tags_default-setting_utf8.model

- Trained by: Martin Hammarstedt
- Trained on: SUC3
- Tags: SUC3
- Encoding: UTF8
- Hunpos-settings: default

## suc3_suc-tags_default-setting_utf8-mivoq.model

Same as suc3_suc-tags_default-setting_utf8.model but compiled with [this hunpos version](https://github.com/mivoq/hunpos)
which works on MacOS.

- Trained by: Peter Ljunglöf
- Trained on: SUC3
- Tags: SUC3
- Encoding: UTF8
- Hunpos-settings: default


# Hunpos-morphtables

## saldo_suc-tags.morphtable

- Created by: Martin Hammarstedt
- Tags: SUC3
- Encoding: UTF-8
- Created with: `sparv.modules.hunpos.morphtable`

## suc3_morphtable.words

Tab-separated file with wordforms from SUC, containing: frequency, wordform, tag
(used for creating `hunpos.saldo.suc-tags.morphtable`).

## suc.morphtable

Existing morphtable file, whose contents will be included in the new morphtable 
(`hunpos.saldo.suc-tags.morphtable`).

## suc.patterns

File with regular expressions used for creating `hunpos.saldo.suc-tags.morphtable`.

## parole.morphtable

Same as `hunpos.suc.morphtable` but with parole POS tags.
