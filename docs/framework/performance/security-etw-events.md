---
title: "보안 ETW 이벤트"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- security events [.NET Framework]
- ETW, security events (CLR)
ms.assetid: 0ed69f73-5c01-4514-bd63-979c6e38d41d
caps.latest.revision: 8
author: mairaw
ms.author: mairaw
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: a7e28eeabecfe0f1043328618f6e1be143f198a6
ms.contentlocale: ko-kr
ms.lasthandoff: 08/21/2017

---
# <a name="security-etw-events"></a>보안 ETW 이벤트
<a name="top"></a> 보안 이벤트는 강력한 이름 확인 및 Authenticode 확인 중에 발생합니다.  
  
 이 범주는 다음 이벤트로 구성됩니다.  
  
-   [StrongNameVerificationStart_V1 및 StrongNameVerificationStop_V1 이벤트](#strongnameverificationstart_v1_and_strongnameverificationstop_v1_events)  
  
-   [AuthenticodeVerificationStart_V1 및 AuthenticodeVerificationStop_V1 이벤트](#authenticodeverificationstart_v1_and_authenticodeverificationstop_v1_events)  
  
<a name="strongnameverificationstart_v1_and_strongnameverificationstop_v1_events"></a>   
## <a name="strongnameverificationstartv1-and-strongnameverificationstopv1-events"></a>StrongNameVerificationStart_V1 및 StrongNameVerificationStop_V1 이벤트  
 다음 표에서는 키워드와 수준을 보여 줍니다. 자세한 내용은 [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)을 참조하세요.  
  
|이벤트를 발생시키기 위한 키워드|수준|  
|-----------------------------------|-----------|  
|`SecurityKeyword` (0x400)|정보 제공(4)|  
  
 다음 표에서는 이벤트 정보를 보여 줍니다.  
  
|이벤트|이벤트 ID|발생 시기|  
|-----------|--------------|-----------------|  
|`StrongNameVerificationStart_V1`|181|강력한 이름 확인의 시작입니다.|  
|`StrongNameVerificationStop_V1`|182|강력한 이름 확인의 끝입니다.|  
  
 다음 표에서는 이벤트 데이터를 보여 줍니다.  
  
|필드 이름|데이터 형식|설명|  
|----------------|---------------|-----------------|  
|VerificationFlags|win:UInt32|확인 플래그입니다.|  
|ErrorCode|win:UInt32|HResult 오류 코드입니다.|  
|FullyQualifiedAssemblyName|win:UnicodeString|정규화된 어셈블리 이름입니다.|  
|ClrInstanceID|win:UInt16|CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.|  
  
 [맨 위로 이동](#top)  
  
<a name="authenticodeverificationstart_v1_and_authenticodeverificationstop_v1_events"></a>   
## <a name="authenticodeverificationstartv1-and-authenticodeverificationstopv1-events"></a>AuthenticodeVerificationStart_V1 및 AuthenticodeVerificationStop_V1 이벤트  
 다음 표에서는 키워드와 수준을 보여 줍니다.  
  
|이벤트를 발생시키기 위한 키워드|수준|  
|-----------------------------------|-----------|  
|`SecurityKeyword` (0x400)|정보 제공(4)|  
  
 다음 표에서는 이벤트 정보를 보여 줍니다.  
  
|이벤트|이벤트 ID|발생 시기|  
|-----------|--------------|-----------------|  
|`AuthenticodeVerificationStart_V1`|183|Authenticode 확인의 시작입니다.|  
|`AuthenticodeVerificationStop_V1`|184|Authenticode 확인의 끝입니다.|  
  
 다음 표에서는 이벤트 데이터를 보여 줍니다.  
  
|필드 이름|데이터 형식|설명|  
|----------------|---------------|-----------------|  
|VerificationFlags|win:UInt32|확인 플래그입니다.|  
|ErrorCode|win:UInt32|HResult 오류 코드입니다.|  
|ModulePath|win:UnicodeString|모듈 경로입니다.|  
|ClrInstanceID|win:UInt16|CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.|  
  
## <a name="see-also"></a>참고 항목  
 [CLR ETW 이벤트](../../../docs/framework/performance/clr-etw-events.md)

