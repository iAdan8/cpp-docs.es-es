---
title: strstr, wcsstr, _mbsstr, _mbsstr_l
ms.date: 11/04/2016
apiname:
- _mbsstr
- wcsstr
- _mbsstr_l
- strstr
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ntdll.dll
- ucrtbase.dll
- api-ms-win-crt-multibyte-l1-1-0.dll
- ntoskrnl.exe
apitype: DLLExport
f1_keywords:
- _fstrstr
- _ftcsstr
- strstr
- wcsstr
- _mbsstr
- _tcsstr
helpviewer_keywords:
- strings [C++], searching
- mbsstr function
- _ftcsstr function
- ftcsstr function
- fstrstr function
- _tcsstr function
- substrings, finding
- mbsstr_l function
- tcsstr function
- _mbsstr function
- wcsstr function
- _fstrstr function
- _mbsstr_l function
- strstr function
ms.assetid: 03d70c3f-2473-45cb-a5f8-b35beeb2748a
ms.openlocfilehash: 42e02473e062c3af9524ed432aa163b7574342de
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/31/2018
ms.locfileid: "50541068"
---
# <a name="strstr-wcsstr-mbsstr-mbsstrl"></a>strstr, wcsstr, _mbsstr, _mbsstr_l

Devuelve un puntero a la primera aparición de una cadena de búsqueda en una cadena.

