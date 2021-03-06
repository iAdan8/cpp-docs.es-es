---
title: /BIND
ms.date: 11/04/2016
f1_keywords:
- /bind
helpviewer_keywords:
- -BIND editbin option
- entry points, addresses
- BIND editbin option
- entry points
- /BIND editbin option
- import address table
ms.assetid: 3772b330-1868-4c90-857d-c31faa867982
ms.openlocfilehash: 671a26268ab07db4a38ae241ae1e0867dd0eb43c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/31/2018
ms.locfileid: "50470855"
---
# <a name="bind"></a>/BIND

```
/BIND[:PATH=path]
```

## <a name="remarks"></a>Comentarios

Esta opción establece las direcciones de los puntos de entrada en la tabla de direcciones de importación para un archivo ejecutable o DLL. Use esta opción para reducir el tiempo de carga de un programa.

Especifique el archivo ejecutable y los archivos DLL en el programa la *archivos* argumento en la línea de comandos EDITBIN. El elemento opcional *ruta* argumento/BIND especifica la ubicación de los archivos DLL utilizado por los archivos especificados. Separe varios directorios con punto y coma (**;**). Si *ruta* no se especifica, EDITBIN buscará los directorios especificados en la variable de entorno PATH. Si *ruta* se especifica, EDITBIN pasará por alto la variable PATH.

De forma predeterminada, el cargador del programa establece las direcciones de puntos de entrada cuando se carga un programa. La cantidad de tiempo que tarda este proceso varía, dependiendo del número de archivos DLL y el número de puntos de entrada hace referencia en el programa. Si se ha modificado un programa con/BIND, y si las direcciones base del archivo ejecutable y sus archivos DLL no entren en conflicto con los archivos DLL que ya están cargadas, el sistema operativo no es necesario establecer estas direcciones. En una situación donde incorrectamente se basan los archivos, el sistema operativo vuelve a colocar los archivos DLL y vuelve a calcular las direcciones de punto de entrada, que se suma al tiempo de carga del programa.

## <a name="see-also"></a>Vea también

[Opciones de EDITBIN](../../build/reference/editbin-options.md)