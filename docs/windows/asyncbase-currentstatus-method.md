---
title: "Asyncbase:: currentStatus (método) | Documentos de Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: async/Microsoft::WRL::AsyncBase::CurrentStatus
dev_langs: C++
helpviewer_keywords: CurrentStatus method
ms.assetid: 26ee4c4a-6525-4a5f-b49c-3ca40c365eb6
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b70974d4d53c819d1cf614660c53df0a75510482
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/24/2017
---
# <a name="asyncbasecurrentstatus-method"></a>AsyncBase::CurrentStatus (Método)
Recupera el estado de la operación asincrónica actual.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
inline void CurrentStatus(  
   Details::AsyncStatusInternal *status  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `status`  
 La ubicación donde esta operación almacena el estado actual.  
  
## <a name="remarks"></a>Comentarios  
 Esta operación es segura para subprocesos.  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** async.h  
  
 **Espacio de nombres:** Microsoft::WRL  
  
## <a name="see-also"></a>Vea también  
 [AsyncBase (clase)](../windows/asyncbase-class.md)   
 [AsyncStatusInternal (enumeración)](../windows/asyncstatusinternal-enumeration.md)