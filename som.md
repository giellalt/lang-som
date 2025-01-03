# Somali language model documentation

All doc-comment documentation in one large file.

---

# src-cg3-functions.cg3.md 



* Sets for POS sub-categories

* Sets for Semantic tags

* Sets for Morphosyntactic properties

* Sets for verbs

- V is all readings with a V tag in them, REAL-V should
be the ones without an N tag following the V.  
The REAL-V set thus awaits a fix to the preprocess V ... N bug.

* The set COPULAS is for predicative constructions

* NP sets defined according to their morphosyntactic features

* The PRE-NP-HEAD family of sets

These sets model noun phrases (NPs). The idea is to first define whatever can
occur in front of the head of the NP, and thereafter negate that with the
expression **WORD - premodifiers**.

The set **NOT-NPMOD** is used to find barriers between NPs.
Typical usage: ... (*1 N BARRIER NPT-NPMOD) ...
meaning: Scan to the first noun, ignoring anything that can be
part of the noun phrase of that noun (i.e., "scan to the next NP head")

* Miscellaneous sets

* Border sets and their complements

* Syntactic sets

These were the set types.

## HABITIVE MAPPING

* **hab1** 

* **hab2** 

* **hab3** (<hab> @ADVL>) for hab-actor and hab-case; if leat to the right, and Nom to the right of leat. Lots of restrictions.

* **habNomLeft** 

* **hab4** 	

* **hab6** 

* **hab7** 

* **hab8** This is not HAB
* **hab5**  This is not HAB

* **habDain** (<hab> @ADVL>) for (Pron Dem Pl Loc) if leat followed by Nom to the right

* **habGen** (<hab> @<ADVL) hab for Gen; if Gen is located in the end of the sentence and Nom is sentence initial

* **spred<obj** (@SPRED<OBJ) for Acc; the object of an SPRPED. Not to be mistaken with OPRED. If SPRED is to the left, and copulas is to the left of it. Nom or Hab are found sentence initially.

* **Hab<spred** (@<SPRED) for Nom; if copulas, goallut or jápmit is FMAINV and habitive or human Loc is found to the left. OR: if Ill or @Pron< followed by HAB are found to the left.

* **Hab>Advlcase<spred** (<ext> @<SUBJ) for Nom; it allows adverbials with Ill/Loc/Com/Ess to be found inbetween HAB and <ext>.

* **Nom>Advlcase<spred** (<ext> @<SUBJ) for Nom; it allows adverbials with Ill/Loc/Com/Ess to be found inbetween Nom and <ext> @<SUBJ.

* **<spred** (<ext> @<SUBJ) for Nom; if copulas to the left, and some kind of adverb, N Loc, time related word or Po to the left of it. OR: if Ill or @Pron< to the left, followed by copulas and the before mentioned to the left of copulas. 

* **<spred** (<ext> @<SUBJ) for Nom, but not for Pers. To the left boahtit or heaŋgát as MAINV, and futher to the left is some kind of place related word, or time related word

* **<spredQst1** (<ext> @<SUBJ) for Nom in a typically question sentence; if A) Hab, some kind of place word, Po or Nom to the left, and Qst followed by copulas to the left. B) same as a, only the Qst-pcle is attached to copulas. C) Qst to the left, with copulas to its left, but not if two Nom:s are found somewhere to the right. D) copulas to the left, and BOS to the left. E) Loc or Ill to the left, and Loc or Hab to the left of this, Qst and copulas to the left. F) Num @>N to the left, Hab, some kind of place word, Po or Nom to the left, and Qst followed by copulas to the left. NOTE) for all these rules; human, Loc or Sem/Plc not allowed to the right.

* **<spredQst2** (@<SPRED) for Nom; in a typically question sentence; differs from <spredQst1 by not beeing as restricted to the right. Though you are not allowed to be Pers or human.

* **Nom<spredQst** (@<SPRED) for Nom; in a typically question sentence. Differs from <spredQst2 by letting Nom be found between SPRED and copulas

* **<spred** (@<SPRED) for A Nom or N Nom if; the subject Nom is on the same side of copulas as you: on the right side of copulas

* **<spredVeara** (@<SPRED) for veara + Nom; if genitive immediately to the right, and intransitive mainverb to the right of genitive

* **leftCop<spred** (@<SPRED) for Nom; if copulas is the main verb to the left, and there is no Ess found to the left of cop (note that Loc is allowed between target and cop). OR: if you are Coll or Sem/Group with copulas to your left. 

* **<spredLocEXPERIMENT** (@<SPRED) for material Loc; if you are to the right of copulas, and the Nom to the left of copulas is not a hab-actor

* **NumTime** (@<SPRED) for A Nom

* **<spredSg** (@<SPRED) for Sg Nom	

* **<spredPg** (@<SPRED) for Pl Nom	

* **<spred** (@<SPRED) for Nom; if copulas to the left, and Nom or sentence boundary to the left of copulas. First one to the right is EOS.

* **<spred** (@<SPRED) for N Ess

* **spredEss>** (@SPRED>) for N Ess; if copulas to the right of you, and if an NP with nom-case first one to your left.

* **HABSpredSg>** (@SPRED>) for Nom; if habitive first one to the left, followed by copulas.

* **GalleSpred>** (@SPRED>) for Num Nom; if sentence initial

* **spredSgMII>** (@SPRED>)

* **r492>** (@SPRED>) for Interr Gen; consisting only of negations. You are not allowed to be MII. You are not allowed to have an adjective or noun to yor right. You are not allowed to have a verb to your right; the exception beeing an aux.

* **AdjSpredSg>** (@SPRED>) for A Sg Nom; if copulas to the right, but not if A or @<SPRED are found to the right of copulas

* **SpredSg>Hab** (@SPRED>) for Nom; if you are sentence initial, copulas is located to the right, and there is a habitive to the right of copulas

* **Spred>SubjInf** (@SPRED>) for Nom; if copulas to the right, and the subject of copulas is an Inf to the right

* **spredCoord** (@<SPRED) coordination for Nom; only if there already is a SPRED to the left of CNP. Not if there is some kind of comparison involved.

* **subj>Sgnr1** (@SUBJ>) for Nom Sg, including Indef Nom if; VFIN + Sg3 or Pl3 to the right (VFIN not allowed to the left) 

* **subj>Du** (@SUBJ>) for dual nominatives, including Coll Nom. VFIN + Du3 to the right. 
* **subj>Pl** (@SUBJ>) for plural nominatives, including Coll and Sem/Group. VFIN + Pl3 to the right.

* **subj>Pl** (@SUBJ>) for plural nominatives