> [!IMPORTANT]
> `_mbsstr` y `_mbsstr_l` no se pueden usar en aplicaciones que se ejecutan en Windows en tiempo de ejecución. Para obtener más información, vea [Funciones de CRT no admitidas en aplicaciones de la Plataforma universal de Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sintaxis

```C
char *strstr(
   const char *str,
   const char *strSearch
); // C only
char *strstr(
   char *str,
   const char *strSearch
); // C++ only
const char *strstr(
   const char *str,
   const char *strSearch
); // C++ only
wchar_t *wcsstr(
   const wchar_t *str,
   const wchar_t *strSearch
); // C only
wchar_t *wcsstr(
   wchar_t *str,
   const wchar_t *strSearch
); // C++ only
const wchar_t *wcsstr(
   const wchar_t *str,
   const wchar_t *strSearch
); // C++ only
unsigned char *_mbsstr(
   const unsigned char *str,
   const unsigned char *strSearch
); // C only
unsigned char *_mbsstr(
   unsigned char *str,
   const unsigned char *strSearch
); // C++ only
const unsigned char *_mbsstr(
   const unsigned char *str,
   const unsigned char *strSearch
); // C++ only
unsigned char *_mbsstr_l(
   const unsigned char *str,
   const unsigned char *strSearch,
   _locale_t locale
); // C only
unsigned char *_mbsstr_l(
   unsigned char *str,
   const unsigned char *strSearch,
   _locale_t locale
); // C++ only
const unsigned char *_mbsstr_l(
   const unsigned char *str,
   const unsigned char *strSearch,
   _locale_t locale
); // C++ only
```

### <a name="parameters"></a>Parámetros

*str*<br/>
Cadena terminada en NULL que se va a buscar.

*strSearch*<br/>
Cadena terminada en NULL que se va a buscar.

*locale*<br/>
Configuración regional que se va a usar.

## <a name="return-value"></a>Valor devuelto

Devuelve un puntero a la primera aparición de *strSearch* en *str*, o NULL si *strSearch* no aparece en *str*. Si *strSearch* señala a una cadena de longitud cero, la función devuelve *str*.

## <a name="remarks"></a>Comentarios

El `strstr` función devuelve un puntero a la primera aparición de *strSearch* en *str*. En la búsqueda no se incluyen los caracteres nulos de finalización. `wcsstr` es la versión con caracteres anchos de `strstr` y `_mbsstr` es la versión de caracteres multibyte. Los argumentos y el valor devuelto de `wcsstr` son cadenas de caracteres anchos; los de `_mbsstr` son cadenas de caracteres multibyte. `_mbsstr` valida sus parámetros. Si *str* o *strSearch* es NULL, se invoca el controlador de parámetros no válidos, como se describe en [validación de parámetros](../../c-runtime-library/parameter-validation.md) . Si la ejecución puede continuar, `_mbsstr` establece `errno` EINVAL y devuelve 0. `strstr` y `wcsstr` no validan sus parámetros. Estas tres funciones se comportan exactamente igual.

> [!IMPORTANT]
> Estas funciones podrían provocar la amenaza de un problema de saturación del búfer. Los problemas de saturación del búfer se pueden usar para atacar un sistema, porque pueden permitir la ejecución de código arbitrario, lo que podría dar lugar a un aumento de privilegios injustificado. Para obtener más información, vea [Avoiding Buffer Overruns](/windows/desktop/SecBP/avoiding-buffer-overruns)(Evitar saturaciones del búfer).

En C, estas funciones toman una **const** puntero para el primer argumento. En C++, hay disponibles dos sobrecargas. La sobrecarga que toma un puntero a **const** devuelve un puntero a **const**; la versión que toma un puntero a que no sean de**const** devuelve un puntero a que no sean de **Const**. Se define la macro _CRT_CONST_CORRECT_OVERLOADS si tanto el **const** y no-**const** versiones de estas funciones están disponibles. Si necesita que no sea**const** comportamiento para ambas sobrecargas de C++, defina el símbolo _CONST_RETURN.

El valor de salida se ve afectado por el valor de la categoría de configuración regional de LC_CTYPE; Para obtener más información, consulte [setlocale, _wsetlocale](setlocale-wsetlocale.md). Las versiones de estas funciones que no tienen la **_l** sufijo usan la configuración regional actual de este comportamiento dependiente de la configuración regional; las versiones que tienen el **_l** sufijo son idénticas salvo que usan en su lugar el parámetro de configuración regional que se pasa. Para obtener más información, vea [Locale](../../c-runtime-library/locale.md).

### <a name="generic-text-routine-mappings"></a>Asignaciones de rutina de texto genérico

|Rutina TCHAR.H|_UNICODE y _MBCS no definidos|_MBCS definido|_UNICODE definido|
|---------------------|------------------------------------|--------------------|-----------------------|
|`_tcsstr`|`strstr`|`_mbsstr`|`wcsstr`|
|**N/D**|**N/D**|`_mbsstr_l`|**N/D**|

## <a name="requirements"></a>Requisitos

|Rutina|Encabezado necesario|
|-------------|---------------------|
|`strstr`|\<string.h>|
|`wcsstr`|\<string.h> o \<wchar.h>|
|`_mbsstr`, `_mbsstr_l`|\<mbstring.h>|

Para obtener más información sobre la compatibilidad, vea [Compatibilidad](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Ejemplo

```C
// crt_strstr.c

#include <string.h>
#include <stdio.h>

char str[] =    "lazy";
char string[] = "The quick brown dog jumps over the lazy fox";
char fmt1[] =   "         1         2         3         4         5";
char fmt2[] =   "12345678901234567890123456789012345678901234567890";

int main( void )
{
   char *pdest;
   int  result;
   printf( "String to be searched:\n   %s\n", string );
   printf( "   %s\n   %s\n\n", fmt1, fmt2 );
   pdest = strstr( string, str );
   result = (int)(pdest - string + 1);
   if ( pdest != NULL )
      printf( "%s found at position %d\n", str, result );
   else
      printf( "%s not found\n", str );
}
```

```Output
String to be searched:
   The quick brown dog jumps over the lazy fox
            1         2         3         4         5
   12345678901234567890123456789012345678901234567890

lazy found at position 36
```

## <a name="see-also"></a>Vea también

[Manipulación de cadenas](../../c-runtime-library/string-manipulation-crt.md)<br/>
[Configuración regional](../../c-runtime-library/locale.md)<br/>
[Interpretación de secuencias de caracteres de varios bytes](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[strcspn, wcscspn, _mbscspn, _mbscspn_l](strcspn-wcscspn-mbscspn-mbscspn-l.md)<br/>
[strcmp, wcscmp, _mbscmp](strcmp-wcscmp-mbscmp.md)<br/>
[strpbrk, wcspbrk, _mbspbrk, _mbspbrk_l](strpbrk-wcspbrk-mbspbrk-mbspbrk-l.md)<br/>
[strrchr, wcsrchr, _mbsrchr, _mbsrchr_l](strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)<br/>
[strspn, wcsspn, _mbsspn, _mbsspn_l](strspn-wcsspn-mbsspn-mbsspn-l.md)<br/>
[basic_string::find](../../standard-library/basic-string-class.md#find)<br/>
