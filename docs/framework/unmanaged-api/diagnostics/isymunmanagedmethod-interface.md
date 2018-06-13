---
title: ISymUnmanagedMethod 인터페이스
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod
helpviewer_keywords:
- ISymUnmanagedMethod interface [.NET Framework debugging]
ms.assetid: f204d74c-cc79-4092-83bb-60654be95649
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 728acc09f739fe567fca4a2571cbabf1ba8838a2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33427433"
---
# <a name="isymunmanagedmethod-interface"></a>ISymUnmanagedMethod 인터페이스
기호 저장소 내의 메서드를 나타냅니다. 이 인터페이스는만 형식 관련 특성 대신 메서드의 기호 관련 특성에 대 한 액세스를 제공 합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[GetNamespace 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getnamespace-method.md)|이 메서드가 정의 된 네임 스페이스를 가져옵니다.|  
|[GetOffset 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getoffset-method.md)|문서 내에서 지정된 된 위치에 해당 하는이 메서드 내에서 오프셋을 반환 합니다.|  
|[GetParameters 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getparameters-method.md)|이 메서드에 대 한 매개 변수를 가져옵니다.|  
|[GetRanges 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getranges-method.md)|제공 되는 위치가 문서에는 위치가이 메서드에 설명 되어 있는 Microsoft intermediate language (MSIL)의 범위에 해당 하는 시작 및 종료 오프셋된 쌍의 배열을 반환 합니다.|  
|[GetRootScope 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getrootscope-method.md)|이 메서드 내에서 루트 어휘 범위를 가져옵니다. 이 범위는 전체 메서드를 포함합니다.|  
|[GetScopeFromOffset 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getscopefromoffset-method.md)|지정된 된 오프셋을 포함 하는이 메서드 내에서 최대 포함 어휘 범위를 가져옵니다.|  
|[GetSequencePointCount 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getsequencepointcount-method.md)|이 메서드 내에서 시퀀스 위치 수를 가져옵니다.|  
|[GetSequencePoints 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getsequencepoints-method.md)|이 메서드 내에서 모든 시퀀스 위치를 가져옵니다.|  
|[GetSourceStartEnd 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getsourcestartend-method.md)|이 방법의 원본에 대 한 시작 및 끝 문서 위치를 가져옵니다.|  
|[GetToken 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-gettoken-method.md)|이 메서드에 대 한 메타 데이터 토큰을 반환합니다.|  
  
## <a name="requirements"></a>요구 사항  
 **Header:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>참고 항목  
 [진단 기호 저장소 인터페이스](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
