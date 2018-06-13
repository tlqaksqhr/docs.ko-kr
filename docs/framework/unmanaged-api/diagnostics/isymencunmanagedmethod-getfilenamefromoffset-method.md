---
title: ISymENCUnmanagedMethod::GetFileNameFromOffset 메서드
ms.date: 03/30/2017
api_name:
- ISymENCUnmanagedMethod.GetFileNameFromOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymENCUnmanagedMethod::GetFileNameFromOffset
helpviewer_keywords:
- GetFileNameFromOffset method [.NET Framework debugging]
- ISymENCUnmanagedMethod::GetFileNameFromOffset method [.NET Framework debugging]
ms.assetid: 00e2e194-12f5-436e-a997-2b9d3e844d4f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: db3e9cfa73672920ff70d9128541a8f513fca00f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33432658"
---
# <a name="isymencunmanagedmethodgetfilenamefromoffset-method"></a>ISymENCUnmanagedMethod::GetFileNameFromOffset 메서드
오프셋와 관련 된 선에 대 한 파일 이름을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetFileNameFromOffset(  
    [in]  ULONG32  dwOffset,  
    [in]  ULONG32  cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName),  
       length_is(*pcchName)] WCHAR szName[]);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `dwOffset`  
 [in] A `ULONG32` 오프셋을 포함 하는 합니다.  
  
 `cchName`  
 [in] A `ULONG32` 크기를 표시 하는 `szName` 버퍼입니다.  
  
 `pcchName`  
 [out] 에 대 한 포인터는 `ULONG32` 문자의 파일 이름을 포함 하는 데 필요한 버퍼 크기를 받는 합니다.  
  
 `szName`  
 [out] 파일 이름을 포함 하는 버퍼입니다.  
  
## <a name="return-value"></a>반환 값  
 메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.  
  
## <a name="requirements"></a>요구 사항  
 **Header:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>참고 항목  
 [ISymENCUnmanagedMethod 인터페이스](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-interface.md)
