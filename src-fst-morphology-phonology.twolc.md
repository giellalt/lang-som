
# The Somali morphophonological/twolc rules file 

## Morphophonological notes 

# Phonological Processes in Somali
Somali has several phonological alternations involving reduplication, lenition, vowel harmony
and tone.
The hopes with this documentation is that it will either make twolc rules clearer, or help
if it comes time to completely redo all the rules.
## Spreading processes
### Lenition
The lenis stop series in Somali <b d g> alternates with the fortis series <t k>, note that
the <b> does not actually participate. Lenis stops are found in coda positions, and fortis
stops are found elsewhere. The alternation occurs in both nouns and verbs.
```
ilig ‘tooth'   ~   iligga ‘tooth (Def.)'     ~   ilko ‘teeth (Indef.)’
arag ‘see'     ~   aragtaa ‘2Sg/3SgF sees'   ~   arkaa ‘1Sg/3SgM sees’
```

### Voicing assimilation

Stops assimilate for voicing (or lenis/fortis), particularly across morpheme boundaries,
however they only assimilate if they share place of articulation.
```
aragtaa            ‘2Sg/3SgF sees’
wararka            ‘the news’
buugga             ‘the book’
naagta            ‘the woman’
jaamacadda        ‘the university’
```
This also follows for the retroflex segment <dh>, however the sequence <dhdh> is shortened
to <dh>.
```
gabadh            ‘(a) girl’
gabadha           ‘the girl’
```
### Vowel ablaut
Vowels are subject to two main types of ablaut: (1) full ablaut across back consonants,
and (2) partial ablaut with <a> ~ <e> preceding the high vowel <i>.
Full ablaut is constrained to morpheme boundaries: and most commonly occurs in the ‘waxa’
focus marker.
```
waxaan ‘foc+1Sg'            magac                        rah
wuxuu  ‘foc+3SgM'           magucu    / magacu           ruhu
magicii   / magicii 
```
Full ablaut appears to be optional in some words.
Partial ablaut occurs in verbal infinitives with mostly any word of the pattern CaC. When
the infinitive ending <i> is appended, <a> raises to <e>. It also occurs around person
suffixes and tense ending in <e>
```
tag ‘go'        tegi ‘to go'            tegeen ‘they went’
bax ‘leave'     bexi ‘to leave'         bexeen ‘they left’
```

## <k> deletion

<k> is deleted when it follows a back consonant (which is not <k> itself):
```
wax + ka => waxa
magac + ka => magaca
rah + ka => raha
```
<l> + <t> -> <sh>
Occurs only across morpheme boundaries, in verbs and nouns.
wiilal        =>        wiilasha
‘boys'                  ‘the boys’
maqal        =>        maqashay
‘listen'            ‘2Sg/3SgF listened’
## Vowel harmony
For a complete description of vowel harmony, see the literature.
Short summary: +ATR is the active spreading feature, and spreads leftward across all
boundaries but is blocked by pauses in speech (Intonation Phrase). +ATR can spread
rightward, but stops at the word boundary. It does not cross clitics, typically.
Hopefully VH will be covered in this analyzer.
## Tonal Processes
In certain environments Somali appears to dislike having two tones immediately next
to eachother. I have some collected environments for a phonology paper. May not be
super important right off the bat.
## Reduplication

