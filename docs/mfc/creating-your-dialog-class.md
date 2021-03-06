---
title: Creating Your Dialog (Clase)
ms.date: 11/04/2016
helpviewer_keywords:
- dialog boxes [MFC], creating
- MFC dialog boxes [MFC], creating
- files [MFC], creating
- dialog classes [MFC], Add Class Wizard
- dialog classes [MFC], creating
ms.assetid: d5321741-da41-47a8-bb1c-6a0e8b28c4c1
ms.openlocfilehash: 924cf2d79056d958aad775f92a6d0df2d45c8a70
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/31/2018
ms.locfileid: "50536586"
---
# <a name="creating-your-dialog-class"></a>Creating Your Dialog (Clase)

Para cada cuadro de diálogo en el programa, cree una nueva clase de cuadro de diálogo para que funcione con el recurso de cuadro de diálogo.

[Agregar una clase](../ide/adding-a-class-visual-cpp.md) se explica cómo crear una nueva clase de cuadro de diálogo. Cuando se crea una clase de cuadro de diálogo con el Asistente para agregar clases, escribe lo siguiente el. H y. Archivos CPP que especifique:

En. Archivo de H:

- Una declaración de clase para la clase de cuadro de diálogo. La clase se deriva [CDialog](../mfc/reference/cdialog-class.md).

En. Archivo CPP:

- Un mapa de mensajes para la clase.

- Un constructor estándar para el cuadro de diálogo.

- Un reemplazo del [DoDataExchange](../mfc/reference/cwnd-class.md#dodataexchange) función miembro. Editar esta función. Se utiliza para las capacidades de intercambio y validación de datos de cuadro de diálogo como se describe más adelante en [intercambio de datos de cuadro de diálogo y validación](../mfc/dialog-data-exchange-and-validation.md).

## <a name="see-also"></a>Vea también

[Creación de una clase de diálogo con los Asistentes para código](../mfc/creating-a-dialog-class-with-code-wizards.md)<br/>
[Ciclo de vida de un cuadro de diálogo](../mfc/life-cycle-of-a-dialog-box.md)

