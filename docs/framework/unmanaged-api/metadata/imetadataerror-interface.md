---
title: "IMetaDataError 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataError
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataError
helpviewer_keywords: IMetaDataError interface [.NET Framework metadata]
ms.assetid: 0020b62c-ea88-40c7-a9ee-16b064f81624
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4df7aa7400a180151de5420effc8738955d51c26
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataerror-interface"></a>IMetaDataError 인터페이스
메타 데이터를 병합 하는 동안 오류를 보고 하는 콜백 메커니즘을 제공 합니다.  
  
> [!NOTE]
>  `IMetaDataError` 클라이언트에서 인터페이스를 구현 해야 합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[OnError 메서드](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-onerror-method.md)|메타 데이터를 병합 하는 동안 발생 하는 오류에 대 한 알림을 제공 합니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** Cor.h  
  
 **라이브러리:** MsCorEE.dll에서 리소스로 사용  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [메타데이터 인터페이스](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
