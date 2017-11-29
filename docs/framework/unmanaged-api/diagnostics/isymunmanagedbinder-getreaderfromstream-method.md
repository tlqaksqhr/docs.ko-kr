---
title: "ISymUnmanagedBinder::GetReaderFromStream 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedBinder.GetReaderFromStream
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedBinder::GetReaderFromStream
helpviewer_keywords:
- ISymUnmanagedBinder::GetReaderFromStream method [.NET Framework debugging]
- GetReaderFromStream method [.NET Framework debugging]
ms.assetid: aa38efd4-de7e-4482-a5d3-adc152093460
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 96bd12b69b84537415ddf2e0ae992ec179f32493
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedbindergetreaderfromstream-method"></a>ISymUnmanagedBinder::GetReaderFromStream 메서드
제공 되는 메타 데이터 인터페이스와 기호 저장소를 포함 하는 스트림을 올바른 반환 <<!--zz xref:ISymUnmanagedReader --> `ISymUnmanagedReader`> 지정 된 기호 저장소에서 기호 디버깅 읽을 구조입니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetReaderFromStream(  
    [in]  IUnknown  *importer,  
    [in]  IStream   *pstream,  
    [out,retval] ISymUnmanagedReader **pRetVal);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `importer`  
 [in] 메타 데이터 가져오기 인터페이스 포인터입니다.  
  
 `pstream`  
 [in] 기호 저장소를 포함 하는 스트림에 대 한 포인터입니다.  
  
 `pRetVal`  
 [out] 설정 된 포인터가 반환 된 <<!--zz xref:ISymUnmanagedReader --> `ISymUnmanagedReader`> 인터페이스입니다.  
  
## <a name="return-value"></a>반환 값  
 메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>참고 항목  
 [ISymUnmanagedBinder 인터페이스](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)
