---
title: "ISymUnmanagedDocument::GetSourceRange 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedDocument.GetSourceRange
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedDocument::GetSourceRange
helpviewer_keywords:
- ISymUnmanagedDocument::GetSourceRange method [.NET Framework debugging]
- GetSourceRange method [.NET Framework debugging]
ms.assetid: 20fefee7-1040-41ba-93dc-bd42f68b90c2
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: dcddebbca74bb94bd2411038a02b900b2f64f2d5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanageddocumentgetsourcerange-method"></a>ISymUnmanagedDocument::GetSourceRange 메서드
지정 된 버퍼로 포함된 리소스의 지정된 된 범위를 반환합니다. 버퍼 소스를 저장할 수 있을 만큼 크기가 커야 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetSourceRange(  
    [in]  ULONG32  startLine,  
    [in]  ULONG32  startColumn,  
    [in]  ULONG32  endLine,  
    [in]  ULONG32  endColumn,  
    [in]  ULONG32  cSourceBytes,  
    [out] ULONG32  *pcSourceBytes,  
    [out, size_is(cSourceBytes),  
        length_is(*pcSourceBytes)] BYTE source[]);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `startLine`  
 [in] 현재 문서의 시작 줄입니다.  
  
 `startColumn`  
 [in] 현재 문서의 시작 열입니다.  
  
 `endLine`  
 [in] 현재 문서에서 마지막 줄입니다.  
  
 `endColumn`  
 [in] 현재 문서에서 마지막 열입니다.  
  
 `cSourceBytes`  
 [in] 원본 바이트의 크기입니다.  
  
 `pcSourceBytes`  
 [out] 원본 크기를 받는 변수에 대 한 포인터입니다.  
  
 `source`  
 [out] 크기와 소스 문서의 바이트 단위로 지정 된 범위의 길이입니다.  
  
## <a name="return-value"></a>반환 값  
 메서드가 성공 하면 S_OK입니다.  
  
## <a name="see-also"></a>참고 항목  
 [ISymUnmanagedDocument 인터페이스](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
