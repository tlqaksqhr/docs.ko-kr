---
title: ISymUnmanagedReader::GetUserEntryPoint 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetUserEntryPoint
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetUserEntryPoint
helpviewer_keywords:
- GetUserEntryPoint method [.NET Framework debugging]
- ISymUnmanagedReader::GetUserEntryPoint method [.NET Framework debugging]
ms.assetid: 3fd3a34c-d176-46e9-9996-fb1646cff9b0
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7b4c334d82320066bf9459907660fe6b7e2acefd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33425323"
---
# <a name="isymunmanagedreadergetuserentrypoint-method"></a>ISymUnmanagedReader::GetUserEntryPoint 메서드
있는 경우 모듈의 사용자 진입점으로 지정 된 메서드를 반환 합니다. 예를 들어이 메서드는 컴파일러에서 생성 된 스텁이 main 메서드 전에 아닌 사용자의 주요 메서드 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetUserEntryPoint (  
    [out, retval]  mdMethodDef  *pToken);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pToken`  
 [out] 진입점을 수신 하는 변수에 대 한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.  
  
## <a name="requirements"></a>요구 사항  
 **Header:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>참고 항목  
 [ISymUnmanagedReader 인터페이스](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
