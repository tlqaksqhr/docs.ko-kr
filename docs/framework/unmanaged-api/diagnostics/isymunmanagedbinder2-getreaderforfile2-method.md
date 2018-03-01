---
title: "ISymUnmanagedBinder2::GetReaderForFile2 메서드"
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
- ISymUnmanagedBinder2.GetReaderForFile2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder2::GetReaderForFile2
helpviewer_keywords:
- ISymUnmanagedBinder2::GetReaderForFile2 method [.NET Framework debugging]
- GetReaderForFile2 method [.NET Framework debugging]
ms.assetid: dd92dcaf-403c-464d-a254-21594985dddd
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 270a154c40b85ad4774bececf12685393f4d6c58
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedbinder2getreaderforfile2-method"></a>ISymUnmanagedBinder2::GetReaderForFile2 메서드
메타 데이터 인터페이스와 파일 이름을 제공 올바른 반환 <<!--zz xref:ISymUnmanagedReader --> `ISymUnmanagedReader`> 인터페이스를 모듈와 관련 된 디버깅 기호를 읽습니다.  
  
 이 방법은 보다 프로그램 데이터베이스 (PDB) 파일에 대 한 보다 광범위 한 검색을 제공 된 [isymunmanagedbinder:: Getreaderforfile](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md) 메서드.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetReaderForFile2(  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *fileName,  
    [in]  const WCHAR  *searchPath,  
    [in]  ULONG32      searchPolicy,  
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
  
 `pRetVal`  
 [out] 설정 된 포인터가 반환 된 <<!--zz xref:ISymUnmanagedReader --> `ISymUnmanagedReader`> 인터페이스입니다.  
  
## <a name="return-value"></a>반환 값  
 메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** CorSym.idl, CorSym.h  
  
## <a name="remarks"></a>설명  
 이 버전의 메서드 오른쪽 모듈에 있지 않은 영역에서 PDB 파일을 검색할 수 있습니다. 검색 정책 결합 하 여 제어할 수 있습니다 [CorSymSearchPolicyAttributes](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md)합니다. 예를 들어 `AllowReferencePathAccess | AllowSymbolServerAccess` 옆에 있는 실행 파일 및 기호 서버에서 pdb 되지만 않습니다 레지스트리 나 실행 파일의 경로 사용 합니다. 경우는 `searchPath` 매개 변수를 제공,이 디렉터리는 항상 검색 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [ISymUnmanagedBinder2 인터페이스](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)  
 [GetReaderForFile 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md)
