---
title: Error del compilador C3536
ms.date: 11/04/2016
f1_keywords:
- C3536
helpviewer_keywords:
- C3536
ms.assetid: 8d866075-866b-49eb-9979-ee27b308f7e3
ms.openlocfilehash: b58136cc03efda83071c531b25889743de3485f5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/31/2018
ms.locfileid: "50456750"
---
# <a name="compiler-error-c3536"></a>Error del compilador C3536

'símbolo': no se puede usar antes de inicializarse

No se puede usar el símbolo indicado antes de inicializarse. En la práctica, esto significa que una variable no se puede usar para inicializarse a sí misma.

### <a name="to-correct-this-error"></a>Para corregir este error

1. No se inicialice una variable consigo misma.

## <a name="example"></a>Ejemplo

El ejemplo siguiente genera el error C3536 porque cada variable se inicializa con sí mismo.

```
// C3536.cpp
// Compile with /Zc:auto
int main()
{
   auto a = a;     //C3536
   auto b = &b;    //C3536
   auto c = c + 1; //C3536
   auto* d = &d;   //C3536
   auto& e = e;    //C3536
   return 0;
};
```

## <a name="see-also"></a>Vea también

[Auto (palabra clave)](../../cpp/auto-keyword.md)