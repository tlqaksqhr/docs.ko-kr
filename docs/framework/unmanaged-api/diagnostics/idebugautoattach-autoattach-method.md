---
title: "IDebugAutoAttach::AutoAttach 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IDebugAutoAttach.AutoAttach
api_location: diasymreader.dll
api_type: COM
f1_keywords: IDebugAutoAttach::AutoAttach
helpviewer_keywords:
- AutoAttach method [.NET Framework debugging]
- IDebugAutoAttach::AutoAttach method [.NET Framework debugging]
ms.assetid: 3cf3bd9c-7d88-4afa-a476-94cdc7609aa6
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 359aaf96c42a661657028d508f096f9625d4ba71
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="idebugautoattachautoattach-method"></a>IDebugAutoAttach::AutoAttach 메서드
서버에서 호출한 디버거 자동 수행 연결 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT AutoAttach  
(  
    [in]  REFGUID   guidPort,  
    [in]  DWORD     dwPid,  
    [in]  AUTOATTACH_PROGRAM_TYPE dwProgramType,  
    [in]  DWORD     dwProgramId,  
    [in]  LPCWSTR   pszSessionId  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `guidPort`  
 [in] 항상으로 설정 `GUID_NULL`합니다.  
  
 `dwPid`  
 [in] 프로세스 ID, 일반적으로 사용 하 여 검색 된 `GetCurrentProcessId` 함수입니다.  
  
 `dwProgramType`  
 [in] 프로그램 종류: `AUTOATTACH_PROGRAM_WIN32`, `AUTOATTACH_PROGRAM_COMPLUS`, 또는 `AUTOATTACH_PROGRAM_UNKNOWN`합니다.  
  
 `dwProgramId`  
 [in] 프로그램 id입니다.  
  
 `pszSessionId`  
 [in] Debug 동사에서 전달 된 문자열입니다.  
  
## <a name="return-value"></a>반환 값  
 메서드가 성공 하면 S_OK입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** DbgAutoAttach.h  
  
## <a name="see-also"></a>참고 항목  
 [IDebugAutoAttach 인터페이스](../../../../docs/framework/unmanaged-api/diagnostics/idebugautoattach-interface.md)
