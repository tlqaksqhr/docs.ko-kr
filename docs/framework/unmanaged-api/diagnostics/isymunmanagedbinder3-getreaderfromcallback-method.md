---
title: "ISymUnmanagedBinder3::GetReaderFromCallback 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedBinder3.GetReaderFromCallback
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedBinder3::GetReaderFromCallback
helpviewer_keywords:
- GetReaderFromCallback method [.NET Framework debugging]
- ISymUnmanagedBinder3::GetReaderFromCallback method [.NET Framework debugging]
ms.assetid: 4ef83bd2-3d8e-499e-8a12-d9d6fd6ced30
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 648559936259e7412011f9fb7613bd0e938e4ecb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedbinder3getreaderfromcallback-method"></a>ISymUnmanagedBinder3::GetReaderFromCallback 메서드
구현 하거나 콜백을 통해 하거나 제공을 사용 하면는 `IID_IDiaReadExeAtRVACallback` 또는 `IID_IDiaReadExeAtOffsetCallback` 메모리에서 디버그 디렉터리 정보를 얻을 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetReaderFromCallback(  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *fileName,  
    [in]  const WCHAR  *searchPath,  
    [in]  ULONG32      searchPolicy,  
    [in]  IUnknown     *callback,  
    [out,retval] ISymUnmanagedReader  **pRetVal);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `importer`  
 [in] 메타 데이터 가져오기 인터페이스 포인터입니다.  
  
 `fileName`  
 [in] 파일 이름에 대 한 포인터입니다.  
  
 `searchPath`  
 [in] 검색 경로에 대 한 포인터입니다.  
  
 `searchPolicy`  
 [in] 값은 [CorSymSearchPolicyAttributes](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md) 기호 판독기에 대 한 검색을 수행할 때 사용할 정책을 지정 하는 열거형입니다.  
  
 `callback`  
 [in] 콜백 함수에 대 한 포인터입니다.  
  
 `pRetVal`  
 [out] 설정 된 포인터를 반환 되 [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) 인터페이스입니다.  
  
## <a name="return-value"></a>반환 값  
 메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** CorSym.idl  
  
## <a name="see-also"></a>참고 항목  
 [ISymUnmanagedBinder3 인터페이스](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-interface.md)
