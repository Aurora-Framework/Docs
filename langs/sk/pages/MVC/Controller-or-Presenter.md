# Controller alebo Presenter

Ak ste nový v frameworkoch, môže Vám robiť menší problém
rozhodnúť sa či použiť Controller alebo Presenter.

Poďme sa pozrieť na to, kedy použiť Presenter a kedy Controller.

Presenter slúži na to, aby clientovi zobrazil údaje, s ktorými
môže interagovať.

Controller je na to, aby spracoval požiadavky používateľa, napríklad
Ajax, Soap, Rest.

Áno, je to tak jednoduché, ak vaša aplikácia neobsahuje Ajax alebo iné
podobné požiadavky, jednoducho si v presentery pridajte časť kódu,
ktorá overí, či ide napríklad o `POST` požiadavku, ktorú spracujete.
