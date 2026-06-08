BUILD = build
STY   = styles/beamerthemetao.sty

.PHONY: all cn clean

all: slides.pdf

cn: slides_chinese.pdf

$(BUILD):
	mkdir -p $(BUILD)

slides.pdf: slides.tex styles/loadslides.tex $(STY) | $(BUILD)
	xelatex -interaction=nonstopmode -output-directory=$(BUILD) slides
	xelatex -interaction=nonstopmode -output-directory=$(BUILD) slides
	cp $(BUILD)/slides.pdf .

slides_chinese.pdf: slides_chinese.tex styles/loadslides_chinese.tex $(STY) | $(BUILD)
	xelatex -interaction=nonstopmode -output-directory=$(BUILD) slides_chinese
	xelatex -interaction=nonstopmode -output-directory=$(BUILD) slides_chinese
	cp $(BUILD)/slides_chinese.pdf .

clean:
	rm -rf $(BUILD)
	rm -f slides.pdf slides_chinese.pdf missfont.log
