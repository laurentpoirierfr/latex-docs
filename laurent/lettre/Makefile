# Makefile for LaTeX documents

# Source files
MAIN_TEX := motivation.tex
PDF_OUTPUT := $(MAIN_TEX:.tex=.pdf)

# LaTeX compiler
PDFLATEX := pdflatex -interaction=nonstopmode -synctex=1
BIBTEX := bibtex

.PHONY: all build clean view help

# Default target
all: build

# Build PDF (with multiple passes for references)
build: $(PDF_OUTPUT)

$(PDF_OUTPUT): $(MAIN_TEX)
	$(PDFLATEX) $<
	$(PDFLATEX) $<

# View PDF
view: $(PDF_OUTPUT)
	xdg-open $(PDF_OUTPUT) &

# Clean auxiliary files
clean:
	rm -f *.aux *.log *.out *.tns *.fls *.fdb_latexmk *.synctex.gz *.bbl *.blg *.bcf *.toc

# Remove all generated files
cleanall: clean
	rm -f $(PDF_OUTPUT)

# Help
help:
	@echo "LaTeX Makefile targets:"
	@echo "  make build     - Compile LaTeX to PDF"
	@echo "  make view      - Compile and open PDF"
	@echo "  make clean     - Remove auxiliary files"
	@echo "  make cleanall  - Remove all generated files including PDF"
	@echo "  make help      - Show this help message"

