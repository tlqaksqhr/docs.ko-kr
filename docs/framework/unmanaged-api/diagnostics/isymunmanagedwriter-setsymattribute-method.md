---
title: ISymUnmanagedWriter::SetSymAttribute 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.SetSymAttribute
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::SetSymAttribute
helpviewer_keywords:
- SetSymAttribute method [.NET Framework debugging]
- ISymUnmanagedWriter::SetSymAttribute method [.NET Framework debugging]
ms.assetid: 64d9b80e-b883-4539-89c7-03573185a1eb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bd1a55d4100d74b769b2bc1b8fe33d2042f5e739
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33428303"
---
# <a name="isymunmanagedwritersetsymattribute-method"></a>ISymUnmanagedWriter::SetSymAttribute 메서드
이름을 기반으로 사용자 지정 특성을 정의 합니다. 이러한 특성은 사용자 지정 특성 메타 데이터와 달리 기호 저장소에 보관 됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT SetSymAttribute(  
    [in] mdToken parent,  
    [in] const WCHAR *name,  
    [in] ULONG32 cData,  
    [in, size_is(cData)] unsigned char data[]);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `parent`  
 [in] 특성은 정의 메타 데이터 토큰입니다.  
  
 `name`  
 [in] 에 대 한 포인터는 `WCHAR` 특성 이름이 들어 있는입니다.  
  
 `cData`  
 [in] A `ULONG32` 크기를 표시 하는 `data` 배열입니다.  
  
 `data`  
 [in] 특성 값입니다.  
  
## <a name="return-value"></a>반환 값  
 메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.  
  
## <a name="requirements"></a>요구 사항  
 **Header:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>참고 항목  
 [ISymUnmanagedWriter 인터페이스](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
