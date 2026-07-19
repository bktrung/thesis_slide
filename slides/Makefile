MAIN = main

.PHONY: all clean view

all:
	latexmk -pdf -interaction=nonstopmode -halt-on-error $(MAIN).tex

clean:
	latexmk -C
	rm -f *.nav *.snm *.vrb *.bbl *.blg

view: all
	xdg-open $(MAIN).pdf
