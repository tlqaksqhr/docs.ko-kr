---
title: "ISymUnmanagedBinder 인터페이스"
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
- ISymUnmanagedBinder
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder
helpviewer_keywords:
- ISymUnmanagedBinder interface [.NET Framework debugging]
ms.assetid: b22fbe19-b30f-4696-8175-e6b91da9edab
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 79d3758f57976d08d4599de500e2e12e4d67cb4b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedbinder-interface"></a>ISymUnmanagedBinder 인터페이스
비관리 코드의 기호 바인더를 나타냅니다.  
  
> [!IMPORTANT]
>  것은 신뢰할 수 없는 소스에서 프로그램 데이터베이스 (PDB) 파일을 열려면 보안상 위험 합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[GetReaderForFile 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md)|메타 데이터 인터페이스와 파일 이름을 제공 올바른 반환 [ISymUnmanagedReader](isymunmanagedreader-interface.md) 구조는 모듈에 연결 된 디버깅 기호는 읽기입니다.|  
|[GetReaderFromStream 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderfromstream-method.md)|제공 되는 메타 데이터 인터페이스와 기호 저장소를 포함 하는 스트림을 올바른 반환 [ISymUnmanagedReader](isymunmanagedreader-interface.md) 디버깅 읽을 구조에서 지정 된 기호 저장소 기호입니다.|  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>참고 항목  
 [진단 기호 저장소 인터페이스](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [ISymUnmanagedBinder2 인터페이스](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)  
 [ISymUnmanagedBinder3 인터페이스](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-interface.md)
