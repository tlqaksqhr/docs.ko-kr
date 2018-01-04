---
title: "ISymUnmanagedENCUpdate 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedENCUpdate
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedENCUpdate
helpviewer_keywords: ISymUnmanagedENCUpdate interface [.NET Framework debugging]
ms.assetid: 63a9ef45-01a6-46da-b958-5c6dc2dc232c
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f68d000824779fcffb90ec031b86b50e8c80eccd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedencupdate-interface"></a>ISymUnmanagedENCUpdate 인터페이스
편집 하며 계속 하기 기능에 대 한 기능을 제공합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[GetLocalVariableCount 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-getlocalvariablecount-method.md)|지역 변수의 개수를 가져옵니다.|  
|[GetLocalVariables 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-getlocalvariables-method.md)|지역 변수를 가져옵니다.|  
|[InitializeForEnc 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-initializeforenc-method.md)|처음 호출 하기 전에 계산 해야 메서드 경계 수는 [isymunmanagedencupdate:: Updatesymbolstore2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-updatesymbolstore2-method.md) 메서드.|  
|[UpdateMethodLines 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-updatemethodlines-method.md)|다시 컴파일되지 않은, 하지만 해당 줄 독립적으로 이동 하는 방법에 대 한 줄 정보를 업데이트할 수 있습니다. 각 문에 대 한 델타 허용 됩니다.|  
|[UpdateSymbolStore2 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-updatesymbolstore2-method.md)|컴파일러가 줄 정보 요구 사항을 충족 하는 프로그램 데이터베이스 (PDB) 스트립에서 수정 되지 않은 함수를 생략할 수 있습니다. 오래 된 PDB 줄 정보 및 모든 줄은 함수에 대 한 델타 올바른 줄 정보를 확인할 수 있습니다.|  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>참고 항목  
 [진단 기호 저장소 인터페이스](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
