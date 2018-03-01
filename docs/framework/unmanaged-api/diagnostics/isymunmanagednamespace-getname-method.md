---
title: "ISymUnmanagedNamespace::GetName 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ISymUnmanagedNamespace.GetName
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedNamespace::GetName
helpviewer_keywords:
- ISymUnmanagedNamespace::GetName method [.NET Framework debugging]
- GetName method, ISymUnmanagedNamespace interface [.NET Framework debugging]
ms.assetid: 657bf91d-005a-4ea4-9298-04d1291c0bc3
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 37b29e71a9a1185a7080f71b1621a07dd7ae41a2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagednamespacegetname-method"></a>ISymUnmanagedNamespace::GetName 메서드
이 네임 스페이스의 이름을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetName(  
    [in]  ULONG32  cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName),  
        length_is(*pcchName)] WCHAR szName[]);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `cchName`  
 [in] A `ULONG32` 크기를 표시 하는 `szName` 버퍼입니다.  
  
 `pcchName`  
 [out] 에 대 한 포인터는 `ULONG32` 문자의 null 종결을 포함 하 여 네임 스페이스 이름을 포함 하는 데 필요한 버퍼 크기를 받는 합니다.  
  
 `szName`  
 [out] 네임 스페이스 이름을 포함 하는 버퍼에 대 한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>참고 항목  
 [ISymUnmanagedNamespace 인터페이스](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md)
