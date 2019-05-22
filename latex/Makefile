1: all
all : main.pdf view github
#all : main.pdf view
main.pdf : 
#	bibtex hyphy2.5
	latex -halt-on-error hyphy2.5.tex
	dvipdfm hyphy2.5.dvi
view :
	open -a Preview hyphy2.5.pdf -g
github:
	git commit -a -m "`whoami` edit"
	git push origin master
