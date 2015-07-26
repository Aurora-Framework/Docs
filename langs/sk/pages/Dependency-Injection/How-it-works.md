#Ako funguje Dependency injection?

Dependency Injection slúži na dodanie všetkých závislostí, ktoré trieda
potrebuje poznáme 2 typy odovzdávania závislostí.

Dodanie závislostí môže byť:

* __constructor Injection
* setter Injection

Dependency Injection je proces kedy Dependency Resolver, teda trieda pre rozoznanie
závislostí odovzdá jej závislosti, cez daný typ dodania.

## Dependency Injection cez __construct

Uveďme si príklad, na ktorom si to vysvetlíme.

Máme triedu Opravár, náš opravár potrebuje niečo, čo spraví.
Na to, aby pracoval sa musí hneď dostať k produktu, ktorý ma opraviť.
Jeho trieda bude vyzerať takto:

```php
class Opravar extends OpravarInterface
{
   public function __construct($vec)
   {
      $this->oprav = $vec;
   }
}
```

Avšak, je tu jeden problém, opravár nevie čo všetko môže byť táto `Vec`,
preto využijeme hint na triedu.

```php
class Opravar extends OpravarInterface
{
   public function __construct(Vec $Vec)
   {
      $this->Oprav = $Vec;
   }
}
```

Teraz si môžeme byť istý, že opraví len jedenu vec, vie čo má očakávať,
samozrejme je lepšie, ak by daný opravár rátal len s jedným typom vecí.

```php
use ElektronikaInterface;

class Opravar extends OpravarInterface
{
   public function __construct(ElektronikaInterface $Vec)
   {
      $this->Oprav = $Vec;
   }
}
```
Prosím berte na vedomie, že predchádzajúci príklad je čisto príkladom,
ničím iným, neviem, kto by pomenoval triedy slovenskými názvami,
to by bolo veľmi zlé :).

## Dependency Injection cez setter

Setter injection je vhodný aj pre závisloti, na ktorých už trieda nutne nezávisí.
Napríklad trieda `Auto`, môže ale aj nemusí mať ŠPZ. Nastaviť závislosť je možné
2 spôsobmi, cez metodu alebo priamo cez premennú.

```php
class Auto
{
   public $SPZ;
}
```

Na záver skvelé video od Anthonyho Ferraru:
https://www.youtube.com/watch?v=IKD2-MAkXyQ
