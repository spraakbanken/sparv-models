
# Files for cstlemma

# cstlemma.suc.{dict,flex} and cstlemma.saldo.{dict,flex}

SUC/SALDO lexicon, in format that fits the CST-lemmatizer

- Format: special cstlemma-files
- Encoding: Latin1
- Created by: cstlemma-train.sh

```
./cstlemma-train.sh suc.cstlemma.lemmas cstlemma.suc.dict cstlemma.suc.flex
./cstlemma-train.sh saldo.cstlemma.lemmas cstlemma.saldo.dict cstlemma.saldo.flex
```

## suc.cstlemma.lemmas

SUC-word list (lexicon), in format that fits to training of the CST-lemmatizer

- Format: tab-separated
- Encoding: Latin1
- Created with: Perl

```
# Copy frequency file from SUC2
cat ../suc2/original/rådata/SUC2.0/WORDLISTS/tagged/freqtextw.txt

# Transform to cstlemma word list file
# The order is FBT: Fullform Baseform Tag
| perl -ne '($freq,$full,@tag)=split; $base=pop(@tag); $tag=join(".",@tag); print "$full\t$base\t$tag\n";'

# Remove numbers
| perl -ne 'print unless /\bRG.NOM/ && /^[\d\W]+\t/'

# Remove all words containing "," (cstlemma does not like commas)
| perl -ne 'print unless /,/'

> suc.cstlemma.lemmas
```

## saldo.cstlemma.lemmas

SALDO, in format that fits training of CST-lemmatizer

- Format: tab-separated
- Encoding: Latin1
- Created with: sparv.modules.saldo.saldo_model, from saldom.xml

```
import sparv.modules.saldo.saldo_model as saldo
lex = saldo.read_xml("saldom.xml", "gf")
saldo.save_to_cstlemmatizer("saldo.cstlemma.lemmas", lex)
```
