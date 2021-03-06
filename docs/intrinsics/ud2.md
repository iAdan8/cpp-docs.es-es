---
title: __ud2
ms.date: 11/04/2016
f1_keywords:
- __ud2
helpviewer_keywords:
- UD2 instruction
- __ud2 intrinsic
ms.assetid: 0831cd5a-8b65-402e-bb57-11e1d5d7ffd2
ms.openlocfilehash: dd876f26349c39e0af0d2e0f100fb4e13efa50f4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/31/2018
ms.locfileid: "50666549"
---
# <a name="ud2"></a>__ud2

**Específicos de Microsoft**

Genera una instrucción no definida.

## <a name="syntax"></a>Sintaxis

```
void __ud2();
```

## <a name="remarks"></a>Comentarios

El procesador genera una excepción de código de operación no válida si ejecuta una instrucción no definida.

El `__ud2` función es equivalente a la `UD2` instrucción máquina y solo está disponible en modo kernel. Para obtener más información, busque el documento, "Manual del desarrollador de Software de arquitectura Intel, volumen 2: referencia de conjunto de instrucciones," en el [Intel Corporation](https://software.intel.com/articles/intel-sdm) sitio.

## <a name="requirements"></a>Requisitos

|Función intrínseca|Arquitectura|
|---------------|------------------|
|`__ud2`|x86, x64|

**Archivo de encabezado** \<intrin.h >

**FIN de Específicos de Microsoft**

## <a name="example"></a>Ejemplo

El ejemplo siguiente ejecuta una instrucción no definida, que produce una excepción. El controlador de excepciones, a continuación, cambia el código de retorno de cero a uno.

```
// __ud2_intrinsic.cpp
#include <stdio.h>
#include <intrin.h>
#include <excpt.h>
// compile with /EHa

int main() {

// Initialize the return code to 0.
int ret = 0;

// Attempt to execute an undefined instruction.
  printf("Before __ud2(). Return code = %d.\n", ret);
  __try {
  __ud2();
  }

// Catch any exceptions and set the return code to 1.
  __except(EXCEPTION_EXECUTE_HANDLER){
  printf("  In the exception handler.\n");
  ret = 1;
  }

// Report the value of the return code.
  printf("After __ud2().  Return code = %d.\n", ret);
  return ret;
}
```

```Output
Before __ud2(). Return code = 0.
  In the exception handler.
After __ud2().  Return code = 1.
```

## <a name="see-also"></a>Vea también

[Intrínsecos del controlador](../intrinsics/compiler-intrinsics.md)