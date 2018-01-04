---
title: "IMetaDataEmit::SetPinvokeMap 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.SetPinvokeMap
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::SetPinvokeMap
helpviewer_keywords:
- IMetaDataEmit::SetPinvokeMap method [.NET Framework metadata]
- SetPinvokeMap method [.NET Framework metadata]
ms.assetid: c6bfd574-1da3-4ba7-82f2-46ca5efcbaba
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ebf8363bc70d7303d2827e94befefe8a0ddd9573
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitsetpinvokemap-method"></a>IMetaDataEmit::SetPinvokeMap 메서드
설정 하거나 이전 호출에 정의 된 대로 메서드의 PInvoke 서명의 기능 변경 [imetadataemit:: Definepinvokemap](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepinvokemap-method.md)합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT SetPinvokeMap (   
    [in]  mdToken      tk,   
    [in]  DWORD        dwMappingFlags,  
    [in]  LPCWSTR      szImportName,   
    [in]  mdModuleRef  mrImportDLL   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `tk`  
 [in] `mdToken` 정보가 적용 되는 매핑.  
  
 `dwMappingFlags`  
 [in] PInvoke 하는 매핑을 수행 하는 데 사용 하는 플래그입니다. 이 비트 마스크의 `CorPinvokeMap` 값입니다.  
  
 `szImportName`  
 [in] 네이티브 DLL의 내보내기 대상의 이름입니다.  
  
 `mrImportDLL`  
 [in] `mdModuleRef` 토큰의 대상에 대 한 관리 되지 않는 리소스 DLL입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** Cor.h  
  
 **라이브러리:** MSCorEE.dll에서 리소스로 사용  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [IMetaDataEmit 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [IMetaDataEmit2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
