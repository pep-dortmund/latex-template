TEXOPTS= --lualatex \
	 --output-directory=build \
	 --interaction=nonstopmode \
	 --halt-on-error

TARGETS=soak_anmeldung \
	bescheinigung \
	brief \
	mitgliedsantrag \
	mitgliedsantrag_a5 \
	stipendium_antrag \
	stipendium_aushang \
	stipendium_initiativ \
	stipendium_initiativ_vertrag \
	mindstorms_ausleihe \
	goingabroad/purdue/purdue_brief_absage \
	goingabroad/purdue/purdue_brief_zusage \
	goingabroad/purdue/purdue_anleitung \
	satzung/gebuehrenordnung \
	satzung/satzung

all: $(addprefix build/, $(addsuffix .pdf, $(TARGETS)))

build/%.pdf: %.tex FORCE | build
	TEXINPUTS=../logos:..: latexmk $(TEXOPTS) $<

FORCE:

build:
	mkdir -p build

clean:
	rm -r build

.PHONY: all clean FORCE
