## Process this file with automake to produce Makefile.in

## Copyright (C) 2011 Samediggi

## This program is free software: you can redistribute it and/or modify
## it under the terms of the GNU General Public License as published by
## the Free Software Foundation, either version 3 of the License, or
## (at your option) any later version.

## This program is distributed in the hope that it will be useful,
## but WITHOUT ANY WARRANTY; without even the implied warranty of
## MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
## GNU General Public License for more details.

## You should have received a copy of the GNU General Public License
## along with this program.  If not, see <http://www.gnu.org/licenses/>.

GT_FILTER_TARGETS=

# List any local additions here:
GT_FILTER_LOCAL_SRCS=\
			   remove-tones.regex \
			   remove-declension-tags.regex \
			   make-optional-tags-and-tones.regex

# Add the target of local additions here:
# HFST targets here:
if CAN_HFST
GT_FILTER_TARGETS+=remove-tones.hfst \
				   remove-declension-tags.hfst \
				   make-optional-tags-and-tones.hfst

endif

# And Xerox targets here:
if CAN_XFST
GT_FILTER_TARGETS+=remove-tones.xfst \
				   remove-declension-tags.xfst \
				   make-optional-tags-and-tones.xfst

endif

include $(top_srcdir)/am-shared/src-filters-dir-include.am

# vim: set ft=automake:
