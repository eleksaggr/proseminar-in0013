DOCS=talk.tex
PDFS=$(DOCS:.tex=.pdf)

all: $(PDFS)
fig:
	@$(MAKE) -C svg all
$(PDFS): %.pdf : %.tex fig
	@latexmk -shell-escape -g -recorder -use-make -bibtex -pdf -deps -deps-out=$<.deps $<
deltemp:
	@rm *~
clean:
	#@$(MAKE) -C figs clean
	@$(MAKE) -C svg clean
	@rm -rf _minted-$(DOCS:.tex=)
	@rm -f $(talk.[^tex][^bib]*)
	@rm -f *~
	@rm -f *.backup *.aux
	@rm -f texput.log $(DOCS:.tex=.toc) $(DOCS:.tex=.fdb_latexmk) $(DOCS:.tex=.fls) $(DOCS:.tex=.vrb) $(DOCS:.tex=.tpt) $(DOCS:.tex=.dvi) $(DOCS:.tex=.blg) $(DOCS:.tex=.bbl) $(DOCS:.tex=.tex.flc) $(DOCS:.tex=.log) $(DOCS:.tex=.aux) $(DOCS:.tex=.nav) $(DOCS:.tex=.out) $(DOCS:.tex=.snm) $(DOCS:.tex=.pdf)
