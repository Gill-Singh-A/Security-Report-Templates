## Makefile for the Comprehensive Code Audit Report template
## Usage: make            (build PDF)
##        make clean      (remove auxiliary files)
##        make distclean  (remove all generated files including PDF)

MAIN = main
LATEX = pdflatex
LATEXFLAGS = -interaction=nonstopmode -shell-escape

.PHONY: all clean distclean

all: $(MAIN).pdf

$(MAIN).pdf: $(MAIN).tex preamble.tex \
	chapters/ch01_executive_summary.tex \
	chapters/ch02_scope_methodology.tex \
	chapters/ch03_example_category_one.tex \
	chapters/ch04_example_category_two.tex \
	chapters/ch05_example_category_three.tex \
	chapters/ch06_dependencies.tex \
	chapters/ch07_remediation_roadmap.tex \
	appendices/app_A_finding_matrix.tex \
	appendices/app_B_evidence_index.tex \
	appendices/app_C_runtime_checklist.tex
	$(LATEX) $(LATEXFLAGS) $(MAIN).tex
	$(LATEX) $(LATEXFLAGS) $(MAIN).tex
	$(LATEX) $(LATEXFLAGS) $(MAIN).tex

clean:
	rm -f $(MAIN).aux $(MAIN).log $(MAIN).out $(MAIN).toc \
	       $(MAIN).lof $(MAIN).lot $(MAIN).lol \
	       chapters/*.aux appendices/*.aux \
	       $(MAIN).bbl $(MAIN).blg \
	       $(MAIN).fdb_latexmk $(MAIN).fls

distclean: clean
	rm -f $(MAIN).pdf
