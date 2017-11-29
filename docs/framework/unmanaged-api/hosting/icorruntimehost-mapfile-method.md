---
title: "ICorRuntimeHost::MapFile 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorRuntimeHost.MapFile
api_location: mscoree.dll
api_type: COM
f1_keywords: ICorRuntimeHost::MapFile
helpviewer_keywords:
- ICorRuntimeHost::MapFile method [.NET Framework hosting]
- MapFile method [.NET Framework hosting]
ms.assetid: 45ae0502-0a31-4342-b7e3-f36e1cf738f3
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: fd156aac23cdca446bcf2666ce36e91fef6d5392
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icorruntimehostmapfile-method"></a>ICorRuntimeHost::MapFile 메서드
지정된 된 파일을 메모리에 매핑합니다. 이 메서드는 사용되지 않습니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT MapFile(  
    [in]  HANDLE    hFile,  
    [out] HMODULE*  hMapAddress  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `hFile`  
 [in] 매핑할 파일의 핸들입니다.  
  
 `hMapAddress`  
 [out] 매핑 파일을 시작 하는 시작 메모리 주소를 지정 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** MSCorEE.h  
  
 **라이브러리:** MSCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:** 1.0, 1.1  
  
## <a name="see-also"></a>참고 항목  
 [ICorRuntimeHost 인터페이스](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
