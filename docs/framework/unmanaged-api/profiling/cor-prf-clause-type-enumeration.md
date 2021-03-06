---
title: COR_PRF_CLAUSE_TYPE-Enumeration
ms.date: 03/30/2017
api_name:
- COR_PRF_CLAUSE_TYPE
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_CLAUSE_TYPE
helpviewer_keywords:
- COR_PRF_CLAUSE_TYPE enumeration [.NET Framework profiling]
ms.assetid: f64c325a-ed3a-4aaf-b847-a88edbc4fefc
topic_type:
- apiref
ms.openlocfilehash: a308017dc80dd973cbf108ba9df824193775f5ff
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501052"
---
# <a name="cor_prf_clause_type-enumeration"></a>COR_PRF_CLAUSE_TYPE-Enumeration
Zeigt den Typ der Ausnahmeklausel an, die der Code gerade eben eingegeben oder zurückgelassen hat.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef enum {  
    COR_PRF_CLAUSE_NONE = 0,  
    COR_PRF_CLAUSE_FILTER = 1,  
    COR_PRF_CLAUSE_CATCH = 2,  
    COR_PRF_CLAUSE_FINALLY = 3,  
} COR_PRF_CLAUSE_TYPE;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`COR_PRF_CLAUSE_NONE`|Die Exception-Klausel ist ungültig.|  
|`COR_PRF_CLAUSE_FILTER`|Die Exception-Klausel ist ein Filter Ausdruck.|  
|`COR_PRF_CLAUSE_CATCH`|Die Exception-Klausel ist eine- `catch` Anweisung.|  
|`COR_PRF_CLAUSE_FINALLY`|Die Exception-Klausel ist eine- `finally` Anweisung.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen:

- [Profilerstellungsenumerationen](profiling-enumerations.md)
