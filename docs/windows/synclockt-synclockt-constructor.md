---
title: Constructor Synclockt | Documentos de Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockT::SyncLockT
dev_langs: C++
helpviewer_keywords: SyncLockT, constructor
ms.assetid: 713dfd9f-7369-4d86-b4a0-8b32c184d89b
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: fb7e1f9715f84a272e6bdb1029439f9310a65428
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/24/2017
---
# <a name="synclocktsynclockt-constructor"></a>SyncLockT::SyncLockT (Constructor)
Admite la infraestructura WRL y no está diseñada para utilizarse directamente desde el código.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
SyncLockT(  
   _Inout_ SyncLockT&& other  
);  
  
explicit SyncLockT(  
   typename SyncTraits::Type sync = SyncTraits::GetInvalidValue()  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `other`  
 Una referencia a valor r a otro objeto SyncLockT.  
  
 `sync`  
 Una referencia a otro objeto de SyncLockWithStatusT.  
  
## <a name="remarks"></a>Comentarios  
 Inicializa una nueva instancia de la clase SyncLockT.  
  
 El primer constructor inicializa el objeto de SyncLockT actual de otro objeto SyncLockT especificado por el parámetro `other`y, a continuación, se invalidan del otro objeto SyncLockT. El segundo constructor es `protected`y se inicializa el objeto de SyncLockT actual en un estado no válido.  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** corewrappers.h  
  
 **Namespace:** Wrappers  
  
## <a name="see-also"></a>Vea también  
 [SyncLockT (clase)](../windows/synclockt-class.md)