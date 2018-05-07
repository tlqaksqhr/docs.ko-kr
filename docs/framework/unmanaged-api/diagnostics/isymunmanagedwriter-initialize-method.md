---
title: ISymUnmanagedWriter::Initialize 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.Initialize
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::Initialize
helpviewer_keywords:
- ISymUnmanagedWriter::Initialize method [.NET Framework debugging]
- Initialize method, ISymUnmanagedWriter interface [.NET Framework debugging]
ms.assetid: e0ebd793-3764-4df0-8f12-0e95f60b9eae
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 44046560f4f788c4a7d695ff18c9c01740fea35a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="isymunmanagedwriterinitialize-method"></a>ISymUnmanagedWriter::Initialize 메서드
이 작성기를 연결, 될 메타 데이터 내보내기 인터페이스를 설정 하 고 디버깅 기호를 기록할 출력 파일 이름을 설정 합니다.  
  
 이 메서드를 한 번만 호출할 수 있습니다 및 다른 기록기 메서드보다 먼저 호출 해야 합니다. 일부 작성기에는 파일 이름이 필요할 수 있습니다. 그러나이 메서드에 파일 이름을 사용 하지 않는 작성기에 나쁜 영향 없이 항상 파일 이름을 전달할 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT Initialize(  
    [in] IUnknown     *emitter,  
    [in] const WCHAR  *filename,  
    [in] IStream      *pIStream,  
    [in] BOOL         fFullBuild);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `emitter`  
 [in] 메타 데이터 내보내기 인터페이스에 대 한 포인터입니다.  
  
 `filename`  
 [in] 에 디버깅 기호가 쓰여진 파일 이름입니다. 파일 이름을 사용하지 않는 작성기에 대해 파일 이름이 지정되면 이 매개 변수는 무시됩니다.  
  
 `pIStream`  
 [in] 기호 작성기를 지정 하는 경우에 대 한 기호를 내보냅니다는 주어진 <xref:System.Runtime.InteropServices.ComTypes.IStream> 대신에 지정 된 파일에는 `filename` 매개 변수입니다. `pIStream` 매개 변수는 선택적 요소입니다.  
  
 `fFullBuild`  
 [in] `true` 이것이 전체를 다시 빌드해야 합니다. `false` 증분 컴파일을 이것이 합니다.  
  
## <a name="return-value"></a>반환 값  
 메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.  
  
## <a name="requirements"></a>요구 사항  
 **Header:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>참고 항목  
 [ISymUnmanagedWriter 인터페이스](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 [Initialize2 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-initialize2-method.md)
