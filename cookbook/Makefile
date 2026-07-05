# Makefile for LaTeX cookbook

# Source files
MAIN_TEX := recette.tex
PDF_OUTPUT := $(MAIN_TEX:.tex=.pdf)

# LaTeX compiler
PDFLATEX := pdflatex -interaction=nonstopmode -synctex=1

.PHONY: all build clean cleanall view help

# Default target
all: build

# Build PDF (with multiple passes for table of contents)
build: $(PDF_OUTPUT)

$(PDF_OUTPUT): $(MAIN_TEX)
	$(PDFLATEX) $<
	$(PDFLATEX) $<

# View PDF
view: $(PDF_OUTPUT)
	xdg-open $(PDF_OUTPUT) &

# Clean auxiliary files
clean:
	rm -f *.aux *.log *.out *.toc *.lof *.lot *.fls *.fdb_latexmk *.synctex.gz *.bbl *.blg *.bcf

# Remove all generated files
cleanall: clean
	rm -f $(PDF_OUTPUT)

# Help
help:
	@echo "LaTeX Cookbook Makefile targets:"
	@echo "  make build     - Compile LaTeX to PDF"
	@echo "  make view      - Compile and open PDF"
	@echo "  make clean     - Remove auxiliary files"
	@echo "  make cleanall  - Remove all generated files including PDF"
	@echo "  make help      - Show this help message"
