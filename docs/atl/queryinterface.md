---
title: QueryInterface
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- QueryInterface
helpviewer_keywords:
- interfaces, pointers
- interfaces, availability
- QueryInterface method
ms.assetid: 62fce95e-aafa-4187-b50b-e6611b74c3b3
ms.openlocfilehash: 552d0a0f5cbc93bd0d8fc6eb4a77eecee851add6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/31/2018
ms.locfileid: "50477940"
---
# <a name="queryinterface"></a>QueryInterface

Aunque hay mecanismos mediante el cual un objeto puede expresar la funcionalidad que proporciona estáticamente (antes de se crea una instancia), el mecanismo fundamental de COM es usar el `IUnknown` método llamado [QueryInterface](/windows/desktop/api/unknwn/nf-unknwn-iunknown-queryinterface(q_)).

Cada interfaz se deriva `IUnknown`, por lo que cada interfaz tiene una implementación de `QueryInterface`. Independientemente de la implementación, este método consulta un objeto mediante el IID de la interfaz a la que el llamador desea un puntero. Si el objeto admite esa interfaz, `QueryInterface` recupera un puntero a la interfaz, mientras llama a `AddRef`. En caso contrario, devuelve el código de error E_NOINTERFACE.

Tenga en cuenta que debe obedecer [recuento de referencias](../atl/reference-counting.md) reglas en todo momento. Si se llama a `Release` en un puntero de interfaz para reducir el recuento de referencias en cero, no debe usar ese puntero nuevo. En ocasiones necesitará obtener una referencia débil a un objeto (es decir, puede que desee obtener un puntero a una de sus interfaces sin incrementar el recuento de referencias), pero no es aceptable para ello, llame a `QueryInterface` seguido `Release`. El puntero obtenido de manera no es válido y no debe usarse. Esto con más facilidad hace evidente cuando [_ATL_DEBUG_INTERFACES](reference/debugging-and-error-reporting-macros.md#_atl_debug_interfaces) está definido, por lo que definir esta macro es una forma útil de los errores de recuento de referencias de búsqueda.

## <a name="see-also"></a>Vea también

[Introducción a COM](../atl/introduction-to-com.md)<br/>
[QueryInterface: Desplazarse por un objeto](/windows/desktop/com/queryinterface--navigating-in-an-object)

