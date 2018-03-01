---
title: "ForwardTranslateAccelerator 함수 (WPF 관리 되지 않는 API 참조)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- cpp
api_name:
- ForwardTranslateAccelerator
api_location:
- PresentationHost_v0400.dll
ms.assetid: fff47a86-9d9f-4176-9530-10e1876e393f
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: cca9c78eaf13e04d22fce9f61ce4a7ab9ee09769
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="forwardtranslateaccelerator-function-wpf-unmanaged-api-reference"></a>ForwardTranslateAccelerator 함수 (WPF 관리 되지 않는 API 참조)
이 API는 Windows Presentation Foundation (WPF) 인프라를 지원 하며 사용자 코드에서 직접 사용할 수 없습니다.  
  
 Windows 관리에 대 한 Windows Presentation Foundation (WPF) 인프라에서 사용 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT ForwardTranslateAccelerator(  
   MSG* pMsg,   
   VARIANT_BOOL appUnhandled  
)  
```  
  
#### <a name="parameters"></a>매개 변수  
 pMsg  
 메시지에 대 한 포인터입니다.  
  
 appUnhandled  
 `true`응용 프로그램 입력된 메시지를 처리할 수 있는 기회가 부여 이미 하지만, 처리 되지 않은 경우 그렇지 않으면 `false`합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [.NET Framework 시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **DLL:**  
  
 .NET framework 3.0 및 3.5: PresentationHostDLL.dll  
  
 .NET Framework 4 이상: PresentationHost_v0400.dll  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [F 관리되지 않는 API 참조](../../../../docs/framework/wpf/advanced/wpf-unmanaged-api-reference.md)
