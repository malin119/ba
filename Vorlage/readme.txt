Die eingebundene Vorlage verwendet Biber (https://en.wikipedia.org/wiki/Biber_(LaTeX)) anstelle von BibTeX.


===========================================
Um das Kompilieren so einfach wie möglich zu machen, bietet sich ein entsprechender Dockercontainer (https://en.wikipedia.org/wiki/Docker_(software)) an. Dies ist optional und Sie müssen den Docker nicht zum kompilieren verwenden. Durch den Dockercontainer wird bei jedem Speichern einer der Quelldateien das PDF neu erstellt.

1) Docker installieren, siehe https://docs.docker.com/install/
2) git clone https://github.com/Liebeck/docker.git
3) cd dockerlatex/
4) docker build -t dockerlatex .
5) Pfad zu Ihrer Haupt-LaTeX-Datei (d.h. der Order in dem die ba.tex liegt) im folgenden Befehl anpassen:
docker run -it --rm=true -v ~/Documents/bathesis:/tex dockerlatex latexmk -pvc -bibtex -view=none -quiet -pdf ba.tex

Um die Fehler beim Kompilieren besser zu verstehen, bietet es sich an, dass das -quiet Flag entfernt wird:
docker run -it --rm=true -v ~/Documents/bathesis:/tex dockerlatex latexmk -pvc -bibtex -view=none -pdf ba.tex


Als PDF-Viewer mit autorefresh bietet sich Okular an.