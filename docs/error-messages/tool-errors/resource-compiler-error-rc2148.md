---
title: Error del compilador de recursos RC2148
ms.date: 11/04/2016
f1_keywords:
- RC2148
helpviewer_keywords:
- RC2148
ms.assetid: 0290065c-35d3-4815-80c5-40bf7132ae1d
ms.openlocfilehash: 6d9946c20705fa14046823104455c2819fac353f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/31/2018
ms.locfileid: "50551819"
---
# <a name="resource-compiler-error-rc2148"></a>Error del compilador de recursos RC2148

Identificador de SUBIDIOMA demasiado grande

El valor de identificador de SUBIDIOMA estaba fuera del intervalo.

La instrucción **LANGUAGE** debe usar la sintaxis siguiente:

**LANGUAGE** *Id_idioma_primario*,*Id_idioma_secundario*

Identificadores de SUBIDIOMA válidos se definen como **sublang dentro** constantes en el archivo WINNT.h.