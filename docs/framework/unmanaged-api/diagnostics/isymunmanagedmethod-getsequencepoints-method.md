---
title: ISymUnmanagedMethod::GetSequencePoints 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetSequencePoints
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetSequencePoints
helpviewer_keywords:
- ISymUnmanagedMethod::GetSequencePoints method [.NET Framework debugging]
- GetSequencePoints method [.NET Framework debugging]
ms.assetid: f909ac48-3d8f-49fb-a369-e3d9959151cd
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c9a35f35d7aea34c0ef08c30415fde75fe71e645
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33426052"
---
# <a name="isymunmanagedmethodgetsequencepoints-method"></a>ISymUnmanagedMethod::GetSequencePoints 메서드
이 메서드 내에서 모든 시퀀스 위치를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetSequencePoints(  
    [in]  ULONG32  cPoints,  
    [out] ULONG32  *pcPoints,  
    [in, size_is(cPoints)] ULONG32  offsets[],  
    [in, size_is(cPoints)] ISymUnmanagedDocument* documents[],  
    [in, size_is(cPoints)] ULONG32  lines[],  
    [in, size_is(cPoints)] ULONG32  columns[],  
    [in, size_is(cPoints)] ULONG32  endLines[],  
    [in, size_is(cPoints)] ULONG32  endColumns[]);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `cPoints`  
 [in] A `ULONG32` 의 크기를 받는 `offsets`, `documents`, `lines`, `columns`, `endLines`, 및 `endColumns` 배열입니다.  
  
 `pcPoints`  
 [out] 에 대 한 포인터는 `ULONG32` 시퀀스 위치를 포함 하는 데 필요한 버퍼의 길이 받는입니다.  
  
 `offsets`  
 [in] 시퀀스 위치에 대 한 메서드의 시작 부분에서 MSIL (language) 오프셋을 중간 Microsoft 저장할 배열입니다.  
  
 `documents`  
 [in] 시퀀스 위치가 있는 문서를 저장할 배열입니다.  
  
 `lines`  
 [in] 에 시퀀스 위치가 있는 문서의 줄을 저장할 배열입니다.  
  
 `columns`  
 [in] 시퀀스 위치가 있는 문서의에서 열을 저장 하는 배열입니다.  
  
 `endLines`  
 [in] 시퀀스 위치가 끝나는 문서의 줄 배열입니다.  
  
 `endColumns`  
 [in] 시퀀스 위치가 끝나는 문서의 열 배열입니다.  
  
## <a name="return-value"></a>반환 값  
 메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.  
  
## <a name="requirements"></a>요구 사항  
 **Header:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>참고 항목  
 [ISymUnmanagedMethod 인터페이스](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