* **subj>Sgnr2** (@SUBJ>) for Nom Sg; if VFIN + Sg3 to the right.

* **<subjSg** (@<SUBJ) for Nom Sg; if VFIN Sg3 or Du2 to the left (no HAB allowed to the left).

* **f<advl** (@-F<ADVL) for infinite adverbials

* **f<advl** (@-F<ADVL) for infinite adverbials

* **s-boundary=advl>** (@ADVL>) for ADVL that resemble s-booundaries. Mainverb to the right.

* **-fobj>** (@-FOBJ>) for Acc 

* **-fobj>** (@-FOBJ>) for Acc

* **advl>mainV** (@ADVL>) if; finite mainverb not found to the left, but the finite mainverb is found to the right.

* **<advl** (@<ADVL) if; finite mainverb found to the left. Not if a comma is found immediately to the left and a finite mainverb is located somewhere to the right of this comma.

* **<advlPoPr** (@<ADVL) if mainverb to the left.
* **advlPoPr>** (@<ADVL) if mainverb to the right.

* **advlEss>** (@<ADVL) for weather and time Ess, if FMAINV to the left.

* **advl>inbetween** (@ADVL>) for Adv; if inbetween two sentenceboundaries where no mainverb is present.

* **comma<advlEOS** (@<ADVL) if; comma found to the left and the finite mainverb to the left of comma. To the right is the end of the sentence.

* **advlBOS>** (@ADVL>) if; you are N Ill and found sentnece initially. First one to your right is a clause.

* **<advlPoEOS** (@<ADVL) for Po; if you are found at the very end of a sentence. A mainverb is needed to the right though.

* **cleanupILL<advl** (@<ADVL) for N Ill if; there are no boundarysymbols to your left, if you arent already @N< OR @APP-N<, and no mainverb is to yor left.

* **<opredAAcc** (@<OPRED) for A Acc; if an other accusative to the left, and a transtive verb to the left of it. OR: if a transitive verb to the left, and an accusative to the left of it.

### sma object

* **<advlEss** (@<ADVL) for ESS-ADVL if; FMAINV to the left
* **<spredEss** (@<SPRED) for N Ess if; FMAINV to the left is intransitive or bargat

## SUBJ MAPPING - leftovers

## OBJ MAPPING - leftovers

## HNOUN MAPPING

* * *

