---
title: Error del compilador C2534
ms.date: 11/04/2016
f1_keywords:
- C2534
helpviewer_keywords:
- C2534
ms.assetid: 481f9f54-5b51-4aa0-8eea-218f10807705
ms.openlocfilehash: e684804ea31b16f31c82e244cb4f9a6aaf2d08c3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/31/2018
ms.locfileid: "50638261"
---
# <a name="compiler-error-c2534"></a>Error del compilador C2534

'identifier': constructor no puede devolver un valor

Un constructor no puede devolver un valor o tienen un tipo de valor devuelto (ni siquiera un `void` tipo de valor devuelto).

Este error puede corregirse mediante la eliminación de la `return` instrucción desde la definición del constructor.

El ejemplo siguiente genera C2534:

```
// C2534.cpp
class A {
public:
   int i;
   A() { return i; }   // C2534
};
```