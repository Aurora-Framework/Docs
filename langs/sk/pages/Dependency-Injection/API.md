# API

## Zdieľanie

Pri opakovanom použití triedy s rovnakými parametrami je vhodné použiť
možnosť zdieľania, ktorá vytvorí triedu s parametrami len raz, druhý krát je to tá istá instancia.

```php
$DI->setShared(string menoTriedy);
```

## Aliasy a Inteface

Predstavme si situáciu, kedy sa nám nechce písať celý názov triedy s jej namespacom, vtedy do hry prichádzajú aliasy.

```php
$DI->alias(string aliasPreTriedu, string aliasTriedy);
```

## Vytváranie definície

Vytvoriť definíciu triedy je možné cez metodu:

```php
define(string menoTriedy, array parametre, bool zdielanie)
```

Parametre sa delia podľa toho, či ide o čistý parameter alebo o triedu s hintom.

```php
[
   ":GET" => $_GET # Parameter
   "Aurora\\AdapterInterface" => new Aurora\Adapter\JSON(); # Instancia
]
```
Napríklad:

```php
$DI->define("Aurora\\Http\\Request",[
   ":get" => $_GET,
   /* Atď, (komu sa to chce písať) */
], true);
```

## Setter Injection

Niekedy nie je nutné pre funkčnosť triedy vkládať aj jej dodatočné závislosti,
riešenia sú dve. Prvým riešením je `ServiceLocator`, pozor jedná sa o zlý-vzor.
Druhým riešením je `Setter Injection`, kedy po vytvorení triedy uložíme naše závislosti
do premmených cez metody setteru alebo priamo do premmenej.

Príklad:

```php
$Resolver->prepare("Aurora\\MVC\\Presenter", function($Instance) use ($Config) {
	$Instance->Cookie = new Aurora\Http\Cookie();
	$Instance->Cookie->raw = true;

	$Instance->Session = new Aurora\Session(null, $Config->get("session"));
	$Instance->Session->start();
});
```

Tento príklad nastaví Cookie aj Session.
