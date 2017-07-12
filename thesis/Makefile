# vim: noexpandtab

LATEX=latexmk
CONVERT=inkscape

SVGS=
DOCS=seminarpaper.tex

PICS=$(SVGS:.svg=.pdf)
PDFS=$(DOCS:.tex=.pdf)

all: svgs_old $(PICS) $(PDFS)

$(PICS): %.pdf : %.svg
	$(CONVERT) --file=$< --export-pdf=$@

-include ${PDFS:.pdf=.tex.deps}
$(PDFS): %.pdf : %.tex $(PICS)
	$(LATEX) -shell-escape -g -recorder -use-make -bibtex -pdf -deps -deps-out=$<.deps $<

svgs_old:
	$(MAKE) -C svg/

$(DOCS:.tex=).aex:
	touch --date=800101 $@

$(DOCS:.tex=).out.pyg:
	touch --date=800101 $@

$(DOCS:.tex=).pyg:
	touch --date=800101 $@

$(DOCS:.tex=).w18:
	touch --date=800101 $@

clean:
	rm -rf $(PICS) $(PDFS) $(DOCS:.tex=.aux) $(DOCS:.tex=.bbl) $(DOCS:.tex=.blg) $(DOCS:.tex=.log) $(DOCS:=.deps) $(DOCS:.tex=.fdb_latexmk) $(DOCS:.tex=.pyg) $(DOCS:.tex=.fls) $(DOCS:.tex=.out) $(DOCS:.tex=.out.pyg) $(DOCS:.tex=.w18) $(DOCS:.tex=.aex) _minted-*
	$(MAKE) -C svg/ clean
