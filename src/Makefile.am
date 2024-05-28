## Process this file with automake to produce Makefile.in
## Copyright: Sámediggi/Divvun/UiT
## Licence: GPL v3+

SUBDIRS = fst cg3

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
# 		 save stack $@\n\
# 		 quit\n" | $(XFST) -q
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
# 		 save stack $@\n\
# 		 quit\n" | $(XFST) -q
# 
##################################################################
#### END: Add local processing instructions ABOVE this line ######
##################################################################

include $(top_srcdir)/../giella-core/am-shared/src-dir-include.am
include $(top_srcdir)/../giella-core/am-shared/devtest-include.am
