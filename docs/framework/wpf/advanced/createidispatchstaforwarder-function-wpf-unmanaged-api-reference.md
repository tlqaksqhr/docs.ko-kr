---
title: CreateIDispatchSTAForwarder 함수 (WPF 관리 되지 않는 API 참조)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- CreateIDispatchSTAForwarder
api_location:
- PresentationHost_v0400.dll
ms.assetid: 57a02dfa-f091-4ace-9c06-1f4ab52b3527
ms.openlocfilehash: f7e45d5cafa40ba147fe39888e74a67ac9f95c5b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33536653"
---
# <a name="createidispatchstaforwarder-function-wpf-unmanaged-api-reference"></a>CreateIDispatchSTAForwarder 함수 (WPF 관리 되지 않는 API 참조)
이 API는 Windows Presentation Foundation (WPF) 인프라를 지원 하며 사용자 코드에서 직접 사용할 수 없습니다.  
  
 스레드 및 창 관리를 위한 Windows Presentation Foundation (WPF) 인프라에서 사용 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT CreateIDispatchSTAForwarder(  
   __in IDispatch *pDispatchDelegate,   
   __deref_out IDispatch **ppForwarder  
)  
```  
  
#### <a name="parameters"></a>매개 변수  
  
## <a name="property-valuereturn-value"></a>속성 값/반환 값  
 pDispatchDelegate  
 에 대 한 포인터는 `IDispatch` 인터페이스입니다.  
  
 ppForwarder  
 주소에 대 한 포인터는 `IDispatch` 인터페이스입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [.NET Framework 시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **DLL:**  
  
 .NET framework 3.0 및 3.5: PresentationHostDLL.dll  
  
 .NET Framework 4 이상: PresentationHost_v0400.dll  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [F 관리되지 않는 API 참조](../../../../docs/framework/wpf/advanced/wpf-unmanaged-api-reference.md)
