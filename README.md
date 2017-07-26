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
