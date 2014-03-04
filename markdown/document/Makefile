
INPUT=plan
OUTEXT=.pdf

TEMPLATE=mdtemplate.tex

paper=a4paper
hmargin=2cm
vmargin=2.5cm
fontsize=11pt

#mainfont="Helvetica Light"
mainfont="Helvetica"
sansfont="Verdana"
monofont="Courier New"

nohyphenation=false
columns=onecolumn
geometry=portrait


MDS=$(wildcard *.md)
NAMES=$(subst .md,,$(MDS))
PDFS=$(subst .md,$(OUTEXT),$(MDS))


%$(OUTEXT): %.md
	pandoc -s --latex-engine=xelatex --template=$(TEMPLATE) \
	-V paper=$(paper) -V hmargin=$(hmargin) -V vmargin=$(vmargin) \
	-V mainfont=$(mainfont) -V sansfont=$(sansfont) -V monofont=$(monofont) \
	-V geometry=$(geometry) -V alignment=$(alignment) -V columns=$(columns) \
	-V fontsize=$(fontsize) -V nohyphenation=$(nohyphenation) \
	-o $@ $^

all: $(PDFS)
#-V toc=$(toc) \
#$@

.PHONY : clean info

clean:
	rm -f $(PDFS)

info:
	@echo $(MDS)
	@echo $(PDFS)
	@echo $(NAMES)

