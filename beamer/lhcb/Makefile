
MAIN = main

LATEX = pdflatex
MAINEXT = .pdf
FIGEXT  = .pdf
OUTPUT = $(MAIN)$(MAINEXT)
AUXDIR = aux

BUILDCMD   = $(LATEX) --output-directory=$(AUXDIR) $(MAIN)
BUILDCMD  += && mv -f $(AUXDIR)/$(OUTPUT) $(OUTPUT)

TEXSOURCES = $(wildcard *.tex)
FIGSOURCES = $(wildcard figs/*$(FIGEXT))
SOURCES    = $(TEXSOURCES) $(FIGSOURCES)

(OUTPUT): $(SOURCES) Makefile
	$(BUILDCMD)

all:
	$(BUILDCMD) && $(BUILDCMD) && $(BUILDCMD)

.PHONY: clean
clean:
	rm -f $(AUXDIR)/* $(OUTPUT)

open:
	open $(OUTPUT)
