LATEX = pdflatex
MAIN = main
COVER=cover_form.pdf
LETTERS_CO=../letters_CO/all_CO.pdf
LETTERS_DE=../letters_DE/all_DE.pdf
FINAL=20130430_StudyTripApplication_ForeroRomero.pdf

all: $(MAIN).pdf $(LETTERS_CO) $(LETTERS_DE)
	pdftk A=$(COVER) B=$(MAIN).pdf C=$(LETTERS_DE) D=$(LETTERS_CO) cat A B1-6 C B7 D output $(FINAL)

$(LETTERS_CO):
	pdftk ../letters_CO/*_Winter*pdf cat output $(LETTERS_CO)

$(LETTERS_DE):
	pdftk ../letters_DE/*_Winter*pdf cat output $(LETTERS_DE)

$(MAIN).pdf: $(MAIN).tex 
	$(LATEX) $(MAIN).tex
	$(LATEX) $(MAIN).tex

clean:
	rm -f $(MAIN).{aux,bbl,ps,pdf,div,blg,log}
	rm -f $(MAIN).pdf $(FINAL)
	rm -f *~
	rm -f $(LETTERS_CO)
	rm -f $(LETTERS_DE)

view:
	open $(MAIN).pdf &


