---
title: Control de eventos
ms.date: 11/04/2016
helpviewer_keywords:
- attributes [C++], event handling
- intrinsic functions [C++], event handling
- event handling [C++], Visual C++
ms.assetid: 82de3f9a-2d88-470c-9527-8a5b54c8ced4
ms.openlocfilehash: d1a89d5afce2e3715b5a61c0815d88ed2fbae8b5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/31/2018
ms.locfileid: "50523258"
---
# <a name="event-handling"></a>Control de eventos

Control de eventos es compatible principalmente para las clases COM (las clases de C++ que implementan objetos COM, normalmente mediante clases ATL o [coclase](../windows/coclass.md) atributo).  Para obtener más información, consulte [control de eventos en COM](../cpp/event-handling-in-com.md).

El control de eventos también se admite para las clases de C++ nativo (clases de C++ que no implementan objetos COM); sin embargo, esa compatibilidad está en desuso y se quitará en futuras versiones.  Para obtener más información, consulte [control de eventos en C++ nativo](../cpp/event-handling-in-native-cpp.md).

El control de eventos admite el uso de único subproceso y multiproceso y protege los datos de acceso multiproceso simultáneo. También permite que se deriven subclases de clases del origen de eventos o del receptor y que se admita el suministro y la recepción de eventos extendidos en la clase derivada.

Visual C++ incluye atributos y palabras clave para declarar eventos y controladores de eventos. Los atributos y las palabras clave de eventos se pueden utilizar en programas de CLR y en programas de C++ nativo.

|Tema|Descripción|
|-----------|-----------------|
|[event_source](../windows/event-source.md)|Crea un origen de eventos.|
|[event_receiver](../windows/event-receiver.md)|Crea un receptor de eventos (receptor).|
|[__event](../cpp/event.md)|Declara un evento.|
|[__raise](../cpp/raise.md)|Resalta el sitio de llamada de un evento.|
|[__hook](../cpp/hook.md)|Asocia un método de control a un evento.|
|[__unhook](../cpp/unhook.md)|Disocia un método de control de un evento.|

## <a name="see-also"></a>Vea también

[Referencia del lenguaje C++](../cpp/cpp-language-reference.md)<br/>
[Palabras clave](../cpp/keywords-cpp.md)