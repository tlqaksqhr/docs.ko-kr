---
title: "ISymUnmanagedNamespace::GetVariables 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedNamespace.GetVariables
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedNamespace::GetVariables
helpviewer_keywords:
- ISymUnmanagedNamespace::GetVariables method [.NET Framework debugging]
- GetVariables method, ISymUnmanagedNamespace interface [.NET Framework debugging]
ms.assetid: ea7c1617-f3ce-4220-8288-f2b50eaf0f0f
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 6f2de9f683a9ce667b4b72c94204d39082cdaee4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagednamespacegetvariables-method"></a>ISymUnmanagedNamespace::GetVariables 메서드
이 네임 스페이스 내에서 전역 범위에서 정의 된 모든 변수를 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetVariables(  
    [in]  ULONG32  cVars,  
    [out] ULONG32  *pcVars,  
    [out, size_is(cVars), length_is(*pcVars)]  
        ISymUnmanagedVariable *pVars[]);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `cVars`  
 [in] A `ULONG32` 크기를 표시 하는 `pVars` 배열입니다.  
  
 `pcVars`  
 [out] 에 대 한 포인터는 `ULONG32` 네임 스페이스를 포함 하는 데 필요한 버퍼의 크기를 받는 합니다.  
  
 `pVars`  
 [out] 네임 스페이스를 포함 하는 버퍼에 대 한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>참고 항목  
 [ISymUnmanagedNamespace 인터페이스](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md)