<small>This (part of) documentation was generated from [src/cg3/functions.cg3](https://github.com/giellalt/lang-som/blob/main/src/cg3/functions.cg3)</small>

---

# src-fst-morphology-affixes-adjectives.lexc.md 

Adjective inflection
The Somali language adjectives compare.

* * *

<small>This (part of) documentation was generated from [src/fst/morphology/affixes/adjectives.lexc](https://github.com/giellalt/lang-som/blob/main/src/fst/morphology/affixes/adjectives.lexc)</small>

---

# src-fst-morphology-affixes-irregularverbs.lexc.md 


Irregular verbs

These are the "irregular" verbs, which are mostly prefixing or copular.

The copulas are mostly suffixing, and all the other verbs include person
prefixes, and agreement on suffixes for person. Tense and mood are
expressed with complex stem alternations that are no longer 100% productive,
and progressive is formed from a derivational stem, with no person prefixes.

NB: After adding in some additional morphological boundaries for some of the
verbs, it should become obvious that some more simplification in amount
of lexica is possible. Prefixing verbs often have multiple stems for
separate tenses, and more or less get the same person prefixes in
full and reduced paradigms. The only trick there is it requires more
flag diacritics, to make sure that the prefix matches the suffix.

TODO: omg

LEXICON MA  _ma_ and related inflected forms.

Ah

_ah_ is a verb meaning 'to exist', but can function as a copula. It is
inflected in all tenses, but has long and short forms.

LEXICON Ah  Inflections in tense.

* * *

<small>This (part of) documentation was generated from [src/fst/morphology/affixes/irregularverbs.lexc](https://github.com/giellalt/lang-som/blob/main/src/fst/morphology/affixes/irregularverbs.lexc)</small>

---

# src-fst-morphology-affixes-nouns.lexc.md 

Noun inflection
The Somali nouns inflect in cases, are marked for gender and number.

* * *

<small>This (part of) documentation was generated from [src/fst/morphology/affixes/nouns.lexc](https://github.com/giellalt/lang-som/blob/main/src/fst/morphology/affixes/nouns.lexc)</small>

---

# src-fst-morphology-affixes-propernouns.lexc.md 

Proper noun inflection
The Somali language proper nouns inflect in the same cases as regular
nouns, but with a colon (':') as separator.

* * *

<small>This (part of) documentation was generated from [src/fst/morphology/affixes/propernouns.lexc](https://github.com/giellalt/lang-som/blob/main/src/fst/morphology/affixes/propernouns.lexc)</small>

---

# src-fst-morphology-affixes-symbols.lexc.md 


# Symbol affixes

* * *

<small>This (part of) documentation was generated from [src/fst/morphology/affixes/symbols.lexc](https://github.com/giellalt/lang-som/blob/main/src/fst/morphology/affixes/symbols.lexc)</small>

---

# src-fst-morphology-affixes-verbs.lexc.md 

Verb inflection
The Somali language verbs inflect in persons.

Full            Reduced
1Sg    A               A
2Sg    B               A
3SgM   A               A
3SgF   B               B
1Pl    C               C
2Pl    D               A
3Pl    E               A

Present         Past
1Sg    keenaa          keenay
2Sg    keentaa         keentay
3SgM   keenaa          keenay
3SgF   keentaa         keentay
1Pl    keennaa         keennay
2Pl    keentaan        keenteen
3Pl    keenaan         keenaan

Present         Past
1Sg    keénayaa        keénayay
2Sg    keénaysaa       keénaysay
3SgM   keénayaa        keénayay
3SgF   keénaysaa       keénaysay
1Pl    keénaynaa       keénaynay
2Pl    keénaysaan      keénayseen
3Pl    keénayaan       keénayeen

Apply post-root tones, and other root triggers

* * *

<small>This (part of) documentation was generated from [src/fst/morphology/affixes/verbs.lexc](https://github.com/giellalt/lang-som/blob/main/src/fst/morphology/affixes/verbs.lexc)</small>

---

# src-fst-morphology-phonology.twolc.md 


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

---

# src-fst-morphology-root.lexc.md 


# Somali morphological analyser

INTRODUCTION TO THE MORPHOLOGICAL ANALYSER OF SOMALI.

# Multichar_Symbols definitions

## Analysis symbols

The morphological analyses of Somali wordforms are presented
in this system in terms of the following symbols.
(It is highly suggested to follow existing standards when adding new tags).

The parts-of-speech are:

* +N	  
* +V	  
* +A	  
* +Adp      
* +Q	  
* +Pr	  
* +Adv      
* +CC	  
* +CS	  
* +Interj   
* +Pron     
* +Num      

Fusional adpositions

*  +Adp/u	    Fusional ú
*  +Adp/ka    Fusional ká
*  +Adp/la    Fusional lá
*  +Adp/ku    Fusional kú

Object pronouns in adpositional+pronoun

*  +1SgObj/i      E.x.: la + i + lá  -> laylá
*  +2SgObj/ku     E.x.: la + ku + lá -> lagulá

Focus

* +Foc/L    Focus markers **baa** and **ayaa**
* +Foc/R    Focus marker **waxaa**
* +Foc/V	  ??2023-12-07 validating Jaska
* +Foc/baa  ??2023-12-07 validating Jaska

The parts of speech are further split up into:

* +Interr             
* +Interr/ma          
* +Attr        
* +Short        
* +Cmp        
* +Der/sho        
* +Pfx        
* +PP        
* +Sep        
* +Com		      
* +Appos        
* +Impers        
* +Inch				      

*  +Recit        
* +Restr						      

*  +Pers	      
*  +Dem	      
*  +Coll	      
*  +Mass	      
*  +Acr	      
*  +Abstr	      
*  +Abbr        
*  +Prop        

*  +Null  ??2023-12-07 validating Jaska
*  +V/ah  ??2023-12-07 validating Jaska
*  +V/  ??2023-12-07 validating Jaska

Verb and noun declensions for the analysers that want to know about that
NOTE: We probably do not want to thag these, this is morphological and
not morphosyntactic info. t.

* +Decl/1 				      
* +Decl/2 				      
* +Decl/2A				      
* +Decl/2B    
* +Decl/3 +Decl/3A +Decl/3B    
* +Decl/4 				      
* +Decl/5				      
* +Decl/6 				      
* +Decl/7				      

The Usage extents are marked using the following tags:

*  +Err/Orth				      
*  +Use/-Spell				      
*  +Use/-Spell				      
*  +Use/Circ				      
*  +Use/CircN				      
*  +Err/Lex				      
*  +Use/Marg				      
*  +Use/NG				      
*  +Use/Ped				      
*  +Use/SpellNoSugg+Prog				      
*  +Err/Orth				      

The nominals are inflected in the following case, number

* +Sg				      
* +Pl				      

* +Nom				      
* +Abs				      
* +Gen				      

* +Indef				      
* +Def				      

Nominals also are inflected for gender

*  +Masc				      
*  +Fem				      

Nominal marked for gender undergo gender polarity changes in plural.
We want to mark +Masc and +Fem, such that disambiguation is easier,
but knowing the gender of the lemma since it is not predictable from
a given plural form is a good thing.

*  +M→M				      
*  +M→F				      
*  +F→M				      
*  +F→F				      

Nominals also have affixed demonstratives

*  +Prox       -0
*  +Dist       -ii
*  +Near       -aas / -aasi
*  +Far        -eer / -eeri
*  +Farther    -oo / -ooyi
*  +Close      -an / -anu / -ani

Are these in use?

*  +Adc            
*  +Apr            
*  +Prl            
*  +Apr            
*  +Cns            
*  +Ord            

The possession is marked as such:

*  +PxSg1          
*  +PxSg2          
*  +PxSg3F         
*  +PxSg3M         

*  +PxPl1          
*  +PxPl1Incl      
*  +PxPl1Excl      
*  +PxPl2          
*  +PxPl3          

The comparative forms are:

*  +Comp	   
*  +Superl   

Numerals are classified under:

*  +Attr   
*  +Card   
*  +Ord    

Verb moods are:

*  +Ind     
*  +Opt     
*  +Imprt   
*  +Neg     
*  +Imper   

Verb tenses

*  +Past   
*  +Pres   

Verb aspects are:

*  +Prog   

Verb personal forms are (NB: no inclusive/exclusive):

* +1Sg    
* +2Sg    
* +3Sg    
* +3SgM   
* +3SgF   
* +1Pl    
* +2Pl    
* +3Pl    

Verbs also mark some non-agreement syntactic information

*  +Red  occurs often with subjects that are focused
*  +Rel  the verb is within a relative clause, and is also case marked.

Other verb forms are

* +Inf	    
* +Ger	    
* +ConNeg	    
* +ConNegII   
* +Neg	    
* +ImprtII    
* +PrsPrc	    
* +PrfPrc	    
* +Sup	    
* +VGen	    
* +VAbess	    

Abbreviated words are classified with:

*  +ABBR   
* +Symbol = independent symbols in the text stream, like £, €, ©
*  +ACR   

Special symbols are classified with:

* +CLB    
* +PUNCT   
* +LEFT    
* +RIGHT   

The verbs are syntactically split according to transitivity:

* +TV   
* +IV   
* +DV   

Special multiword units are analysed with:

*  +Multi   

Non-dictionary words can be recognised with:

*  +Guess   
*  ^GUESSNOUNROOT   

Question and Focus particles:

*  +Qst   
*  +Foc  

Semantics are classified with

*  +Sem/Plc   

Derivations are classified under the morphophonetic form of the suffix, the
source and target part-of-speech.

*  +V→N 	    
*  +V→V 	    
*  +V→A	    
*  +Der/xxx   

*  +Incl 	    
*  +Excl	    

Syntaxy stuff, don't want to use +Acc, because this isn't relevant in nouns

*  +Subj   
*  +Sem/Obj  

Nominal MSP

*  +Rel  

Derivation

*  +Der/A  
*  +Der/V  
*  +Der/N  

Clitics

*  +Clit/ba  
*  +Clit/se  
*  +Clit/na  
*  +Clit/oo  

*  +Clit/CS  
*  +Clit/Without  

Style

*  +Use/NG  

*  +Sty   
*  +Sty/TODO  
*  +Sty/i  
*  +Sty/D  
*  +Sty/R  

*  +TODO  

## Morphophonology

To represent phonologic variations in word forms we use the following
symbols in the lexicon files:

* {N}    For tagging certain twolc rules as nominal-only

Going to try to replace these with flag diacritics if possible.

And following triggers to control variation

* {#} # -      

TODO: no need for , but needs to be removed in all files

*  {m}     in nouns: for marking m~n alternations
*  {mm}    in nouns: rare instance of mm ~ n
*  {C2}    in nouns: consonant reduplication in noun declension 4. (yaab ~ yaabab)

*  {X}     in nouns: insertion of some kind in noun definiteness. TODO: twolc rule no longer exists?
*  {ae}    in verbs: umlaut of a~i in some verb stems (seems restricted to specific lexemes, not productive)
*  {e}     in nouns: -e- variation in declension 7 (waraabe ~ waraabaha), not 100% predictable
*  {-e}    in nouns: delete final -e, often used in conjunction with {a}, possible room for cleaning up.
*  {a}     in verbs: Mostly V3B: has alternation between o ~ a. (sigo ~ sigaday)
*  {-V}    in verbs: deletion of specific vowel, used only in affixes, to make stems prettier? room for cleaning
*  {-I}    in verbs: -i- deletions in V3A and -san adjectives
*  {-a}    used specifically in -sho derivations. TODO: change to rule with » ?

*  {E}     part of cliticized ee (CS+Appos)

*  {y}     in verbs: -y- deletion in certain parts of V2

Tone

*  ´´     

## Symbols that need to be escaped on the lower side (towards twolc):
* **»7**:  Literal »
* **«7**:  Literal «
```
 %[%>%]  - Literal >
 %[%<%]  - Literal <
```

## Flag diacritics
We have manually optimised the structure of our lexicon using following
flag diacritics to restrict morhpological combinatorics - only allow compounds
with verbs if the verb is further derived into a noun again:
|  @P.NeedNoun.ON@ | (Dis)allow compounds with verbs unless nominalised
|  @D.NeedNoun.ON@ | (Dis)allow compounds with verbs unless nominalised
|  @C.NeedNoun@ | (Dis)allow compounds with verbs unless nominalised

For languages that allow compounding, the following flag diacritics are needed
to control position-based compounding restrictions for nominals. Their use is
handled automatically if combined with +CmpN/xxx tags. If not used, they will
do no harm.
|  @P.CmpFrst.FALSE@ | Require that words tagged as such only appear first
|  @D.CmpPref.TRUE@ | Block such words from entering ENDLEX
|  @P.CmpPref.FALSE@ | Block these words from making further compounds
|  @D.CmpLast.TRUE@ | Block such words from entering R
|  @D.CmpNone.TRUE@ | Combines with the next tag to prohibit compounding
|  @U.CmpNone.FALSE@ | Combines with the prev tag to prohibit compounding
|  @P.CmpOnly.TRUE@ | Sets a flag to indicate that the word has passed R
|  @D.CmpOnly.FALSE@ | Disallow words coming directly from root.

Use the following flag diacritics to control downcasing of derived proper
nouns (e.g. Finnish Pariisi -> pariisilainen). See e.g. North Sámi for how to use
these flags. There exists a ready-made regex that will do the actual down-casing
given the proper use of these flags.
|  @U.Cap.Obl@ | Allowing downcasing of derived names: deatnulasj.
|  @U.Cap.Opt@ | Allowing downcasing of derived names: deatnulasj.

* @P.VCLASS.V1@  @R.VCLASS.V1@				     
* @P.VCLASS.V1ow@  @R.VCLASS.V1ow@			     
* @P.VCLASS.V1ow2@  @R.VCLASS.V1ow2@			     

* @P.VCLASS.V2A@ @R.VCLASS.V2A@				     
* @P.VCLASS.V2B@ @R.VCLASS.V2B@				     
* @P.VCLASS.V3A@ @R.VCLASS.V3A@				     
* @P.VCLASS.V3B@ @R.VCLASS.V3B@				     
* @P.VCLASS.V3B_ADel@ @R.VCLASS.V3B_ADel@		     
* @P.VCLASS.V3B_ADelPart@ @R.VCLASS.V3B_ADelPart@  
* @P.VCLASS.PREFIXING@						     

* @U.VCLASS.V1@ 								     
* @U.VCLASS.V2A@								     
* @U.VCLASS.V2B@								     
* @U.VCLASS.V3A@								     
* @U.VCLASS.V3B@								     
* @U.VCLASS.UREFIXING@						     

* @P.ATR.True@								     
* @R.ATR.True@								     

Person flags

* @U.Pers.1Sg@      
* @U.Pers.2Sg@      
* @U.Pers.3SgM@     
* @U.Pers.3SgF@     

* @U.Pers.1Pl@      
* @U.Pers.2Pl@      
* @U.Pers.3Pl@      

* @P.Pers.1Sg@      
* @P.Pers.2Sg@      
* @P.Pers.3SgM@     
* @P.Pers.3SgF@     

* @P.Pers.1Pl@      
* @P.Pers.2Pl@      
* @P.Pers.3Pl@      

* @R.Pers.1Sg@      
* @R.Pers.2Sg@      
* @R.Pers.3SgM@     
* @R.Pers.3SgF@     

* @R.Pers.1Pl@      
* @R.Pers.2Pl@      
* @R.Pers.3Pl@      

* @R.Gender.Masc@   
* @P.Gender.Masc@   

* @R.Gender.Fem@    
* @P.Gender.Fem@    

# The continuation lexica

The word forms in Somali start from the lexeme roots of basic
word classes, or optionally from prefixes:

* LEXICON Root   

* Abbreviations   ;   

* Nouns           ;   
* ProperNouns     ;   

* Numerals        ;   

* Pronouns        ;   

* Verbs           ;   
* IrregularVerbs  ;   
* VerbalPrefixes  ;    Certain VP elements often get combined with the verbs in writing.
* Adjectives      ;    Some have verb morphology, and some view them to just be a 4th declension of verbs.

* Adverbs         ;   

* Conjunctions    ;   
* Subjunctions    ;   

* Adpositions     ;   
* Determiners     ;   
* Interjections   ;   
* Punctuation     ;   
* Symbols         ;   

## The following are coming from som-lex.txt
* IrregularAdjective ;
* Prefixes  ;

* LEXICON FINAL_NG  just adds the +Use/NG tag to lower ##

* LEXICON FINAL  just adds lower ##

These lexica are dummy lexical to make the source compile, they contain only #.

* LEXICON Proper   

* LEXICON Unknown_Declensions  

* LEXICON Obj_Pron  

* LEXICON SemiReducedPerson  

* * *

<small>This (part of) documentation was generated from [src/fst/morphology/root.lexc](https://github.com/giellalt/lang-som/blob/main/src/fst/morphology/root.lexc)</small>

---

# src-fst-morphology-stems-adjectives.lexc.md 

Adjectives
Adjectives in the Somali language describe things.

* * *

<small>This (part of) documentation was generated from [src/fst/morphology/stems/adjectives.lexc](https://github.com/giellalt/lang-som/blob/main/src/fst/morphology/stems/adjectives.lexc)</small>

---

# src-fst-morphology-stems-adpositions.lexc.md 



Real Prepositions
These are the few actual prepositions that exist in Somali.

* LEXICON RealPrepositions  

Locative adpositions
These are a part of the verb complex, mark other kinds of locations than the
basic ones below.

Ex.) Gurigaa gashaba hoos buu ka guban.
THe house burned down from inside.

Simple adpositions
These imply something about the motion of the verb. All have high tones.

Fusional adpositions

Negation
The negative marker _ma_ may fuse with the simple adpositions, maintaining its low tone. (ú + ma -> úma)

Long form pronouns and adpositions, and CS

* * *

<small>This (part of) documentation was generated from [src/fst/morphology/stems/adpositions.lexc](https://github.com/giellalt/lang-som/blob/main/src/fst/morphology/stems/adpositions.lexc)</small>

---

# src-fst-morphology-stems-nouns.lexc.md 

Nouns

Nouns in Somali have separate paradigms depending on
morphophonological stuff, but are split up into subgroups which correspond
to gender polarity groups.

Note that items containing ATR should mark the ATR using <¨> before the vowel
or at the beginning of the stem if uncertain.

```
doog:¨doog NOUN1_M/SgOnly ;
```

Irregular nouns
_il_ and _si_ are both female in singular, and have typical morphology there
but, have varying irregular masculine plural forms.

* LEXICON IrregNouns  

* il # Irregular tests examples:*
* *il:* `il+N+Fem+Sg+Indef+Abs`
* *isha:* `il+N+Fem+Sg+Def+Abs+Prox`
* *indho:* `il+N+Masc+Pl+Indef+Abs`
* *indhaha:* `il+N+Masc+Pl+Def+Abs+Prox`

* il # Irregular tests examples:*
* *si:* `si+N+Fem+Sg+Indef+Abs`
* *sida:* `si+N+Fem+Sg+Def+Abs+Prox`
* *siyaabo:* `si+N+Masc+Pl+Indef+Abs`
* *siyaabaha:* `si+N+Masc+Pl+Def+Abs+Prox`

Declension 1: F→M

TODO: write quick overview of morphosyntax, morphophon
-i for some nominatives. Pl is -o.

Good amount of nouns with -ad, Fem derivational suffix.

* aalad # aalad sample paradigm. examples:*
* *aalad:* `aalad+N+Decl/1+Fem+Sg+Indef+Abs`
* *aaladda:* `aalad+N+Decl/1+Fem+Sg+Def+Abs+Prox`
* *aalado:* `aalad+N+Decl/1+Masc+Pl+Indef+Abs`
* *aaladaha:* `aalad+N+Decl/1+Masc+Pl+Def+Abs+Prox`

Declension 1: M, sg. only

Declension 1: M→M, M→F

Declension 1: Masc. Pl. Only

Declension 1: Fem. Sg. Only

A fair amount of abstract things, and some collective things that probably need
to be moved to collective lexica.

Declension 2

Declension 2: Collective

Groups of things, -ley is a common suffix. Taged with +Coll, but available
only in singular.

Declension 2: M→F
-yo is plural.

Declension 2: M→F

Some consonant doubling in plurals with -o, some with -yo, no doubling.

Declension 2: M→M - Arabic words with Somali plurals.

Declension 2: F→F
-yo plurals

Declension 2: M→F - collectives

TODO: these are collectives, but not marked as such and perhaps should be.
but also, they have plurals. May be marked as collectives because of Orwin

Declension 2: M→F - Mass

TODO: these are mass nouns, but not marked as such and perhaps should be.
Plurals found in word lists, so maybe these need some special handling.

Declension 3: M→M
These are fun, because plurals delete the second vowel.
Ex.) gabadh -> gabdho; xubin -> xubno
Note that some of these have lenis/fortis changes:
Ex.) xadhig -> xadhko

Declension 3: F→M

* gabadh # dh + d -> dh; vowel deletion examples:*
* *gabadh:* `gabadh+N+Fem+Sg+Indef+Abs`
* *gabadha:* `gabadh+N+Fem+Sg+Def+Abs+Prox`
* *gabdho:* `gabadh+N+Masc+Pl+Indef+Abs`
* *gabdhaha:* `gabadh+N+Masc+Pl+Def+Abs+Prox`

Declension 3: M→M

* xadhig # g ~ k; vowel deletion examples:*
* *xadhig:* `xadhig+N+Masc+Sg+Indef+Abs`
* *xadhigga:* `xadhig+N+Masc+Sg+Def+Abs+Prox`
* *xadhko:* `xadhig+N+Masc+Pl+Indef+Abs`
* *xadhkaha:* `xadhig+N+Masc+Pl+Def+Abs+Prox`

Arabic loan plural forms
These are borrowed Arabic plural forms for Arabic loans. Not really predictable
but mostly taken from Qaamuuska af-Soomaaliga.

Ex.) 

* amar -> awaamiir
* axmaq -> axmaqiin
* banki -> bunuug

* LEXICON ArabicLoans  

* guri # Odd-syllable test examples:*
* *guri:* `guri+N+Masc+Sg+Indef+Nom`

* * *

<small>This (part of) documentation was generated from [src/fst/morphology/stems/nouns.lexc](https://github.com/giellalt/lang-som/blob/main/src/fst/morphology/stems/nouns.lexc)</small>

---

# src-fst-morphology-stems-numerals.lexc.md 

Numerals
Numerals in the Somali language are numbers.

* * *

<small>This (part of) documentation was generated from [src/fst/morphology/stems/numerals.lexc](https://github.com/giellalt/lang-som/blob/main/src/fst/morphology/stems/numerals.lexc)</small>

---

# src-fst-morphology-stems-prefixes.lexc.md 

Prefixes
Prefixes in the Somali language are bound to beginning of other words.

* * *

<small>This (part of) documentation was generated from [src/fst/morphology/stems/prefixes.lexc](https://github.com/giellalt/lang-som/blob/main/src/fst/morphology/stems/prefixes.lexc)</small>

---

# src-fst-morphology-stems-pronouns.lexc.md 

Pronouns
Pronouns in the Somali language are references to things.

* * *

<small>This (part of) documentation was generated from [src/fst/morphology/stems/pronouns.lexc](https://github.com/giellalt/lang-som/blob/main/src/fst/morphology/stems/pronouns.lexc)</small>

---

# src-fst-morphology-stems-propernouns.lexc.md 



Ruuxa the spirit
Suuriya placetag "Syrian" ; Suuriyihii

* * *

<small>This (part of) documentation was generated from [src/fst/morphology/stems/propernouns.lexc](https://github.com/giellalt/lang-som/blob/main/src/fst/morphology/stems/propernouns.lexc)</small>

---

# src-fst-morphology-stems-verbs.lexc.md 

Verbs
Verbs in Somali language are actions, and also states. They agree in person
and number, and also gender.

* * *

<small>This (part of) documentation was generated from [src/fst/morphology/stems/verbs.lexc](https://github.com/giellalt/lang-som/blob/main/src/fst/morphology/stems/verbs.lexc)</small>

---

# src-fst-phonetics-txt2ipa.xfscript.md 



retroflex plosive, voiceless			t`  ʈ	    0288, 648 (` = ASCII 096)
retroflex plosive, voiced			d`	ɖ		0256, 598
labiodental nasal					F 	ɱ		0271, 625
retroflex nasal						n` 	ɳ		0273, 627
palatal nasal						J 	ɲ		0272, 626
velar nasal							N 	ŋ		014B, 331
uvular nasal							N\	ɴ		0274, 628
	
bilabial trill						B\ 	ʙ		0299, 665
uvular trill							R\ 	ʀ		0280, 640
alveolar tap							4	ɾ		027E, 638
retroflex flap						r` 	ɽ		027D, 637
bilabial fricative, voiceless		p\ 	ɸ		0278, 632
bilabial fricative, voiced			B 	β		03B2, 946
dental fricative, voiceless			T 	θ		03B8, 952
dental fricative, voiced				D 	ð		00F0, 240
postalveolar fricative, voiceless	S	ʃ		0283, 643
postalveolar fricative, voiced		Z 	ʒ		0292, 658
retroflex fricative, voiceless		s` 	ʂ		0282, 642
retroflex fricative, voiced			z` 	ʐ		0290, 656
palatal fricative, voiceless			C 	ç		00E7, 231
palatal fricative, voiced			j\ 	ʝ		029D, 669
velar fricative, voiced	        	G 	ɣ		0263, 611
uvular fricative, voiceless			X	χ		03C7, 967
uvular fricative, voiced				R 	ʁ		0281, 641
pharyngeal fricative, voiceless		X\ 	ħ		0127, 295
pharyngeal fricative, voiced			?\ 	ʕ		0295, 661
glottal fricative, voiced			h\	ɦ		0266, 614

alveolar lateral fricative, vl.		K 
alveolar lateral fricative, vd.		K\

labiodental approximant				P (or v\) 
alveolar approximant					r\ 
retroflex approximant				r\` 
velar approximant					M\

retroflex lateral approximant		l` 
palatal lateral approximant			L 
velar lateral approximant			L\
Clicks

bilabial								O\	(O = capital letter) 
dental								|\
(post)alveolar						!\ 
palatoalveolar						=\ 
alveolar lateral						|\|\
Ejectives, implosives

ejective								_>	e.g. ejective p		p_>
implosive							_<	e.g. implosive b	b_<
Vowels

close back unrounded					M
close central unrounded 				1 
close central rounded				} 
lax i								I 
lax y								Y 
lax u								U

close-mid front rounded				2 
close-mid central unrounded			@\ 
close-mid central rounded			8 
close-mid back unrounded				7

schwa	ə							@

open-mid front unrounded				E 
open-mid front rounded				9
open-mid central unrounded			3 
open-mid central rounded				3\ 
open-mid back unrounded				V 
open-mid back rounded				O

ash (ae digraph)						{ 
open schwa (turned a)				6

open front rounded					& 
open back unrounded	        		A 
open back rounded					Q
Other symbols

voiceless labial-velar fricative		W 
voiced labial-palatal approx.		H 
voiceless epiglottal fricative		H\ 
voiced epiglottal fricative			<\ 
epiglottal plosive					>\

alveolo-palatal fricative, vl. 		s\ 
alveolo-palatal fricative, voiced	z\ 
alveolar lateral flap				l\ 
simultaneous S and x					x\ 
tie bar								_
Suprasegmentals

primary stress						" 
secondary stress						% 
long									: 
half-long							:\ 
extra-short							_X 
linking mark							-\
Tones and word accents

level extra high						_T 
level high							_H
level mid							_M 
level low							_L 
level extra low						_B
downstep								! 
upstep								^	(caret, circumflex)

contour, rising						 
contour, falling						_F 
contour, high rising					_H_T 
contour, low rising					_B_L 

contour, rising-falling				_R_F 
(NB Instead of being written as diacritics with _, all prosodic 
marks can alternatively be placed in a separate tier, set off 
by < >, as recommended for the next two symbols.)
global rise						<R> 
global fall						<F>
Diacritics						
									
voiceless						_0	(0 = figure), e.g. n_0
voiced							_v 
aspirated						_h 
more rounded						_O	(O = letter) 
less rounded						_c 
advanced							_+
retracted						_-
centralized						_" 
syllabic							=	(or _=) e.g. n= (or n_=) 
non-syllabic						_^ 
rhoticity						`
									
breathy voiced					_t 
creaky voiced					_k
linguolabial						_N 
labialized						_w 
palatalized						'	(or _j) e.g. t' (or t_j) 
velarized						_G 
pharyngealized					_?\
									
dental							_d 
apical							_a 
laminal							_m
nasalized						~	(or _~) e.g. A~ (or A_~) 
nasal release					_n
lateral release					_l 
no audible release				_}

velarized or pharyngealized		_e 
velarized l, alternatively		5 
raised							_r 
lowered							_o 
advanced tongue root				_A 
retracted tongue root			_q

* * *

<small>This (part of) documentation was generated from [src/fst/phonetics/txt2ipa.xfscript](https://github.com/giellalt/lang-som/blob/main/src/fst/phonetics/txt2ipa.xfscript)</small>

---

# src-fst-phonology-vh.twolc.md 

=================================== !
The Somali VH morphophonological file !
=================================== !

* * *

<small>This (part of) documentation was generated from [src/fst/phonology-vh.twolc](https://github.com/giellalt/lang-som/blob/main/src/fst/phonology-vh.twolc)</small>

---

# src-fst-transcriptions-transcriptor-abbrevs2text.lexc.md 



We describe here how abbreviations are in Somali are read out, e.g.
for text-to-speech systems.

For example:

* s.:syntynyt # ;  
* os.:omaa% sukua # ;  
* v.:vuosi # ;  
* v.:vuonna # ;  
* esim.:esimerkki # ; 
* esim.:esimerkiksi # ; 

* * *

<small>This (part of) documentation was generated from [src/fst/transcriptions/transcriptor-abbrevs2text.lexc](https://github.com/giellalt/lang-som/blob/main/src/fst/transcriptions/transcriptor-abbrevs2text.lexc)</small>

---

# src-fst-transcriptions-transcriptor-numbers-digit2text.lexc.md 



% komma% :,      Root ;
% tjuohkkis% :%. Root ;
% kolon% :%:     Root ;
% sárggis% :%-   Root ; 
% násti% :%*     Root ; 

* * *

<small>This (part of) documentation was generated from [src/fst/transcriptions/transcriptor-numbers-digit2text.lexc](https://github.com/giellalt/lang-som/blob/main/src/fst/transcriptions/transcriptor-numbers-digit2text.lexc)</small>

---

# tools-grammarcheckers-grammarchecker.cg3.md 


[ L A N G U A G E ]  G R A M M A R   C H E C K E R

# DELIMITERS

# TAGS AND SETS

## Tags

This section lists all the tags inherited from the fst, and used as tags
in the syntactic analysis. The next section, **Sets**, contains sets defined
on the basis of the tags listed here, those set names are not visible in the output.

### Beginning and end of sentence
BOS
EOS

### Parts of speech tags

N
A
Adv
V
Pron
CS
CC
CC-CS
Po
Pr
Pcle
Num
Interj
ABBR
ACR
CLB
LEFT
RIGHT
WEB
PPUNCT
PUNCT

COMMA
¶

### Tags for POS sub-categories

Pers
Dem
Interr
Indef
Recipr
Refl
Rel
Coll
NomAg
Prop
Allegro
Arab
Romertall

### Tags for morphosyntactic properties

Nom
Acc
Gen
Ill
Loc
Com
Ess
Ess
Sg
Du
Pl
Cmp/SplitR
Cmp/SgNom Cmp/SgGen
Cmp/SgGen
PxSg1
PxSg2
PxSg3
PxDu1
PxDu2
PxDu3
PxPl1
PxPl2
PxPl3
Px

Comp
Superl
Attr
Ord
Qst
IV
TV
Prt
Prs
Ind
Pot
Cond
Imprt
ImprtII
Sg1
Sg2
Sg3
Du1
Du2
Du3
Pl1
Pl2
Pl3
Inf
ConNeg
Neg
PrfPrc
VGen
PrsPrc
Ger
Sup
Actio
VAbess

Err/Orth

### Semantic tags

Sem/Act
Sem/Ani
Sem/Atr
Sem/Body
Sem/Clth
Sem/Domain
Sem/Feat-phys
Sem/Fem
Sem/Group
Sem/Lang
Sem/Mal
Sem/Measr
Sem/Money
Sem/Obj
Sem/Obj-el
Sem/Org
Sem/Perc-emo
Sem/Plc
Sem/Sign
Sem/State-sick
Sem/Sur
Sem/Time
Sem/Txt

HUMAN

PROP-ATTR
PROP-SUR

TIME-N-SET

###  Syntactic tags

@+FAUXV
@+FMAINV
@-FAUXV
@-FMAINV
@-FSUBJ>
@-F<OBJ
@-FOBJ>
@-FSPRED<OBJ
@-F<ADVL
@-FADVL>
@-F<SPRED
@-F<OPRED
@-FSPRED>
@-FOPRED>
@>ADVL
@ADVL<
@<ADVL
@ADVL>
@ADVL
@HAB>
@<HAB
@>N
@Interj
@N<
@>A
@P<
@>P
@HNOUN
@INTERJ
@>Num
@Pron<
@>Pron
@Num<
@OBJ
@<OBJ
@OBJ>
@OPRED
@<OPRED
@OPRED>
@PCLE
@COMP-CS<
@SPRED
@<SPRED
@SPRED>
@SUBJ
@<SUBJ
@SUBJ>
SUBJ
SPRED
OPRED
@PPRED
@APP
@APP-N<
@APP-Pron<
@APP>Pron
@APP-Num<
@APP-ADVL<
@VOC
@CVP
@CNP
OBJ
<OBJ
OBJ>
<OBJ-OTHERS
OBJ>-OTHERS
SYN-V
@X

## Sets containing sets of lists and tags

This part of the file lists a large number of sets based partly upon the tags defined above, and
partly upon lexemes drawn from the lexicon.
See the sourcefile itself to inspect the sets, what follows here is an overview of the set types.

### Sets for Single-word sets

INITIAL

### Sets for word or not

WORD
NOT-COMMA

### Case sets

ADLVCASE

CASE-AGREEMENT
CASE

NOT-NOM
NOT-GEN
NOT-ACC

### Verb sets

NOT-V

### Sets for finiteness and mood

REAL-NEG

MOOD-V

NOT-PRFPRC

### Sets for person

SG1-V
SG2-V
SG3-V
DU1-V
DU2-V
DU3-V
PL1-V
PL2-V
PL3-V

### Pronoun sets

### Adjectival sets and their complements

### Adverbial sets and their complements

### Sets of elements with common syntactic behaviour

### NP sets defined according to their morphosyntactic features

### The PRE-NP-HEAD family of sets

These sets model noun phrases (NPs). The idea is to first define whatever can
occur in front of the head of the NP, and thereafter negate that with the
expression **WORD - premodifiers**.

### Border sets and their complements

### Grammarchecker sets

* * *

<small>This (part of) documentation was generated from [tools/grammarcheckers/grammarchecker.cg3](https://github.com/giellalt/lang-som/blob/main/tools/grammarcheckers/grammarchecker.cg3)</small>

---

# tools-tokenisers-tokeniser-disamb-gt-desc.pmscript.md 

# Tokeniser for som

Usage:
```
$ make
$ echo "ja, ja" | hfst-tokenise --giella-cg tokeniser-disamb-gt-desc.pmhfst
$ echo "Juos gorreválggain lea (dárbbašlaš) deavdit gáibádusa boasttu olmmoš, man mielde lahtuid." | hfst-tokenise --giella-cg tokeniser-disamb-gt-desc.pmhfst
$ echo "(gáfe) 'ja' ja 3. ja? ц jaja ukjend \"ukjend\"" | hfst-tokenise --giella-cg tokeniser-disamb-gt-desc.pmhfst
$ echo "márffibiillagáffe" | hfst-tokenise --giella-cg tokeniser-disamb-gt-desc.pmhfst
```

Pmatch documentation:
<https://github.com/hfst/hfst/wiki/HfstPmatch>

Characters which have analyses in the lexicon, but can appear without spaces
before/after, that is, with no context conditions, and adjacent to words:
* Punct contains ASCII punctuation marks
* The symbol after m-dash is soft-hyphen `U+00AD`
* The symbol following {•} is byte-order-mark / zero-width no-break space
`U+FEFF`.

Whitespace contains ASCII white space and
the List contains some unicode white space characters
* En Quad U+2000 to Zero-Width Joiner U+200d'
* Narrow No-Break Space U+202F
* Medium Mathematical Space U+205F
* Word joiner U+2060

Apart from what's in our morphology, there are
1. unknown word-like forms, and
2. unmatched strings
We want to give 1) a match, but let 2) be treated specially by
`hfst-tokenise -a`
Unknowns are made of:
* lower-case ASCII
* upper-case ASCII
* select extended latin symbols
ASCII digits
* select symbols
* Combining diacritics as individual symbols,
* various symbols from Private area (probably Microsoft),
so far:
* U+F0B7 for "x in box"

## Unknown handling
Unknowns are tagged ?? and treated specially with `hfst-tokenise`
hfst-tokenise --giella-cg will treat such empty analyses as unknowns, and
remove empty analyses from other readings. Empty readings are also
legal in CG, they get a default baseform equal to the wordform, but
no tag to check, so it's safer to let hfst-tokenise handle them.

Finally we mark as a token any sequence making up a:
* known word in context
* unknown (OOV) token in context
* sequence of word and punctuation
* URL in context

* * *

<small>This (part of) documentation was generated from [tools/tokenisers/tokeniser-disamb-gt-desc.pmscript](https://github.com/giellalt/lang-som/blob/main/tools/tokenisers/tokeniser-disamb-gt-desc.pmscript)</small>

---

# tools-tokenisers-tokeniser-gramcheck-gt-desc.pmscript.md 

# Grammar checker tokenisation for som

Requires a recent version of HFST (3.10.0 / git revision>=3aecdbc)
Then just:
```
$ make
$ echo "ja, ja" | hfst-tokenise --giella-cg tokeniser-disamb-gt-desc.pmhfst
```

More usage examples:
```
$ echo "Juos gorreválggain lea (dárbbašlaš) deavdit gáibádusa boasttu olmmoš, man mielde lahtuid." | hfst-tokenise --giella-cg tokeniser-disamb-gt-desc.pmhfst
$ echo "(gáfe) 'ja' ja 3. ja? ц jaja ukjend \"ukjend\"" | hfst-tokenise --giella-cg tokeniser-disamb-gt-desc.pmhfst
$ echo "márffibiillagáffe" | hfst-tokenise --giella-cg tokeniser-disamb-gt-desc.pmhfst
```

Pmatch documentation:
<https://github.com/hfst/hfst/wiki/HfstPmatch>

Characters which have analyses in the lexicon, but can appear without spaces
before/after, that is, with no context conditions, and adjacent to words:
* Punct contains ASCII punctuation marks
* The symbol after m-dash is soft-hyphen `U+00AD`
* The symbol following {•} is byte-order-mark / zero-width no-break space
`U+FEFF`.

Whitespace contains ASCII white space and
the List contains some unicode white space characters
* En Quad U+2000 to Zero-Width Joiner U+200d'
* Narrow No-Break Space U+202F
* Medium Mathematical Space U+205F
* Word joiner U+2060

Apart from what's in our morphology, there are
1) unknown word-like forms, and
2) unmatched strings
We want to give 1) a match, but let 2) be treated specially by hfst-tokenise -a
* select extended latin symbols
* select symbols
* various symbols from Private area (probably Microsoft),
so far:
* U+F0B7 for "x in box"

TODO: Could use something like this, but built-in's don't include šžđčŋ:

Simply give an empty reading when something is unknown:
hfst-tokenise --giella-cg will treat such empty analyses as unknowns, and
remove empty analyses from other readings. Empty readings are also
legal in CG, they get a default baseform equal to the wordform, but
no tag to check, so it's safer to let hfst-tokenise handle them.

Finally we mark as a token any sequence making up a:
* known word in context
* unknown (OOV) token in context
* sequence of word and punctuation
* URL in context

* * *

<small>This (part of) documentation was generated from [tools/tokenisers/tokeniser-gramcheck-gt-desc.pmscript](https://github.com/giellalt/lang-som/blob/main/tools/tokenisers/tokeniser-gramcheck-gt-desc.pmscript)</small>

---

# tools-tokenisers-tokeniser-tts-cggt-desc.pmscript.md 

# TTS tokenisation for smj

Requires a recent version of HFST (3.10.0 / git revision>=3aecdbc)
Then just:
```sh
make
echo "ja, ja" \
| hfst-tokenise --giella-cg tokeniser-disamb-gt-desc.pmhfst
```

More usage examples:
```sh
echo "Juos gorreválggain lea (dárbbašlaš) deavdit gáibádusa \
boasttu olmmoš, man mielde lahtuid." \
| hfst-tokenise --giella-cg tokeniser-disamb-gt-desc.pmhfst
echo "(gáfe) 'ja' ja 3. ja? ц jaja ukjend \"ukjend\"" \
| hfst-tokenise --giella-cg tokeniser-disamb-gt-desc.pmhfst
echo "márffibiillagáffe" \
| hfst-tokenise --giella-cg tokeniser-disamb-gt-desc.pmhfst
```

Pmatch documentation:
<https://kitwiki.csc.fi/twiki/bin/view/KitWiki/HfstPmatch>

Characters which have analyses in the lexicon, but can appear without spaces
before/after, that is, with no context conditions, and adjacent to words:
* Punct contains ASCII punctuation marks
* The symbol after m-dash is soft-hyphen `U+00AD`
* The symbol following {•} is byte-order-mark / zero-width no-break space
`U+FEFF`.

Whitespace contains ASCII white space and
the List contains some unicode white space characters
* En Quad U+2000 to Zero-Width Joiner U+200d'
* Narrow No-Break Space U+202F
* Medium Mathematical Space U+205F
* Word joiner U+2060

Apart from what's in our morphology, there are
1) unknown word-like forms, and
2) unmatched strings
We want to give 1) a match, but let 2) be treated specially by hfst-tokenise -a
* select extended latin symbols
* select symbols
* various symbols from Private area (probably Microsoft),
so far:
* U+F0B7 for "x in box"

TODO: Could use something like this, but built-in's don't include šžđčŋ:

Simply give an empty reading when something is unknown:
hfst-tokenise --giella-cg will treat such empty analyses as unknowns, and
remove empty analyses from other readings. Empty readings are also
legal in CG, they get a default baseform equal to the wordform, but
no tag to check, so it's safer to let hfst-tokenise handle them.

Needs hfst-tokenise to output things differently depending on the tag they get

* * *

<small>This (part of) documentation was generated from [tools/tokenisers/tokeniser-tts-cggt-desc.pmscript](https://github.com/giellalt/lang-som/blob/main/tools/tokenisers/tokeniser-tts-cggt-desc.pmscript)</small>