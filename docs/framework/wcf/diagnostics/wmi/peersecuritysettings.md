---
title: PeerSecuritySettings
ms.date: 03/30/2017
ms.assetid: 24ae0d35-f3a3-419b-afd6-686e22aae27b
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 58b372f26fee7dc180d75731fd4855db569c87c7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="peersecuritysettings"></a>PeerSecuritySettings
PeerSecuritySettings  
  
## <a name="syntax"></a>구문  
  
```  
class PeerSecuritySettings  
{  
  string Mode;  
  PeerTransportSecuritySettings Transport;  
};  
```  
  
## <a name="methods"></a>메서드  
 PeerSecuritySettings 클래스는 메서드를 정의하지 않습니다.  
  
## <a name="properties"></a>속성  
 PeerSecuritySettings 클래스에는 다음과 같은 속성이 있습니다.  
  
### <a name="mode"></a>모드  
 데이터 형식: string  
  
 액세스 형식: 읽기 전용  
  
 바인딩으로 구성된 끝점이 메시지 수준 보안을 사용하는지 또는 전송 수준 보안을 사용하는지 여부입니다.  
  
### <a name="transport"></a>전송  
 데이터 형식: PeerTransportSecuritySettings  
  
 액세스 형식: 읽기 전용  
  
 전송 보안 설정입니다.  
  
## <a name="requirements"></a>요구 사항  
  
|MOF|Servicemodel.mof에 선언되어 있습니다.|  
|---------|-----------------------------------|  
|네임스페이스|root\ServiceModel에 정의되어 있습니다.|  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ServiceModel.PeerSecuritySettings>
