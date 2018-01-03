---
title: "WIF API 참조"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a027d902-9314-4bfd-b172-4e81847b1d68
caps.latest.revision: "4"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: e3209ac32314e2ac3f4e3e1920991ed29f956832
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="wif-api-reference"></a>WIF API 참조
WIF(Windows Identity Foundation) 클래스는 `mscorlib`(mscorlib.dll), `System.IdentityModel`(System.IdentityModel.dll), `System.IdentityModel.Services`(System.IdentityModel.Services.dll) 및 `System.ServiceModel`(System.ServiceModel.dll) 어셈블리에 분할됩니다. 이 항목에서는 WIF 네임스페이스에 대한 링크 및 각 네임스페이스에 포함된 클래스에 대한 간략한 설명을 제공합니다.  
  
> [!IMPORTANT]
>  다음 `System.IdentityModel` 네임스페이스에는 WCF 클레임 기반 ID 모델을 구현하는 클래스가 포함됩니다. <xref:System.IdentityModel.Claims?displayProperty=nameWithType>, <xref:System.IdentityModel.Policy?displayProperty=nameWithType> 및 <xref:System.IdentityModel.Selectors?displayProperty=nameWithType>. .NET Framework 4.5부터 WCF 클레임 기반 ID 모델은 WIF로 대체됩니다. WIF를 기반으로 솔루션을 빌드할 때 이러한 세 개의 네임스페이스에서 클래스를 사용하면 안 됩니다.  
  
 <xref:System.IdentityModel?displayProperty=nameWithType>  
 쿠키 변환, 보안 토큰 서비스 및 특수 XML 사전 판독기를 나타내는 클래스를 포함합니다.  
  
 <xref:System.IdentityModel.Configuration?displayProperty=nameWithType>  
 WIF(Windows Identity Foundation)를 사용하여 빌드된 응용 프로그램 및 서비스에 대한 구성을 제공하는 클래스를 포함합니다. 이 네임 스페이스의 클래스는 [\<identityConfiguration>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) 요소 아래에 있는 설정을 나타냅니다.  
  
 <xref:System.IdentityModel.Metadata?displayProperty=nameWithType>  
 페더레이션 메타데이터 문서에 있는 요소를 나타내는 클래스를 포함합니다.  
  
 <xref:System.IdentityModel.Protocols.WSTrust?displayProperty=nameWithType>  
 WS-Trust 아티팩트를 나타내는 클래스를 포함합니다.  
  
 <xref:System.IdentityModel.Services?displayProperty=nameWithType>  
 수동(WS-Federation) 시나리오에서 사용되는 클래스를 포함합니다. 또한 [\<system.identityModel.services>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md) 요소 아래에 있는 설정을 나타내는 일부 클래스도 포함합니다. 이 요소 아래에 있는 설정은 응용 프로그램에 대해 WS-Federation을 구성합니다. `System.IdentityModel.Services.Configuration` 네임스페이스에는 WS-Federation 구성에 사용되는 클래스가 대부분 포함됩니다.  
  
 <xref:System.IdentityModel.Services.Configuration?displayProperty=nameWithType>  
 WS-Federation 프로토콜을 사용하는 WIF 응용 프로그램에 대한 구성을 제공하는 클래스를 포함합니다. 이 네임스페이스의 클래스는 [\<system.identityModel.services>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md) 요소 아래에 있는 설정을 나타내는 일부 클래스를 포함합니다. `System.IdentityModel.Services` 네임스페이스에는 WS-Federation 구성에 사용되는 일부 클래스도 포함됩니다.  
  
 <xref:System.IdentityModel.Services.Tokens?displayProperty=nameWithType>  
 웹 팜 시나리오에 대한 특수 보안 토큰 처리기를 포함합니다.  
  
 <xref:System.IdentityModel.Tokens?displayProperty=nameWithType>  
 보안 토큰, 보안 토큰 처리기 및 기타 보안 토큰 아티팩트를 나타내는 클래스를 포함합니다.  
  
 <xref:System.Security.Claims?displayProperty=nameWithType>  
 클레임, 클레임 기반 ID, 클레임 기반 주체 및 기타 클레임 기반 ID 모델 아티팩트를 나타내는 클래스를 포함합니다.  
  
 <xref:System.ServiceModel.Security?displayProperty=nameWithType>  
 활성(WS-Trust) 시나리오에서 사용되는 WCF 계약, 채널, 서비스 호스트 및 기타 아티팩트를 나타내는 클래스를 포함합니다. 이 네임스페이스에는 WCF(Windows Communication Foundation)에 관련이 있고 WIF에서 사용되지 않는 클래스도 포함됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [WIF 구성 참조](../../../docs/framework/security/wif-configuration-reference.md)  
 [WIF 3.5와 WIF 4.5 간의 네임스페이스 매핑](../../../docs/framework/security/namespace-mapping-between-wif-3-5-and-wif-4-5.md)
