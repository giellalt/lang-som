## Process this file with automake to produce Makefile.in
## Copyright: Sámediggi/Divvun/UiT
## Licence: GPL v3+

# always build . last here, and tagsets have to be built after morphology
SUBDIRS = morphology filters phonetics syllabification orthography transcriptions tagsets . test

####### Automake targets: ########

# Define target variables first, before assigning to them:
GT_ANALYSERS=
GT_GENERATORS=
CUSTOM_FSTS=

#### Local modifications in *fst processing: ####
####
#### Copy the fallback targets, and rename them to the desired targets. Then:
#### Replace the 'cp' command (Xerox) / Prepend the hfst-invert command (Hfst -
#### remember to move the $<) with whatever you need to complete
#### the processing to get the final target transducer.
#### Remember to add the dependencies as well.
#### Also make sure that HFST and Xerox processing are the same.
####
#### If you add new transducers to be built, you need to add them to the
#### relevant variable, e.g.:
####
#### if CAN_HFST
#### GT_GENERATORS+=generator-oahpa-gt-norm.hfst
#### endif
####
#### NB!!!! The HFST targets should get a hyphen after 'analyser'/'generator'
#### respectively, to make the local targets minimally different from and
#### slightly more specific than the fallback targets. This is to avoid warnings
#### about duplicate targets. That is, the local targets should looke like:
####
#### analyser-%.hfst: analyser-%.tmp.hfst
#### generator-%.hfst: generator-%.tmp.hfst

##################################################################
#### BEGIN: Add local processing instructions BELOW this line ####
##################################################################

########################################################
#### Add language-specific transducer targets here: ####

#### HFST transducers
if CAN_HFST
GT_ANALYSERS+=
GT_GENERATORS+=

if WANT_CUSTOM_FSTS
CUSTOM_FSTS+=
endif # WANT_CUSTOM_FSTS

endif # CAN_HFST

#### FOMA transducers
if CAN_FOMA
GT_ANALYSERS+=
GT_GENERATORS+=

if WANT_CUSTOM_FSTS
CUSTOM_FSTS+=
endif # WANT_CUSTOM_FSTS

endif # CAN_FOMA

#################################################
#### Add language-specific build rules here: ####

# # Copied from SMA. 
# # analyser-%.hfst: analyser-%.tmp.hfst \
# # 				filters/remove-test-tags.hfst
# #	$(AM_V_RGX2FST)$(PRINTF) "\
# #				@\"filters/remove-test-tags.hfst\" \
# #			.o. @\"$<\" \
# #			;" \
# #		| $(HFST_REGEXP2FST) $(HFST_FLAGS) -S --xerox-composition=ON \
# # 	| $(HFST_INVERT) \
# # 	> $@
# 
# analyser-%.xfst: analyser-%.tmp.xfst \
# 				filters/remove-tones.xfst
# 	$(AM_V_GEN)$(PRINTF) "read regex \
# 				@\"filters/remove-tones.xfst\" \
# 			.o. @\"$<\" ;\n\
# 		save stack $@\n\
# 		quit\n" | $(XFST) -q
# 
# # # And also for the generator:
# # generator-%.hfst: generator-%.tmp.hfst \
# # 				filters/remove-test-tags.hfst
# #	$(AM_V_RGX2FST)$(PRINTF) "\
# #				@\"filters/remove-test-tags.hfst\" \
# #			.o. @\"$<\" \
# #			;" \
# #		| $(HFST_REGEXP2FST) $(HFST_FLAGS) -S --xerox-composition=ON \
# # 	> $@
# 
# generator-%.xfst: generator-%.tmp.xfst \
# 				filters/remove-tones.xfst
# 	$(AM_V_GEN)$(PRINTF) "read regex \
# 				@\"$<\" \
# 			.o. @\"filters/remove-tones.xfst\".i \
# 			;\n\
# 		save stack $@\n\
# 		quit\n" | $(XFST) -q
# 

##################################################################
#### END: Add local processing instructions ABOVE this line ######
##################################################################

include $(top_srcdir)/../giella-core/am-shared/src-fst-dir-include.am
include $(top_srcdir)/../giella-core/am-shared/devtest-include.am
