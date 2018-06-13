---
title: ISymUnmanagedWriter::Close 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.Close
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::Close
helpviewer_keywords:
- Close method, ISymUnmanagedWriter interface [.NET Framework debugging]
- ISymUnmanagedWriter::Close method [.NET Framework debugging]
ms.assetid: 4cce59e1-80b9-4fc4-b3aa-126f1c5876bc
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 30747fa25528f5679264ebfb67addf401b7d01d9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33426331"
---
# <a name="isymunmanagedwriterclose-method"></a>ISymUnmanagedWriter::Close 메서드
기호를 기호 저장소에 커밋한 후 기호 작성기를 닫습니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT Close();  
```  
  
## <a name="return-value"></a>반환 값  
 메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.  
  
## <a name="remarks"></a>설명  
 이 호출 후 기호 작성기 추가로 업데이트할 됩니다. 사용 하 여 기호를 커밋하지 않고 기호 작성기를 닫으려면는 [isymunmanagedwriter:: Abort](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-abort-method.md) 메서드 대신 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **Header:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>참고 항목  
 [ISymUnmanagedWriter 인터페이스](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
