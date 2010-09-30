# This is a makefile that builds the Somali morphological parser
# *****************************************************************
# This is a dummy file. SOM refers to the name of the language, som to the 
# ISO code of the language, for use in file names.

# This is a preliminary file that builds a SOM parser based upon
# xfst and not twolc.

# Here we build the final generator , an inverted transducer of the analyzer.
# It is dependent upon som.save

isom.fst: ../bin/isom.fst
../bin/isom.fst: ../bin/som.fst
	@echo
	@echo "*** Building the inverse isom.fst ***"
	@echo
	@printf "load ../bin/som.save \n\
	invert net \n\
	save stack ../bin/isom.fst \n\
	quit \n" > ../../tmp/isom-fst-script
	@xfst < ../../tmp/isom-fst-script
	@rm -f ../../tmp/isom-fst-script


# This goal is to build the final analyser. It depends on all the files.

som.fst: ../bin/som.fst
../bin/som.fst: ../bin/som.save ../bin/caseconv.fst ../bin/tok.fst 
	@echo
	@echo "*** Building som.fst ***" ;
	@echo
	@printf "read regex [[@\"../bin/som.save\"] .o. \
	[@\"../bin/caseconv.fst\"]] ; \n\
	save stack ../bin/som.fst \n\
	quit \n" > ../../tmp/som-fst-script
	@xfst < ../../tmp/som-fst-script
	@rm -f ../../tmp/som-fst-script


# The second goal is to build the caseconv.fst file
# This goal depends on case.regex

caseconv.fst: ../bin/caseconv.fst
../bin/caseconv.fst: case.regex
	@echo
	@echo "*** Building caseconv.fst ***" ;
	@echo
	@printf "read regex < case.regex \n\
	save stack ../bin/caseconv.fst \n\
	quit \n" > ../../tmp/caseconv-script
	@xfst < ../../tmp/caseconv-script
	@rm -f ../../tmp/caseconv-script


# Another goal is to build a preprocessor.This goal depends on tok.txt

tok.fst: ../bin/tok.fst
../bin/tok.fst: tok.txt
	@echo
	@echo "*** Building the tokenizer tok.fst ***" ;
	@echo
	@printf "source tok.txt \n\
	save stack ../bin/tok.fst \n\
	quit \n" > ../../tmp/tok-script
	@xfst < ../../tmp/tok-script
	@rm -f ../../tmp/tok-script


som.save: ../bin/som.save
../bin/som.save: ../bin/xfst-som.bin ../bin/som-lex.save
	@echo
	@echo "*** Building the parser som.save ***"
	@echo
	@printf "read regex [[@\"../bin/som-lex.save\"] .o. \
	[@\"../bin/xfst-som.bin\"]] ; \n\
	save stack ../bin/som.save \n\
	quit \n" > ../../tmp/som-save-script
	@xfst < ../../tmp/som-save-script
	@rm -f ../../tmp/som-save-script

# The first goal is to build som-lex.save
# This goal depends on a bunch of lexicon files

som-lex.save: ../bin/som-lex.save
../bin/som-lex.save: som-lex.txt noun-som-morph.txt noun-som-lex.txt \
        adj-som-lex.txt \
	adv-som-lex.txt verb-som-lex.txt pron-som-lex.txt punct-som-lex.txt \
	pp-som-lex.txt
	@echo
	@echo "*** Building som-lex.save ***" ;
	@echo
	printf "compile-source som-lex.txt noun-som-morph.txt noun-som-lex.txt \
	adj-som-lex.txt verb-som-lex.txt verb-som-morph.txt pron-som-lex.txt \
	adv-som-lex.txt pp-som-lex.txt punct-som-lex.txt \n\
	save-source ../bin/som-lex.save \n\
	quit \n" > ../../tmp/som-lex-save-script
	@lexc < ../../tmp/som-lex-save-script
	rm -f ../../tmp/som-lex-save-script

# The second goal is to build xfst-som.bin
# This goal depends on xfst-som.txt

xfst-som.bin: ../bin/xfst-som.bin
../bin/xfst-som.bin: xfst-som.txt
	@echo
	@echo "*** Building xfst-som.bin ***" ;
	@echo
	@printf "source xfst-som.txt \n\
	save stack ../bin/xfst-som.bin \n\
	quit \n" > ../../tmp/xfst-som-script
	@xfst < ../../tmp/xfst-som-script
	@rm -f ../../tmp/xfst-som-script

clean:
	@rm -f ../bin/*.bin ../bin/*.fst ../bin/*.save


