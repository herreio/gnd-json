# Zugänge zur GND im JSON-Format

## Testdaten: Johann Justinus Gebauer

- GND-Nummer: 116473207
    - [d-nb.info/gnd](http://d-nb.info/gnd/116473207)
        - [MARC21-XML](http://d-nb.info/gnd/116473207/about/marcxml)
    - [lobid.org/gnd](http://lobid.org/gnd/116473207)
        - [JSON-LD](http://lobid.org/gnd/116473207.json)
    - [portal.dnb.de/metadataShop](https://portal.dnb.de/metadataShop.htm)
        - [JSON-LD](./data/116473207_datenshop.json) (DNB-Konto benötigt!)
    - [services.dnb.de/sru/authorities](http://services.dnb.de/sru/authorities)
        - [MARC21-XML](http://services.dnb.de/sru/authorities?version=1.1&operation=searchRetrieve&query=dnb.nid=116473207&recordSchema=MARC21-xml&maximumRecords=1&accessToken=YOUR_ACCESS_TOKEN) (DNB-Konto und `accessToken` benötigt!)
- OGND-PPN: 134663063
    - [PICA-Datenbank](https://swb.bsz-bw.de/DB=2.104/PPNSET?PPN=134663063&INDEXSET=21)
        - [MARCJSON](http://unapi.gbv.de/?id=ognd:ppn:134663063&format=marcjson)
        - [PICAJSON](http://unapi.gbv.de/?id=ognd:ppn:134663063&format=picajson)

## Zugangsschlüssel

Für den Zugriff auf die von der _Deutschen Nationalbibliothek_ bereitgestellte SRU-Schnittstelle der _Gemeinsamen Normdatei_ wird ein `accessToken` benötigt. Die entsprechende Routine zur Bereitstellung erwartet diesen in der Umgebungsvariable `DNB_TOKEN`.

Im hiesigen Fall wurde ein in der Git-Umgebung ignoriertes, `secret` betiteltes Skript mit folgendem Inhalt erstellt:

```sh
export DNB_TOKEN='YOUR_ACCESS_TOKEN'
```

... und vor Ausführung der Routine [`utils/conv`](./utils/conv) geladen:

```sh
source secret
```

## Verwendete Kommandozeilenprogramme

- [dojson](https://github.com/inveniosoftware/dojson)
- [catmandu](https://librecat.org/Catmandu/)
- [pymarc2jsonl](https://github.com/slub/pymarc2jsonl)
- [yaz-marcdump](https://software.indexdata.com/yaz/doc/yaz-marcdump.html)
