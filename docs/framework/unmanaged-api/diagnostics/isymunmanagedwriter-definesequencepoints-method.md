---
title: "ISymUnmanagedWriter::DefineSequencePoints 메서드"
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
- ISymUnmanagedWriter.DefineSequencePoints
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineSequencePoints
helpviewer_keywords:
- DefineSequencePoints method [.NET Framework debugging]
- ISymUnmanagedWriter::DefineSequencePoints method [.NET Framework debugging]
ms.assetid: 64202baf-be6b-40ba-8162-8cc6c0c9b8e1
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2e1dcc427a6d034ce108ca66f71cc24b1050a72f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedwriterdefinesequencepoints-method"></a>ISymUnmanagedWriter::DefineSequencePoints 메서드
현재 메서드 내에서 시퀀스 위치 그룹을 정의합니다. 각 시작 줄 및 시작 열 메서드 내에서 문의 시작을 정의 합니다. 각각 끝 줄과 끝 열 메서드 내에서 문의 끝을 정의 합니다. 배열은 오프셋의 오름차순으로 정렬 되어야 합니다. 오프셋은 항상 바이트 단위로 메서드의 시작 부분에서 측정 됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT DefineSequencePoints(  
    [in] ISymUnmanagedDocumentWriter*  document,  
    [in] ULONG32 spCount,  
    [in, size_is(spCount)] ULONG32     offsets[],  
    [in, size_is(spCount)] ULONG32     lines[],  
    [in, size_is(spCount)] ULONG32     columns[],  
    [in, size_is(spCount)] ULONG32     endLines[],  
    [in, size_is(spCount)] ULONG32     endColumns[]);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `document`  
 [in] 시퀀스 위치를 정의 하는 문서 개체입니다.  
  
 `spCount`  
 [in] A `ULONG32` 각각의 크기를 표시 하는 `offsets`, `lines`, `columns`, `endLines`, 및 `endColumns` 버퍼입니다.  
  
 `offsets`  
 [in] 메서드의 시작 부분에서 측정 한 시퀀스 위치 오프셋입니다.  
  
 `lines`  
 [in] 시퀀스 위치의 시작 줄 번호입니다.  
  
 `columns`  
 [in] 시퀀스 위치의 시작 열 번호를 지정 합니다.  
  
 `endLines`  
 [in] 시퀀스 위치의 끝 줄 번호를 지정 합니다. 이 매개 변수는 선택적 요소입니다.  
  
 `endColumns`  
 [in] 시퀀스 위치의 끝 열 번호를 지정 합니다. 이 매개 변수는 선택적 요소입니다.  
  
## <a name="return-value"></a>반환 값  
 메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>참고 항목  
 [ISymUnmanagedWriter 인터페이스](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
