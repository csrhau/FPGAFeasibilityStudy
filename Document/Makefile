FIG_DIR = figures
PLT_DIR = plots
TAB_DIR = tables
TEX_DIR = tex

FIG_SRCS = $(wildcard $(FIG_DIR)/*.tex)
FIG_PDFS = $(FIG_SRCS:$(FIG_DIR)/%.tex=%.pdf)

PLT_SRCS = $(wildcard $(PLT_DIR)/*.tex)
PLT_PDFS = $(PLT_SRCS:$(PLT_DIR)/%.tex=%.pdf)

TAB_SRCS = $(wildcard $(TAB_DIR)/*.tex)
TAB_PDFS = $(TAB_SRCS:$(TAB_DIR)/%.tex=%.pdf)

.DEFAULT: all
.PHONY: all
all: paper figures plots tables 

.PHONY: figures
figures: $(FIG_PDFS)

.PHONY: plots
plots: $(PLT_PDFS)

.PHONY: tables
tables: $(TAB_PDFS)

.PHONY: paper
paper: paper.pdf

# Depending on a phony target forces this rule to run.
# We are delegating dependency monitoring to latexmk.
.PHONY: ALWAYS
%.pdf: */%.tex ALWAYS
	latexmk -f -pdf $<

.PHONY: tidy
tidy:
	latexmk -c $(TEX_DIR)/paper.tex $(FIG_SRCS) $(PLT_SRCS) $(TAB_SRCS)
	rm -f *.bbl

.PHONY: clean
clean: tidy
	latexmk -C $(TEX_DIR)/paper.tex $(FIG_SRCS) $(PLT_SRCS) $(TAB_SRCS)
	rm -f *.fls
