main = report

all: once.a

%.eps:
	dot -Teps -o $@ $(patsubst %.eps,%.dot,$@)

graphs: sections/data/trakt.eps

once.%: graphs
	pdflatex $(main)

bibtex: once.a
	bibtex $(main)

cleangraphs:
	rm -f sections/*/*.eps

clean: cleangraphs
	rm -f $(main).{aux,log,toc,out,bbl,blg}

remove: clean
	rm -f $(main).pdf

release: remove bibtex once.b once.c
