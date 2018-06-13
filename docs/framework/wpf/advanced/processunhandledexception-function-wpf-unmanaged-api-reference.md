---
title: ProcessUnhandledException 함수 (WPF 관리 되지 않는 API 참조)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ProcessUnhandledException
api_location:
- PresentationHost_v0400.dll
ms.assetid: 495ce5f6-bb4d-4b30-807a-c3c35f1ca95c
ms.openlocfilehash: bcde3fe6d3fdc1749f29a5c9f7625f802dd49535
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33544526"
---
# <a name="processunhandledexception-function-wpf-unmanaged-api-reference"></a>ProcessUnhandledException 함수 (WPF 관리 되지 않는 API 참조)
이 API는 Windows Presentation Foundation (WPF) 인프라를 지원 하며 사용자 코드에서 직접 사용할 수 없습니다.  
  
 예외 처리를 위한 Windows Presentation Foundation (WPF) 인프라에서 사용 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
void __stdcall ProcessUnhandledException(  
   __in_ecount(1) BSTR errorMsg  
)  
```  
  
#### <a name="parameters"></a>매개 변수  
 errorMsg  
 오류 메시지입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [.NET Framework 시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **DLL:**  
  
 .NET framework 3.0 및 3.5: PresentationHostDLL.dll  
  
 .NET Framework 4 이상: PresentationHost_v0400.dll  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [F 관리되지 않는 API 참조](../../../../docs/framework/wpf/advanced/wpf-unmanaged-api-reference.md)
