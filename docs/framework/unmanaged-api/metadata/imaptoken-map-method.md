---
title: IMapToken::Map 메서드
ms.date: 03/30/2017
api_name:
- IMapToken.Map
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMapToken::Map
helpviewer_keywords:
- IMapToken::Map method [.NET Framework metadata]
- Map method [.NET Framework metadata]
ms.assetid: b9b4bf2f-1098-43d6-9619-a99b4bda1940
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f2633bfadaabf208a2b86fda83375c3a136b93b9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="imaptokenmap-method"></a>IMapToken::Map 메서드
메타 데이터 서명을 사용 하 여 어셈블리 간의 관계를 매핑합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT Map (  
    [in]  mdToken tkImp,   
    [in]  mdToken tkEmit  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `tkImp`  
 [in] 가져온된 코드 개체를 나타내는 메타 데이터 토큰입니다.  
  
 `tkEmit`  
 [in] 내보낸된 코드 개체를 나타내는 메타 데이터 토큰입니다.  
  
## <a name="remarks"></a>설명  
 병합 하는 동안 발생 토큰 다시 매핑 가져온된 (원본) 메타 데이터 범위에서 원래 토큰 범위 지정 및 내보낸된 (대상) 메타 데이터 범위에서 새 토큰 범위가 지정 됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** Cor.h  
  
 **라이브러리:** MsCorEE.dll에서 리소스로 사용  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [IMapToken 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md)
