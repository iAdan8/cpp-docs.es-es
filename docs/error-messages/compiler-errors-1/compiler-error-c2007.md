---
title: Error del compilador C2007
ms.date: 11/04/2016
f1_keywords:
- C2007
helpviewer_keywords:
- C2007
ms.assetid: ecd09d99-5036-408b-9e46-bc15488f049e
ms.openlocfilehash: f3c7b1a18dda9b2f9af7e346c2a1ed2f0303bb61
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/31/2018
ms.locfileid: "50434689"
---
# <a name="compiler-error-c2007"></a>Error del compilador C2007

\#sintaxis de #define

No hay ningún identificador aparece después de un `#define`. Para resolver el error, use un identificador.

El ejemplo siguiente genera C2007:

```
// C2007.cpp
#define   // C2007
```

Posible resolución:

```
// C2007b.cpp
// compile with: /c
#define true 1
```