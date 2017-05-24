SVG=$(wildcard *.svg)
PDFS=$(SVG:.svg=.pdf_tex)
PSS=$(SVG:.svg=.ps_tex)
DIRECTORY=svg

%.pdf_tex: %.svg
	@inkscape -D -z --file=$(@:.pdf_tex=.svg) --export-pdf=$(@:.pdf_tex=.pdf) --export-latex
	@inkscape -D -z --file=$(@:.pdf_tex=.svg) --export-pdf=$(@:.pdf_tex=_raw.pdf) 
%.ps_tex: %.svg
	@inkscape -D -z --file=$(@:.ps_tex=.svg) --export-ps=$(@:.ps_tex=.ps) --export-latex
all: $(PDFS) 
clean:
	@rm -f *.ps
	@rm -f *.ps_tex
	@rm -f *.pdf
	@rm -f *.pdf_tex
	@rm -f *~
	@rm -f *.bak
