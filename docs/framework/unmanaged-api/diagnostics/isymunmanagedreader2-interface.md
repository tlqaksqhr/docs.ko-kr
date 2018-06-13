---
title: ISymUnmanagedReader2 인터페이스
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader2
helpviewer_keywords:
- ISymUnmanagedReader2 interface [.NET Framework debugging]
ms.assetid: a01a881b-82a3-4b3e-a3a9-9dc305c2e5f7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1dfc67ecf1eeb9ea5a19c98a8c378e73021da6c8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33426830"
---
# <a name="isymunmanagedreader2-interface"></a>ISymUnmanagedReader2 인터페이스
문서, 메서드 및 기호 저장소 내의 변수에 대 한 액세스를 제공 하는 기호 판독기를 나타냅니다. 이 인터페이스에서 확장 된 [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) 인터페이스입니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[GetMethodByVersionPreRemap 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-getmethodbyversionpreremap-method.md)|메서드 토큰이 편집 하며 계속 하기 버전 번호를 지정 된 기호 판독기 메서드를 가져옵니다.|  
|[GetMethodsInDocument 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-getmethodsindocument-method.md)|줄 정보를 제공된 된 문서에 있는 모든 메서드를 가져옵니다.|  
|[GetSymAttributePreRemap 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-getsymattributepreremap-method.md)|이름을 기반으로 사용자 지정 특성을 가져옵니다.|  
  
## <a name="requirements"></a>요구 사항  
 **Header:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>참고 항목  
 [진단 기호 저장소 인터페이스](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [ISymUnmanagedReader 인터페이스](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
