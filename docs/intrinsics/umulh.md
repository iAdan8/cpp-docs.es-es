---
title: __umulh
ms.date: 11/04/2016
f1_keywords:
- __umulh
helpviewer_keywords:
- __umulh intrinsic
ms.assetid: d241b53a-e6f7-4af1-9f6e-84e149158f03
ms.openlocfilehash: 6a0d427f32e275725177b10f01565e6947760f09
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/09/2018
ms.locfileid: "51328555"
---
# <a name="umulh"></a>__umulh

**Específicos de Microsoft**

Devolver los 64 bits superiores del producto de dos enteros sin signo de 64 bits.

## <a name="syntax"></a>Sintaxis

```
unsigned __int64 __umulh(
   unsigned __int64 a,
   unsigned __int64 b
);
```

#### <a name="parameters"></a>Parámetros

*a*<br/>
[in] El primer número a multiplicar.

*b*<br/>
[in] El segundo número a multiplicar.

## <a name="return-value"></a>Valor devuelto

Los 64 bits superiores del resultado de 128 bits de la multiplicación.

## <a name="requirements"></a>Requisitos

|Función intrínseca|Arquitectura|
|---------------|------------------|
|`__umulh`|x64|

**Archivo de encabezado** \<intrin.h >

## <a name="remarks"></a>Comentarios

Estas rutinas solo están disponibles como intrínsecos.

## <a name="example"></a>Ejemplo

```
// umulh.cpp
// processor: X64
#include <cstdio>
#include <intrin.h>

int main()
{
    unsigned __int64 i = 0x10;
    unsigned __int64 j = 0xFEDCBA9876543210;
    unsigned __int64 k = i * j; // k has the low 64 bits
                                // of the product.
    unsigned __int64 result;
    result = __umulh(i, j); // result has the high 64 bits
                            // of the product.
    printf_s("0x%I64x * 0x%I64x = 0x%I64x%I64x \n", i, j, result, k);
    return 0;
}
```

```Output
0x10 * 0xfedcba9876543210 = 0xfedcba98765432100
```

**FIN de Específicos de Microsoft**

## <a name="see-also"></a>Vea también

[Intrínsecos del controlador](../intrinsics/compiler-intrinsics.md)