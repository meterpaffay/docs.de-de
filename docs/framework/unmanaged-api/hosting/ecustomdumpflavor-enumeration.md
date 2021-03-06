---
title: ECustomDumpFlavor-Enumeration
ms.date: 03/30/2017
api_name:
- ECustomDumpFlavor
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ECustomDumpFlavor
helpviewer_keywords:
- ECustomDumpFlavor enumeration [.NET Framework hosting]
ms.assetid: b39b3320-fac7-41f1-9a03-ab6fb0cd89c7
topic_type:
- apiref
ms.openlocfilehash: 9b4c1187945b4c243375a3096c3a8a3b22599aef
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616280"
---
# <a name="ecustomdumpflavor-enumeration"></a>ECustomDumpFlavor-Enumeration
Enthält Werte, die angeben, welche Elemente in eine benutzerdefinierte Teilmenge eines Heap Abbilds eingeschlossen werden sollen, wenn Fehler gemeldet werden.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef enum {  
    DUMP_FLAVOR_Mini            = 1,  
    DUMP_FLAVOR_NonHeapCLRState = 2  
} ECustomDumpFlavor;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`DUMP_FLAVOR_Mini`|Gibt an, dass das benutzerdefinierte Heap Abbild als Minidump gestartet werden soll, und schließt zusätzliche Daten ein, die von den an dieselbe Methode übergebenen [CustomDumpItem](customdumpitem-structure.md) -Instanzen angegeben werden.|  
|`DUMP_FLAVOR_NonHeapCLRState`|Gibt an, dass das benutzerdefinierte Heap-Dump alle Lauf Zeit Zustandsdaten erfassen soll, die nicht dynamisch zugeordnet wurden.|  
  
## <a name="remarks"></a>Hinweise  
 Ein Parameter vom Typ `ECustomDumpFlavor` wird an die [ICLRErrorReportingManager:: BeginCustomDump](iclrerrorreportingmanager-begincustomdump-method.md) -Methode übergeben.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Mscoree. dll  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ECustomDumpItemKind-Enumeration](ecustomdumpitemkind-enumeration.md)
- [ICLRErrorReportingManager-Schnittstelle](iclrerrorreportingmanager-interface.md)
- [Hosten von Enumerationen](hosting-enumerations.md)
