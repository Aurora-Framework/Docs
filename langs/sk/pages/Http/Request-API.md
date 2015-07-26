# Request API

## Konštanty
* GET
* POST
* PARAMETERS
* PUT
* OPTIONS
* DELETE
* PATCH

Dostupné sú cez `Request::Konstanta`.

## Získanie súboru

```php
   getFile(string kluc, any nahradnahodnota = null)
```

## Získanie všetkých súborov

```php
   getFiles()
```

## Získanie cookies

```php
   getCookie(string kluc, any nahradnahodnota = null)
```

## Získanie všetkých cookies

```php
   getCookies()
```

## Získanie parametrov z GET a POST

```php
   getParameters()
```

## Získanie parametru podľa typu

```php
   getParameter(konstant Request::PARAMETERS, string kluc, any nahradnahodnota = null)
```

## Získanie Uri

```php
   getUri()
```

## Získanie pathu

```php
   getPath()
```

## Metoda requestu

```php
   getMethod()
```
## Získanie http acceptu

```php
   getHttpAccept()
```
## Získanie http refereru

```php
   getReferer()
```
## Získanie user agenta

```php
   getUserAgent()
```

## Získanie ip adresy

```php
   getIpAddress()
```

## Je zabezpečený?

```php
   isSecure()
```

## Je ajax?

```php
   isAjax()
```
## Je metoda?

```php
   isMethod(string metoda = "POST")
```
## Je post?

```php
   isPost()
```

## Je get?
```php
   isGet()
```
## Získanie stringu s parametrami

```php
   getQueryString()
```

## Získanie čistého tela

```php
   getBody()
```
## Získanie spracovaného tela

```php
  getParsedBody(string kluc, any nahradnahodnota = null)
```

## Získanie používateľského mena

```php
   username()
```

## Získanie hesla

```php
   password()
```

## Získanie parametra z GET

```php
   get(string kluc, any nahradnahodnota = null)
```
## Získanie parametra z POST

```php
   post(string kluc, any nahradnahodnota = null)
```

## Získanie parametra z PUT (POST)

```php
   put(string kluc, any nahradnahodnota = null)
```

## Získanie parametra z PATCH (POST)

```php
   patch(string kluc, any nahradnahodnota = null)
```

## Získanie parametra z DELETE (POST)

```php
   delete(string kluc, any nahradnahodnota = null)
```

## Získanie parametra z OPTIONS (POST)

```php
   options(string kluc, any nahradnahodnota = null)
```

## Získanie parametra z SERVER (Globálna)

```php
   server(string kluc, any nahradnahodnota = null)
```
## Odstráni nežiadúce parametre z definovaného zdroja parametrov

```php
   blacklisted(konstanta Request::PARAMETERS, string|array blacklist)
```

## Zobrazí len žiadúce parametre z definovaného zdroja parametrov

```php
   whitelisted(konstanta Request::PARAMETERS, string|array whitelist)
```
