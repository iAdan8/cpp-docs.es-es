---
title: Error del compilador C2469
ms.date: 11/04/2016
f1_keywords:
- C2469
helpviewer_keywords:
- C2469
ms.assetid: 3814bdff-581a-4d3e-8b47-8de6887cea69
ms.openlocfilehash: e9c447451b052841da2ef0c7be582257ee216785
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/31/2018
ms.locfileid: "50484882"
---
# <a name="compiler-error-c2469"></a>Error del compilador C2469

'operator': no se puede asignar un objeto 'type'

Se pasó un tipo no válido a un operador.

El ejemplo siguiente genera la advertencia C2469:

```
// C2469.cpp
int main() {
   int *i = new void;   // C2469
   int *i = new int;   // OK
}
```