---
title: "COINITIEE 열거형"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COINITIEE
api_location: mscoree.dll
api_type: COM
f1_keywords: COINITIEE
helpviewer_keywords: COINITIEE enumeration [.NET Framework metadata]
ms.assetid: 64264238-3b68-4bac-a887-36b552426a6c
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ad117c3efd31cc176281e571b7fde11229c097e9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="coinitiee-enumeration"></a>COINITIEE 열거형
사용 하는 상수를 지정 [CoInitializeEE](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md) 공용 언어 런타임을 초기화할 때.  
  
## <a name="syntax"></a>구문  
  
```  
typedef enum tagCOINITEE {  
   COINITEE_DEFAULT = 0x0,  
   COINITEE_DLL     = 0x1,  
   COINITEE_MAIN    = 0x2  
} COINITIEE;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`COINITEE_DEFAULT`|기본 초기화 모드입니다. 이 런타임을 초기화 하 고 기본 만듭니다 <xref:System.AppDomain>합니다.|  
|`COINITEE_DLL`|관리 되는 DLL을 실행 하려면를 초기화 합니다.|  
|`COINITEE_MAIN`|관리 되는 EXE를 실행 하도록를 초기화 합니다. 이 런타임을 초기화 만들지는 않습니다 기본 <xref:System.AppDomain>, exe 파일의 기본 루틴에 입력 한 후 생성 됩니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** Cor.h  
  
 **라이브러리:** MsCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [메타데이터 열거형](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
