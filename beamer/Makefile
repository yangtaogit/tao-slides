BUILD = build
STY   = styles/beamerthemeelegant.sty

.PHONY: all cn clean

all: slides.pdf

cn: slides_CN.pdf

$(BUILD):
	mkdir -p $(BUILD)

slides.pdf: slides.tex loadslides.tex references.bib $(STY) | $(BUILD)
	pdflatex -interaction=nonstopmode -output-directory=$(BUILD) slides
	biber $(BUILD)/slides
	pdflatex -interaction=nonstopmode -output-directory=$(BUILD) slides
	pdflatex -interaction=nonstopmode -output-directory=$(BUILD) slides
	cp $(BUILD)/slides.pdf .

slides_CN.pdf: slides_CN.tex loadslides_CN.tex references.bib $(STY) | $(BUILD)
	xelatex -interaction=nonstopmode -output-directory=$(BUILD) slides_CN
	biber $(BUILD)/slides_CN
	xelatex -interaction=nonstopmode -output-directory=$(BUILD) slides_CN
	xelatex -interaction=nonstopmode -output-directory=$(BUILD) slides_CN
	cp $(BUILD)/slides_CN.pdf .

clean:
	rm -rf $(BUILD)
	rm -f slides.pdf slides_CN.pdf missfont.log
