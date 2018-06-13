---
title: INotifyConnection2::UnregisterNotifySource 메서드
ms.date: 03/30/2017
api_name:
- INotifyConnection2.UnregisterNotifySource
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifyConnection2::UnregisterNotifySource
helpviewer_keywords:
- INotifyConnection2::UnregisterNotifySource method [.NET Framework debugging]
- UnregisterNotifySource method [.NET Framework debugging]
ms.assetid: 2fc6c715-646f-41fd-9c12-c59b40575269
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c4b4f90f918c872f3227ac22f4cccadcbf3194a0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33425482"
---
# <a name="inotifyconnection2unregisternotifysource-method"></a>INotifyConnection2::UnregisterNotifySource 메서드
연결에서 지정 된 알림 원본 개체를 제거합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT UnregisterNotifySource  
(  
    [in]  INotifySource2*  in_pNotifySource  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `in_pNotifySource`  
 [in] 등록을 취소할 알림 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 메서드가 성공 하면 S_OK입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** ProtocolNotify2.idl  
  
## <a name="see-also"></a>참고 항목  
 [INotifyConnection2 인터페이스](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)  
 [INotifySource2 인터페이스](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)  
 [INotifySink2 인터페이스](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)  
 [RegisterNotifySource 메서드](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-registernotifysource-method.md)
