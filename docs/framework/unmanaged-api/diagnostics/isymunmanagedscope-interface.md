---
title: "ISymUnmanagedScope 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedScope
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedScope
helpviewer_keywords: ISymUnmanagedScope interface [.NET Framework debugging]
ms.assetid: 3db7a220-cfe9-4810-8ca8-a094bb8e0f5b
topic_type: apiref
caps.latest.revision: "5"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: d25d62dd42e3e93124c9a3bd8945be265f192663
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedscope-interface"></a>ISymUnmanagedScope 인터페이스
메서드에 들어 있는 어휘 범위를 나타냅니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[GetChildren 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getchildren-method.md)|이 범위의 자식을 가져옵니다.|  
|[GetEndOffset 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getendoffset-method.md)|이 범위에 대 한 끝 오프셋을 가져옵니다.|  
|[GetLocalCount 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getlocalcount-method.md)|이 범위 내에 정의 된 지역 변수의 수를 가져옵니다.|  
|[GetLocals 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getlocals-method.md)|이 범위 내에 정의 된 지역 변수를 가져옵니다.|  
|[GetMethod 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getmethod-method.md)|이 범위를 포함 하는 메서드를 가져옵니다.|  
|[GetNamespaces 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getnamespaces-method.md)|이 범위 내에서 사용 되는 네임 스페이스를 가져옵니다.|  
|[GetParent 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getparent-method.md)|이 범위의 상위 범위를 가져옵니다.|  
|[GetStartOffset 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getstartoffset-method.md)|이 범위에 대 한 시작 오프셋을 가져옵니다.|  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>참고 항목  
 [진단 기호 저장소 인터페이스](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [ISymUnmanagedScope2 인터페이스](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-interface.md)
