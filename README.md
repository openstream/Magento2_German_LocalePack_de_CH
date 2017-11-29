# Magento 2 German LocalePack de_CH

Basierend auf dem deutschen Sprachpaket für Magento 2 Community Edition

Die Übersetzung wurde von deutschen Muttersprachlern nach eigenem Ermessen vorgenommen. Die Übersetzung ist komplett, d.h. alle Sprachausgaben von Magento 2 wurden vom Englischen ins Deutsche übersetzt. Gern können Änderungsvorschläge eingebracht oder auch das gesamte Repository geforkt werden, wenn abweichende Übersetzungen eingebracht werden sollen.

Es gibt hier https://crowdin.com/project/magento-2/de auch einen Ansatz für die deutsche Übersetzung, aber das ist noch nicht weit fortgeschritten. 
Und für Magento 1.x gibt es weiterhin das deutsche Sprachpaket von Rico Neitzel: https://github.com/riconeitzel/German_LocalePack_de_DE

# Installation
 - Alle Dateien nach `/app/i18n/openstream/de_CH/` kopieren

Aus dem Magento-Root-Verzeichnis folgende Befehle aufrufen:
```bash
rm pub/static/frontend/Magento/luma/de_CH/js-translation.json
php bin/magento setup:static-content:deploy de_CH
php bin/magento setup:upgrade
rm -rf var/di
php bin/magento setup:di:compile
```

# Installation mit Composer
```bash
composer require openstream/mage2-locale-de-ch
rm pub/static/frontend/Magento/luma/de_CH/js-translation.json
php bin/magento setup:static-content:deploy de_CH
```

# Unterschiede de_DE und de_CH
* ss statt ß
* Region/Bundesland/Kanton statt Region/Bundesland

# Aktualisieren vom Upstream
Sicher stellen, dass der upstream remote korrekt konfiguriert ist, sollte so aussehen:
```bash
$ git remote -v
origin	git@github.com:openstream/Magento2_German_LocalePack_de_CH.git (fetch)
origin	git@github.com:openstream/Magento2_German_LocalePack_de_CH.git (push)
upstream	git@github.com:splendidinternet/Magento2_German_LocalePack_de_DE.git (fetch)
upstream	git@github.com:splendidinternet/Magento2_German_LocalePack_de_DE.git (push)
```
Dann folgende Befehle ausführen:
```bash
git fetch upstream
git merge upstream/master
```
Wenn nötig müssen Konflikte behoben werden bevor man pushen kann.

Nicht vergessen die neuen Tags vom upstream zu holen und auch mit zu pushen, sonst gibt's Probleme mit der Composer-Versionierung!
```bash
git pull origin master --tags
git push --tags
```

# Add new phrases

To translate new phrases follow these steps:

### Get phrases from Magento

Run this in your Magento 2 installation:

```bash
php bin/magento i18n:collect-phrases -m > phrases.csv
```

### Compare phrases with old translation file

Copy the `phrases.csv` into this repository and run:

```bash
php check_new.php
```

This will output a new file `de_DE_new.csv` which only contains the
phrases that are not yet translated in `de_DE.csv`.

### Translate phrases

Now you should translate these phrases. Enter the translated phrase
in the *second* column.

### Copy new phrases and create a pull request

Copy the new phrases to `de_DE.csv`.

**IMPORTANT**: sort the file alphabetically based on the first column, e.g. with LibreOffice.

Now create a [new pull request](https://help.github.com/articles/creating-a-pull-request/) with
your changes!
