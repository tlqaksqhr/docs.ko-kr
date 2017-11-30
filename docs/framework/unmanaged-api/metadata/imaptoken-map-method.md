---
title: "IMapToken::Map 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMapToken.Map
api_location: mscoree.dll
api_type: COM
f1_keywords: IMapToken::Map
helpviewer_keywords:
- IMapToken::Map method [.NET Framework metadata]
- Map method [.NET Framework metadata]
ms.assetid: b9b4bf2f-1098-43d6-9619-a99b4bda1940
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 2e3a9701bab27764803442a3cd0c24c4e412deaf
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
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
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [IMapToken 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md)
