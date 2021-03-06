---
title: __identifier (C++/CLI)
ms.date: 10/12/2018
ms.topic: reference
f1_keywords:
- __identifier
- __identifier_cpp
helpviewer_keywords:
- __identifier keyword [C++]
ms.assetid: 348428af-afa7-4ff3-b571-acf874301cf2
ms.openlocfilehash: b63b7f6fe83c7761846d1d0c70de8b1665ad2f22
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/31/2018
ms.locfileid: "50641043"
---
# <a name="identifier-ccli"></a>__identifier (C++/CLI)

Habilita el uso de palabras clave de C++ como identificadores.

## <a name="all-platforms"></a>Todas las plataformas

### <a name="syntax"></a>Sintaxis

```cpp
__identifier(C++_keyword)
```

### <a name="remarks"></a>Comentarios

El uso de la **__identifier** palabra clave para los identificadores que no son palabras clave está permitido, pero no se recomienda como una cuestión de estilo.

## <a name="windows-runtime"></a>Windows en tiempo de ejecución

### <a name="requirements"></a>Requisitos

Opción del compilador: `/ZW`

### <a name="examples"></a>Ejemplos

**Ejemplo**

En el ejemplo siguiente, una clase denominada **plantilla** se crea en C# y se distribuye como un archivo DLL. En C++ / c++ / programa CLI que utiliza el **plantilla** (clase), el **__identifier** palabra clave oculta el hecho de que **plantilla** es una palabra clave de C++ estándar.

```cs
// identifier_template.cs
// compile with: /target:library
public class template {
   public void Run() { }
}
```

```cpp
// keyword__identifier.cpp
// compile with: /ZW
#using <identifier_template.dll>
int main() {
   __identifier(template)^ pTemplate = ref new __identifier(template)();
   pTemplate->Run();
}
```

## <a name="common-language-runtime"></a>Common Language Runtime

### <a name="remarks"></a>Comentarios

El **__identifier** palabra clave es válida con el `/clr` opción del compilador.

### <a name="requirements"></a>Requisitos

Opción del compilador: `/clr`

### <a name="examples"></a>Ejemplos

En el ejemplo siguiente, una clase denominada **plantilla** se crea en C# y se distribuye como un archivo DLL. En C++ / c++ / programa CLI que utiliza el **plantilla** (clase), el **__identifier** palabra clave oculta el hecho de que **plantilla** es una palabra clave de C++ estándar.

```cs
// identifier_template.cs
// compile with: /target:library
public class template {
   public void Run() { }
}
```

```cpp
// keyword__identifier.cpp
// compile with: /clr
#using <identifier_template.dll>

int main() {
   __identifier(template) ^pTemplate = gcnew __identifier(template)();
   pTemplate->Run();
}
```

## <a name="see-also"></a>Vea también

[Extensiones de componentes de .NET y UWP](../windows/component-extensions-for-runtime-platforms.md)<br/>
[Extensiones de componentes de .NET y UWP](../windows/component-extensions-for-runtime-platforms.md)