Somali has two kinds of reduplication: partial and full. Reduplication is typically
a strategy for marking plural in nouns and adjectives in some declensions, but also
appears in verbs as a derivational process. The inflectional processes are quite
productive, but the derivational processes are not as productive.
Partial reduplication occurs in the 4th declension of nouns, but a subtype of these
4th declensional nouns also has full reduplication. Partial reduplication includes
epenthesis of <a>. Note that partial reduplication in adjectives is prefixing,
while in nouns it is suffixing. Also, the template is slightly different.
```
af ‘mouth, language'        =>        afaf    ‘... +Pl’
qoys ‘family'               =>        qoysas    ‘... +Pl’
```
Note: There may be some partial reduplication that also copies the vowel.
Full reduplication also applies to some of these nouns:
```
qof ‘person'                =>         qofqof
cad ‘part'                  =>        cadcad
```
Adjectives:
```
quruxsán ‘beautiful'        =>        qurquruxsán ‘ ... +Pl’
fudúd ‘easy, light'         =>        fudfudúd
adág ‘difficult'            =>        ad'adág
yár ‘a little'              =>        yaryára
gaabán ‘short'              =>        gaaggaabán ‘ ... +Pl’
laabán ‘folded'             =>        laallaabán
jabán ‘broken'              =>        ‘jajabán’
```
Irregular adjectives:
```
dhéer ‘long, tall (sg)'        =>        dhaadhéer
wéyn ‘big'                     =>        waawéyn
```

Note: Other possibilities might be found greping: with ‘^\(.\)aa\1e', ‘^\(.\)aa\1\1aa',
‘\(.\)a\1$’

## Person morphemes

The realization of personal suffixes on verbs is a little complex and depends mostly on
declension type and whether or not the suffix is preceded by the progressive.

Realization of these suffixes is currently all handled by twolc:
```        
sg            pl                
1          {đ}            {ñ}     ==>        
2          {ŧ}             0                
3 Masc     {đ}            {đ}                
3 Fem      {ŧ}                            
Declension 1

sg            pl                    
1            keenaa        keennaa         1        dhacay        dhacnay
2            keentaa       keenaan         2        dhacday        dheceen
3 Masc       keenaa        keentaan        3 Masc    dhacay        dhecdeen
3 Fem        keentaa                       3 Fem    dhacday
Declension 2
sg            pl                     sg
1            sameeyay    sameynay       1        kariyay        karinay
2            sameysay    sameyseen      2        karisay        kariseen
3 Masc       sameeyay    sameeyeen      3 Masc   kariyay        kariyeen
3 Fem        sameysay                   3 Fem    karisay
Declension 3
sg            pl                    
1            furay        furannay            1        watay        wadannay
2            furtay       furateen            2        wadatay        wadateen
3 Masc       furay        fureen              3 Masc    watay        wateen
3 Fem        furtay                           3 Fem    wadatay
```
A short summary:
```
%{đ%} - 1Sg, 3SgM and 3Pl;     realized as 0/y/d in classes
%{ŧ%} - 2Sg, 3SgF, 2Pl;        realized as t/s in classes 
%{ñ%} - 1Pl;                   realized as n in all classes
‘special' here just in case.
```

This process could easily be removed from twolc and done in just flag diacritics, why not?

More processes to describe:
* wataa / wadatay dissimilation
* a/e alternation in -e nouns (noun type is a bit more complex too, as corpus reveals)
* vowel deletion ilig, ilko
* e/y alternation in samee- verbs
* w/b alternations
* vowel lengthening magaalo / magaalooyin

Notes:
* If forms disappear but the rule should work, make sure
that the pair transforming exists in the Alphabet

Alphabet

For ease of reduplication and treating sh as separate from l + t => sh

TODO: write tests for gacmahii / gacmihii, magacii / magicii, magucu / magacu

TODO: tests from these

```
ilig+N+Masc+Pl+Def+PxSg3M+Abs+Prox       il^ik´%>%{N%}a%>híisa#
-- > ilkihiisa 
walaal+N+Masc+Pl+Def+PxSg3M+Abs+Prox     walaal´´%>%{N%}a%>híisa#
-- > walaalihiisa 

magac+N+Masc+Sg+Def+Abs+Dist                magac´´%>%{N%}kii#
-- > magicii 
magac+N+Masc+Sg+Def+Nom+Prox                magac´´%>%{N%}ku#
-- > magucu 
magac+N+Masc+Sg+Def+PxSg3F+Abs+Prox      magac´´%>%{N%}kíisa#
-- > magiciisa 
waxa+CS+Foc/R+Sg3M      wax%>uu#
-- > wuxuu

wax+N+Masc+Sg+Def+PxSg3M+Nom+Prox        wax´´%>%{N%}kíisu#
-- > wixiisu / waxiisu
```

