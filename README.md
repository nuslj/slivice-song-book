# Slivice-Song-Book
Zpěvník Slivice

## jednotný zpěvník / DB písní k táboráku i pro scholu ##
- formát dat LilyPond (akordy i noty)
- případně https://www.chordpro.org/
- inspirace https://openlilylib.org/tutorials/


## funkce:
- transpozice
- jenom text / text s akordy / noty s textem
- výběr písní pro export (vlstní seznamy / zpěvníky)
- štítkování (vhodné pro, žánr, ...)
- odkazy (nahrávky, ...)

## export do:
* tisk A4 / A5 pdf
* aplikace zpevnik.proscholy.cz (https://github.com/proscholy)
* www.opensong.org (projekce)
* MIDI (přehrávání)
* MusicXML - https://github.com/openlilylib/lilypond-export


## struktura dat:
- co píseň to jeden soubor
- jména souborů (nazev_pisne.ly) místo mezer - nebo _
- 


## WIP - NOTES (prebrat)

ze SW je tu (spíš víc pro sazbu not, ale umí i text s akordy)
LilyPondu nebo MuseScore

případně různé placené co jsem někdy používal (problém s konverzí do něčeho jiného)
Encore
Sibelius (http://www.sibelius.com/download/index.html), 
Finale (free tool https://www.finalemusic.com/products/notepad/)
capella (https://www.capella-software.com/)

další formáty (spíš jako poznámka)
zajímavý souhrn (https://en.wikipedia.org/wiki/List_of_music_software)
https://www.chordpro.org/chordpro/index.html
MusicXML
ABC notation
zajímavá Bakalářka - http://stm.fel.cvut.cz/files/stm_bp/daniel-mikes.pdf
  
nebo naopak vyjít z formátů pro živé promítání na akcích
http://www.opensong.org/
https://straw-solutions.cz/?/uvod
https://openlp.org/

případně vysázení v TeXu
http://zapisnik.glor.cz/sazba-akordu-v-texu.html
viz napr. projekt (více programátorské, ale je to formát textový a dobře editovatelný a generovatelný)
https://github.com/simberaj/zpevnik
z toho by sel udelat klon a drzet to na GITu (sdílený prostor pro editaci kodu/textu ve větším týmu)

mezi textovými (Tex, XML, txt, ...) formáty by melo jít udělat nějakou vhodnou konverzi

z online
http://www.agama2000.cz/
https://www.pisnicky.cz/

za mě bych se kloni k formátu, který půjde použít v opensongu (případně SW tomu podobným)
možná MusicXML
a mít možnost konverze do TeXu a tím pádem vygenerování hezkého pdf.


## LilyPond examples:
```lilypond
\layout {
  indent = 0
  ragged-right = ##t
}

\new Score \with {
  \remove "Bar_number_engraver"
}
<< \chords { c1 g2:7 a:m c1 g2:7 a:m }
   \new Lyrics \with {
 \override VerticalAxisGroup.staff-affinity = ##f
 \override LyricText.parent-alignment-X = #LEFT
 \override LyricText.self-alignment-X = #LEFT
   }
   \lyricmode { This4 and that and sor2 -- row \break
      Come4 back here to -- mor2 -- row }
>>
```
