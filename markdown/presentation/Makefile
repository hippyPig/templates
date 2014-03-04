

THEME = scph-lhcb
OUTEXT = .pdf
MDS=$(wildcard *.md)
NAMES=$(subst .md,,$(MDS))
PDFS=$(subst .md,$(OUTEXT),$(MDS))

#all:
all: $(PDFS)


%$(OUTEXT): %.md
	pandoc -f markdown -t beamer -V theme:$(THEME) -o $@ $^

#pandoc -f markdown  -t beamer $^ -V theme:$(THEME) -o $@ $^
#pandoc -s --latex-engine=xelatex --template=$(TEMPLATE) \
#-V paper=$(paper) -V hmargin=$(hmargin) -V vmargin=$(vmargin) \
#-V mainfont=$(mainfont) -V sansfont=$(sansfont) -V monofont=$(monofont) \
#-V geometry=$(geometry) -V alignment=$(alignment) -V columns=$(columns) \
#-V fontsize=$(fontsize) -V nohyphenation=$(nohyphenation) \
#-o $@ $^

.PHONY: clean

clean:
	rm -f $(PDFS)

