---
title: Advertencia del compilador (nivel 1) C4553
ms.date: 11/04/2016
f1_keywords:
- C4553
helpviewer_keywords:
- C4553
ms.assetid: d8aacbe0-3cb5-4367-a6e5-fd7e28f0ff9d
ms.openlocfilehash: 7a299d4a99818699e9be31e7d15d9e589de05c15
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/31/2018
ms.locfileid: "50470348"
---
# <a name="compiler-warning-level-1-c4553"></a>Advertencia del compilador (nivel 1) C4553

'operador': operador no tiene ningún efecto; ¿ha pensado en 'operador'?

Si una instrucción de expresión tiene un operador con ningún efecto secundario como la parte superior de la expresión, probablemente es un error.

El ejemplo siguiente genera C4553:

```
// C4553.cpp
// compile with: /W1
int func()
{
   return 0;
}

int main()
{
   int i;
   i == func();   // C4553
   // try the following line instead
   // i = func();
}
```