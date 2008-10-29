.SILENT:
.SUFFIXES:
.SUFFIXES: .txt .html .eom
T=./tmp
S=
SRC=index design todo proc
TPL=$(SRC:=.tpl)
TXT=$(TPL:tpl=txt)
.PRECIOUS: $(TXT)
HTML=$(TXT:txt=html)
echo:
	echo 'TPL' $(TPL)
	echo 'HTML' $(HTML)
test:
clean:
	rm -f *.html
	rm -f *.txt
	rm -f *~
aclean:	clean
	rm -f *.sym
$T.sym:	$(TPL)
	sym -s $T $(TPL)
all:	$(HTML)
%.html: %.txt
	eom asciit $< | asciidoc - > $@
%.txt: %.eom

