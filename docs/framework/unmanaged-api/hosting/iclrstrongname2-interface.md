---
title: "ICLRStrongName2 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRStrongName2
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRStrongName2
helpviewer_keywords: ICLRStrongName2 interface [.NET Framework hosting]
ms.assetid: 9f098a74-201e-4628-a468-8dee9ab99b4a
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d4e1274f675ae9289faa6c530d34cd61d033aa07
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="iclrstrongname2-interface"></a>ICLRStrongName2 인터페이스
(Sha-256, sha-384 및 s h A-512) 보안 해시 알고리즘의 sha-2 그룹을 사용 하 여 강력한 이름을 만들 수가 있습니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[StrongNameGetPublicKeyEx 메서드](../../../../docs/framework/unmanaged-api/hosting/strongnamegetpublickeyex-method.md)|공개/개인 키 쌍에서 공개 키를 가져옵니다 하 고는 해시 알고리즘 및 서명 알고리즘을 지정 합니다.|  
|[StrongNameSignatureVerificationEx2 메서드](../../../../docs/framework/unmanaged-api/hosting/strongnamesignatureverificationex2-method.md)|강력한 이름의 어셈블리의 서명을 확인 하 고 실제 키를 ECMA 키로의 매핑을 제공 합니다.|  
  
## <a name="remarks"></a>설명  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** MetaHost.h  
  
 **라이브러리:** MSCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]
