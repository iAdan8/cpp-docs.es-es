---
title: Error del compilador C3865
ms.date: 11/04/2016
f1_keywords:
- C3865
helpviewer_keywords:
- C3865
ms.assetid: 9bc62bb0-4fb8-4856-a5cf-c7cb4029a596
ms.openlocfilehash: 846657d3598e268d78ff3c39f2bfc901756ad370
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/31/2018
ms.locfileid: "50642790"
---
# <a name="compiler-error-c3865"></a>Error del compilador C3865

'convención de llamada': solo puede usarse en funciones miembro nativas

Se usó una convención de llamada en una función que era una función global o en una función miembro administrada. La convención de llamada solo puede usarse en una función miembro (no administrado) nativo.

Para obtener más información, consulte [convenciones de llamada](../../cpp/calling-conventions.md).

El ejemplo siguiente genera C3865:

```
// C3865.cpp
// compile with: /clr
// processor: x86
void __thiscall Func(){}   // C3865

// OK
struct MyType {
   void __thiscall Func(){}
};
```