# Aurora.FileSystem

Knižnica FileSystem obstaráva prácu s lokálnym fileSystemom. Pracuje spolu
s Adaptermi, ktoré parsujú obsah podporovaných formátov.

## Existencia súboru, priečinka
```php
exists(string cesta)
```

## Je súborom?
```
isFile(string subor)
```

## Je priecinkom?

```php
isDirectory(string priecinok)
```
## Je priečinok prázdny?

```php
isDirectoryEmpty(string priecinok)
```

## Je čitateľný?

```php
isReadable(string subor)
```

## Je zapisovateľným?
```php
isWritable(string subor)
```

## Naposledy upravený

```php
lastModified(string subor)
```
## Veľkosť súboru

```php
filesize(string subor);
```

##

extension(string subor)

## Typ súboru

```
mime(string subor)
```
## Zmazať

```php
delete(string subor)
```

public static function deleteDirectory($path)

public static function glob($pattern, $flags = 0)

public static function getContents($file)

public static function putContent($file, $data, $lock = false)

public static function prependContent($file, $data, $lock = false)

public static function appendContent($file, $data, $lock = false)

public static function truncateContents($file, $lock = false)

public static function createDirectory($path, $mode = 0777, $recursive = false)

public static function includeFile($file)

public static function includeFileOnce($file)

public static function requireFile($file)

public static function requireFileOnce($file)

public static function file($file, $openMode = 'r', $useIncludePath = false)
