TEXOPTS= --lualatex \
	 --output-directory=build \
	 --interaction=nonstopmode \
	 --halt-on-error

TARGETS=Bestaetigung_Unternehmen \
	Rechnung_Unternehmen \
	Angebot_Unternehmen \
	Handzettel_00_Unternehmen \
	Handzettel_01_Ablauf \
	Handzettel_02_Anfahrtsskizze \
	Handzettel_03_Messeplan

all: $(addprefix build/, $(addsuffix .pdf, $(TARGETS)))

build/%.pdf: %.tex | build
	TEXINPUTS=../logos:..: latexmk $(TEXOPTS) $<

build:
	mkdir -p build

clean:
	rm -r build

.PHONY: all clean
