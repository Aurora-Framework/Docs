# API

### Nastavenie dát

```
$Config = new Aurora\Config(array data);
```

Príklad:

```php
$Config = new Aurora\Config([
   "user" => [
      "sayHello" => "Hi :name",
      "messages" => ":name, you have :n new messages"
   ]
]);
```

### Získanie kľúča

```php
$Config->get(string kluc);
```

Príklad:
```php
$Config->get("user.sayHello"); # "Hi :name"
```

### Spájanie konfigurácií

```php
$Config->merge(object Config, string preKluc);
```

Príklad:

```php
$App = new Aurora\Config(["key" => "blaaaaa"]);
$Config = $Config->merge($App, "app"); # Dostupné cez app.key
```
Ak je je definovaný predKluc, dochadza k rekrusivnemu nahradzovaniu, teda zachovaniu klucov s rovnakym obsahom.

##### Ostatné funkcie sú prebrané z StatefulTrait, prosím pre bližšiu dokumentáciu pozri Helper\StatefulTrait
