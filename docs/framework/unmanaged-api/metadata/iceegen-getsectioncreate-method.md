---
title: "ICeeGen::GetSectionCreate 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICeeGen.GetSectionCreate
api_location: mscoree.dll
api_type: COM
f1_keywords: ICeeGen::GetSectionCreate
helpviewer_keywords:
- ICeeGen::GetSectionCreate method [.NET Framework metadata]
- GetSectionCreate method [.NET Framework metadata]
ms.assetid: 154b2460-59ce-4874-a9f2-1b3353486ac5
topic_type: apiref
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a069f65d3059bfa427ea20623ff9a2ac4049fd39
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="iceegengetsectioncreate-method"></a>ICeeGen::GetSectionCreate 메서드
생성 하 고 지정한 이름 및 플래그 값을 사용 하는 코드 섹션을 가져옵니다.  
  
 이 메서드는 사용 되지 않으며 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetSectionCreate (  
    [in]  const char     *name,  
    [in]  DWORD          flags,  
    [out] HCEESECTION    *section  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `name`  
 [in] 만들 섹션의 이름을 지정 하는 문자열에 대 한 포인터입니다.  
  
 `flags`  
 [in] 옵션을 지정 하는 플래그입니다.  
  
 `section`  
 [out] 새로 생성된 된 코드 섹션에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  
 호출 `GetSectionCreate` 다른 방법으로 처리 되지 않는 섹션 특별 한 요구 사항이 있는 경우에 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** Cor.h  
  
 **라이브러리:** MsCorEE.dll에서 리소스로 사용  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICeeGen 인터페이스](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
