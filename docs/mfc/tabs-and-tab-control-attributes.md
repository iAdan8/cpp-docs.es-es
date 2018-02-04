---
title: "Pestañas y ficha controlan los atributos | Documentos de Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- attributes [MFC], reference topics
- tab controls [MFC], attributes
- tabs [MFC]
- tabs [MFC], attributes
- CTabCtrl class [MFC], tab control attributes
ms.assetid: ecf190cb-f323-4751-bfdb-766dbe6bb553
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d10db5f1282c726b30536be35b348d50c8bb4a14
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/21/2017
---
# <a name="tabs-and-tab-control-attributes"></a>Pestañas y atributos del control de pestaña
Tiene un gran control sobre la apariencia y el comportamiento de las fichas que componen un control de pestaña ([CTabCtrl](../mfc/reference/ctabctrl-class.md)). Cada pestaña puede tener una etiqueta, un icono, un estado de elemento y un valor de 32 bits definido por la aplicación asociados a él. Para cada pestaña, puede mostrar el icono, la etiqueta o ambos.  
  
 Además, cada elemento de ficha puede tener tres estados posibles: presionado, no presionado o resaltado. Este estado solo puede establecerse mediante la modificación de un elemento de ficha existente. Para modificar un elemento de ficha existente, recuperar con una llamada a [GetItem](../mfc/reference/ctabctrl-class.md#getitem), modifique la `TCITEM` estructura (específicamente el **"_mfc_CTabCtrl.3a3a.GetItem"** y **dwStateMask** miembros de datos ) y, a continuación, devolver modificados `TCITEM` estructura con una llamada a [SetItem](../mfc/reference/ctabctrl-class.md#setitem). Si necesita borrar los Estados de elemento de todos los elementos de ficha en una `CTabCtrl` de objetos, realizar una llamada a [DeselectAll](../mfc/reference/ctabctrl-class.md#deselectall). Esta función restablece el estado de todos los elementos de ficha o todos los elementos excepto la seleccionada actualmente.  
  
 El código siguiente, borra el estado de todos los elementos de ficha y, a continuación, modifica el estado del tercer elemento:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#32](../mfc/codesnippet/cpp/tabs-and-tab-control-attributes_1.cpp)]  
  
 Para obtener más información acerca de los atributos de la pestaña, vea [pestañas y atributos de ficha](http://msdn.microsoft.com/library/windows/desktop/bb760550) del SDK de Windows. Para obtener más información sobre cómo agregar pestañas a un control de pestaña, vea [adición de fichas a un Control de pestaña](../mfc/adding-tabs-to-a-tab-control.md) más adelante en este tema.  
  
## <a name="see-also"></a>Vea también  
 [Usar CTabCtrl](../mfc/using-ctabctrl.md)   
 [Controles](../mfc/controls-mfc.md)
