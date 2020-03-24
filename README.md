# Augsburgliebe.de

Hier ist der Quellcode zur Homepage www.augsburgliebe.de - eine Website zur
Koordination von Nachbarschaftshilfe während der Corona-Pandemie.

## Übersicht

* [Jekyll](https://jekyllrb.com/) baut aus dem Quellcode die Website (Static renderer)
* [Now](https://github.com/apps/now) führt das automatische Bauen durch (CI/CD)

## Quickstart - Redaktionelles

* Du brauchst dazu einen GitHub-Account - [hier klicken zum Registrieren](https://github.com/join?source=header-home).
* Um eine Seite zu bearbeiten, such sie Dir unten in der Liste der Dateien raus
* Klicke dann rechts oben auf das Stift-Icon. Du kannst die Datei dann bearbeiten
  und Deine Änderungen einreichen. Mach erst Deine Änderungen und fülle dann unten
  die Überschrift Deiner Änderungen und ggf. eine längere Beschreibung aus, falls
  Du dazu etwas erklären willst.
* Klicke dann unten auf *Propose changes*.

Du arbeitest da im Hintergrund mit einer *Kopie* der Website. Du kannst also nichts
kaputt machen. Deine Änderungen werden vor Übernahme auf die Seite erst noch
genehmigt - nicht aus autoritären Gründen sondern aus technischen. So funktioniert
GitHub. Alle arbeiten an ihren eigenen Kopien und die von *Debakel* ist eben diejenige,
die man auch im Internet sieht.

[Hier gibt es eine Anleitung für Formattierung und so](https://guides.github.com/features/mastering-markdown/).

## Quickstart - Entwicklung

Grundvoraussetzungen:

* Du brauchst Ruby und am besten `rbenv`, damit Du Gems (Bibliotheken) installieren kannst.

* [rbenv](https://github.com/rbenv/rbenv)
* [ruby-build](https://github.com/rbenv/ruby-build) sollte man als Plugin für `rbenv` installieren.
* Installiere z.B. Ruby `2.7.0`: `rbenv install 2.7.0`
* Installiere `bundler`: `gem install bundler`

Voraussetzungen für das Repo:

* Im [Original-Repository](https://github.com/Debakel/corona-soli-augsburg) rechts oben auf *Fork* klicken
* Eigenes Repo auschecken: `git clone https://github.com/$USER/corona-soli-augsburg`
* Abhängigkeiten installieren: `cd corona-soli-augsburg; bundler`

Jetzt kannst Du am Repostiry arbeiten. Um Dir die Seite auf Deinem Computer
anzusehen, kannst Du den mitgelieferten Server starten, der bei jedem Mal
abspeichern die Änderungen direkt einbaut:

```shell
bundle exec jekyll serve
Configuration file: /home/florian/dev/websites/corona-soli-augsburg/_config.yml
  Source: /home/florian/dev/websites/corona-soli-augsburg
  Destination: /home/florian/dev/websites/corona-soli-augsburg/_site
  Incremental build: disabled. Enable with --incremental
  Generating...
       Jekyll Feed: Generating feed for posts
                    done in 0.165 seconds.
 Auto-regeneration: enabled for '/home/florian/dev/websites/corona-soli-augsburg'
    Server address: http://127.0.0.1:4000/
  Server running... press ctrl-c to stop.
```

Wenn Du diese Meldung siehst, [kannst Du hier klicken um die Seite bei Dir
am PC anzusehen](http://127.0.0.1:4000/). Wenn Du fertig bist, kannst Du `STRG=C`
drücken, um den Server zu beenden.

## Empfohlene Entwicklungsmethode

Ich empfehle, dass Du Deine Änderungen dann wie folgt einreichst:

1. Mache einen neuen Branch in Deinem Repository: `git branch rechtschreibkontrolle_klingonisch`
2. Sammle Deine Änderungen zusammen - fasse dabei zusammengehörige Änderungen
   am besten zusammen und mach für verschiedene Themen verschiedene Commits:
   
   `git add -p; git commit -m 'Kommas korrigiert'`
3. Lade Deine Änderungen in Dein eigenes Repository hoch: `git push origin rechtschreibkontrolle_klingonisch`
4. Dabei kommt dann auch eine URL, mit der Du den Pull-Request gegen das Haupt-Repo einreichen kannst:

```git
remote: Create a pull request for 'readme' on GitHub by visiting:
remote:   https://github.com/fheinle/corona-soli-augsburg/pull/new/rechtschreibkontrolle_klingonisch
```

Auf diesen Link kannst Du dann klicken. Geh sicher, dass unter *Base repository* steht `Debakel/corona-soli-augsburg` und `base: master`.

## Details


### Neue Unterseiten anlegen

Für eine neue Unterseite erstelst Du einfach eine neue Datei im Verzeichnis des
Repositories und benennst sie `NameDerUnterseite.markdown`. Die Datei ist dann
einfach der Inhalt im [Markdown-Format zur
Formattierung](https://guides.github.com/features/mastering-markdown/).

Du solltest auch ein paar Metadaten angeben. Dazu nutzt man
[YAML-Front_Matter](https://jekyllrb.com/docs/front-matter/). Ein minimales Beispiel
sieht so aus:

```markdown
---
permalink: /klingonisch
layout: home
---
```

### Neue Punkte in die Navigation aufnehmen

Jekyll wird automatisch einen Eintrag in der Navigationsleiste einfügen, wenn Du
Deiner Markdown-Datei im [YAML-Front-Matter](https://jekyllrb.com/docs/front-matter/)
einen `title: Blafasel` hinzufügst.