List of rules:

**Ablaut around back fricatives at morpheme boundaries**  

**Ablaut in declension 7 with final vowel**  

**LT -> SH part 1**  

**LT -> SH part 2**  

**LT -> SH part 2 for V3B**  

**LT -> SH in reduplicative plurals, pt 1**  

**V2 {y} deletion**  

**Definite suffix -k to -g next to preceding voiced**  

**t:0 before d h**  

**t/d alternation - definite suffix, V1**  

TODO: dukaammo

**Declension 2: -C doubling in plural**  

TODO: This rule is currently conflicting with the next one.

**Declension 2: -y insertion after back sounds and fricatives; and after -i**  

**Declension 4: Plural Partial Reduplication**  

**Declension 4: Plural Partial Reduplication %{m}**  

**Declension 4: C2->n in m contexts**  

**-y- insertion in plurals**  

**Disallow yy**  

Doesn't work with wuxu, where k has been deleted.
Doesn't work with magicii, magucu, but should optionally. magacii and magicii, etc are both possible

**Declension 6: final vowel**  

**Declension V1: magacow / magacaabay / magacawday, shorten a**  

**Delete preceding a**  

AllBoundaries \?:WordChars

**Declension 7: {-e} delete**  

**Declension 7: final vowel**  

**Declension 7: final vowel in final position**  

## Verbal Rules

**V2A -> V3B derivations, delete -i**  

**V2A -> V3B derivations, depalatization**  

**V1: a/e umlaut before i/e**  

**V1: a/e umlaut before a**  

**V1, D3: Vowel deletion**  

**V1: Simplification of dhd to dh (t)**  

**V1: n/m when deleted vowel results in C0n**  

## V2A

tbw.

## V2B

**V2B: y-insertion**  

**V2B: ey before consonants**  

**V2B: ee before y**  

**V2B: Remove e**  

V3A

## V3B

Following rules are for the funky things that happen with 1Sg, 3SgM, 3Pl
Basically, disallowed d_d, so it gets simplified to t

wada>d>aa#        wada>nn>aa#
wada>t>aa#        wada>d>aan#
wada>d>aa#        wada>t>aan#
wada>t>aa#

wataa                        wadannaa
wadataa                        wadataan
wataa                        wataan
wadataa

fura>d>aa#        fura>nn>aa#
fura>t>aa#        fura>d>aan#
fura>d>aa#        fura>t>aan#
fura>t>aa#

furtaa                        furannaa
furataa                        furataan
furtaa                        furtaan
furataa

Also another type: TODO: merge

sigo+V+IV+1Sg+Ind+Past   sig{a}>d>ay#
sigo+V+IV+2Sg+Ind+Past   sig{a}>t>ay#

sigtay
sigatay

But: obd / cd / hd / qd / xd / yd
Note: bt / obd

**V3B: %{o%}:o finally**  

**V3B: %{o%}:0 in d _ d**  

**V3B: d dissimilation**  

**V3B: d dissimilation w/ cor **  

**V3B: d dissimilation 2 **  

**V3B: root {a} deletion before suffixes with -d**  

**V3B: otherwise**  

General Rules

**Vowel reduction VVV -> VV**  

**m->n in codas**  

**m->m in codas**  

**Optional m doubling**  

**Velar deletion after Back, but avoiding digraphs**  

**Final lenition.**  

**-ee changes to -ye after other vowels**  

**-ee changes to -e after y**  

**-ee clitic deletes preceding -o**  

**progressive nasal assimilation across morphological boundaries**  

* *primus%>s*
* *primus00*

*  examples:*

*  examples:*

*  examples:*

*  examples:*

* * *

<small>This (part of) documentation was generated from [src/fst/morphology/phonology.twolc](https://github.com/giellalt/lang-som/blob/main/src/fst/morphology/phonology.twolc)</small>
