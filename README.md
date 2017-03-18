# Standalone Validator (YForm-Plugin)

__Plugin__ für das REDAXO-Addon [yform](https://github.com/yakamara/redaxo_yform): Ermöglicht das Validieren von PHP Arrays ohne HTML Formulare. Es können alle YForm Validierungen genutzt werden.

## Beispiel
```php
$input = [
  'first_name' => 'Max',
  'last_name' => 'Mustermann'
];

$rules = [
  ['empty' => ['first_name', 'Bitte Vornamen angeben.']],
  ['empty' => ['last_name', 'Bitte Nachnahmen angeben.']]
];

$validator = new standalone_validator();

$validator->setValueArray($input);
$validator->setValidationArray($rules);

if(!$validator->isValid()) {
  print_r($validator->getErrors());
}

```

Installation
-------

* Paket herunterladen oder über den Installer installieren


Changelog
-------

### Version 1.0 // 18.03.2017

* Umstellung auf eigenständiges AddOn
* Ausgabe Fehlermeldungen als assoziatives Array

### Version 0.1 // 26.07.2016

* Initial release
