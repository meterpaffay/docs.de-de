---
title: ISymUnmanagedWriter::Abort-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.Abort
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::Abort
helpviewer_keywords:
- ISymUnmanagedWriter::Abort method [.NET Framework debugging]
- Abort method, ISymUnmanagedWriter interface [.NET Framework debugging]
ms.assetid: 416b220f-38d4-48e0-bb49-d2faa7366702
topic_type:
- apiref
ms.openlocfilehash: 09f39d3b6486e2ec3c04c5d1858a85ce56895527
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610157"
---
# <a name="isymunmanagedwriterabort-method"></a>ISymUnmanagedWriter::Abort-Methode
Schließt den Symbolwriter, ohne die Symbole an den Symbol Speicher zu übergeben. Nach diesem Befehl wird der Symbolwriter für weitere Updates ungültig. Verwenden Sie stattdessen die [ISymUnmanagedWriter:: Close](isymunmanagedwriter-close-method.md) -Methode, um ein Commit für die Symbole durchführen und den Symbolwriter zu schließen.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT Abort();  
```  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** Corsym. idl, corsym. h  
  
## <a name="see-also"></a>Siehe auch

- [ISymUnmanagedWriter-Schnittstelle](isymunmanagedwriter-interface.md)
