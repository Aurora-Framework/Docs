# Controller

## Modely

Pri pracovaní s modelmi nezabudniťe nastaviť aj pripojenie na databázu.

### Pridávanie modelov

Pridať model alebo modely možeme cez pole alebo cez metodu na `Model`.
V Controlleri pristupujeme k vytváraniu modelov následovne:

Pre jeden model:
```php
$this->createModel("App\\Model\\Article", "Article");
```

Pre pole modelov:
```php
$this->Model->createFromList([
   "Article" => "App\\Model\\Article"
]);
```

### Volanie Modelov

Pre získanie modelu používame prístup na triedu:

```php
$Article = $this->Model->Article->get(5);
```

## Cookies

### Pre vytvorenie cookies:

```php
$this->createCookie("test", "c");
```

### Získanie cookie

```php
echo $this->getCookie("test");
```

### Odstránenie Cookie

```php
$this->removeCookie("test");
```

## Sessions

Sú dostupné cez premmenú `Session`, ktorá musí byť nastavená cez
setter injection.

Dokumentáciu nájdete pri Sessions.
