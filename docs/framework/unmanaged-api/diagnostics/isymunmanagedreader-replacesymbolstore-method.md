---
title: "ISymUnmanagedReader::ReplaceSymbolStore 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedReader.ReplaceSymbolStore
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedReader::ReplaceSymbolStore
helpviewer_keywords:
- ReplaceSymbolStore method [.NET Framework debugging]
- ISymUnmanagedReader::ReplaceSymbolStore method [.NET Framework debugging]
ms.assetid: 43257761-8cb1-4eaf-8fb5-1f3980cb66cd
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 09bcad4898cf4d3310a96164bdc82006e185006f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedreaderreplacesymbolstore-method"></a>ISymUnmanagedReader::ReplaceSymbolStore 메서드
기존 기호 저장소를 델타 기호 저장소로 바꿉니다. 이 메서드는 비슷합니다는 [UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) 메서드를 제외 하 고 지정 된 델타 업데이트 보다는 완전 한 대체 역할도 합니다.  
  
> [!NOTE]
>  중 하나만 지정할 필요는 `filename` 또는 `pIStream` 두 매개 변수입니다. 경우 `filename` 지정, 기호 저장소는 해당 파일에 있는 기호도 업데이트 됩니다. 경우 `pIStream` 를 지정 된 저장소의 데이터로 업데이트 됩니다는 <xref:System.Runtime.InteropServices.ComTypes.IStream>합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT ReplaceSymbolStore (  
    [in] const WCHAR *filename,  
    [in] IStream *pIStream);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `filename`  
 [in] 기호 저장소를 포함 하는 파일의 이름입니다.  
  
 `pIStream`  
 [in] 대 안으로 사용 되는 파일 스트림을 `filename` 매개 변수입니다.  
  
## <a name="return-value"></a>반환 값  
 메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>참고 항목  
 [ISymUnmanagedReader 인터페이스](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
