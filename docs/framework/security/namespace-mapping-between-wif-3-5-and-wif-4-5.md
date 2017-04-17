---
title: "WIF 3.5와 WIF 4.5 간의 네임스페이스 매핑 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a092d98c-444d-4336-a644-63c2e11e96c8
caps.latest.revision: 4
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 4
---
# WIF 3.5와 WIF 4.5 간의 네임스페이스 매핑
.NET 4.5로 부터는 소리치 \(Windows Identity Foundation 더\) 완벽 하 게는.NET Framework 통합 되었습니다.  이 통합 이름 변경과 일부 통합 API 서피스 및 소리치 더 네임 스페이스의 현실성.  이 항목에서는 몇 가지 지침 및 일반 3.5 소리치 더 네임 스페이스와 소리치 더 4.5 네임 스페이스 간의 매핑을 제공합니다.  이것을 철저 하 게 했지만 오히려 소리치 더 4.5에 익숙한 소리치 더 3.5 클래스를 찾을 수 있는 위치에 대 한 일반 정보를 제공 것입니다.  3.5 소리치 더 소리치 더 4.5 사이의 차이점에 대 한 자세한 내용은 [Windows Identity Foundation 4.5의 새로운 기능](../../../docs/framework/security/whats-new-in-wif.md).  4.5 소리치 더 소리치 더 3.5를 사용 하 여 작성 된 응용 프로그램을 마이그레이션하는 방법에 대 한 설명서를 참조 하십시오. [WIF 3.5를 사용하여 빌드된 응용 프로그램을 WIF 4.5로 마이그레이션하는 지침](../../../docs/framework/security/guidelines-for-migrating-an-application-built-using-wif-3-5-to-wif-4-5.md).  
  
## 3.5 소리치 더 소리치 더 4.5에 네임 스페이스 매핑  
 수집 된 소리치 더 클래스는 `Microsoft.IdentityModel` 소리치 더 3.5에서 네임 스페이스는 이제 다음과 같은 네임 스페이스 간에 분포: `System.Security.Claims`, `System.ServiceModel.Security`, 및 `System.IdentityModel` 네임 스페이스에 소리치 더 4.5.  또한 일부 소리치 더 3.5 네임 스페이스 통합 또는 소리치 더 4.5에서 완전히 삭제 되었습니다.  
  
> [!IMPORTANT]
>  다음 `System.IdentityModel` 네임 스페이스는 WCF 클레임 기반 id 모델을 구현 하는 클래스를 포함: <xref:System.IdentityModel.Claims?displayProperty=fullName>, <xref:System.IdentityModel.Policy?displayProperty=fullName>, 및 <xref:System.IdentityModel.Selectors?displayProperty=fullName>.  클레임 기반 id 모델 WCF가 소리치 더로 대체 되었습니다.  소리치 더를 기반으로 솔루션을 빌드할 때에 이러한 세 가지 네임 스페이스에 클래스를 사용할 수 없습니다.  
  
 다음 테이블에 소리치 더 4.5 3.5 소리치 더 클래스 위치에 대 한 정보를 제공 합니다.  
  
||||  
|-|-|-|  
|**3.5 소리치 더 네임 스페이스**|**4.5 소리치 더 네임 스페이스**|**설명**|  
|`Microsoft.IdentityModel`|<xref:System.IdentityModel?displayProperty=fullName>|-   대부분의 상수를 나타내는 클래스가 구현 되지 않습니다.<br />-   보안 토큰 서비스를 구축 하는 데 사용 되는 클래스에서 옮겨진 `Microsoft.IdentityModel.SecurityTokenService` 에 <xref:System.IdentityModel?displayProperty=fullName>.<br />-   클래스에서 `Microsoft.IdentityModel.Threading` 이동한 <xref:System.IdentityModel?displayProperty=fullName>.<br />-   `ExceptionMapper` 및 `MruSecurityTokenCache` 클래스를 구현 하지 않았습니다.|  
|`Microsoft.IdentityModel.Claims`|<xref:System.Security.Claims?displayProperty=fullName>|-   `IClaimsPrincipal` 및 `IClaimsIdentity` 소리치 더 4.5에서 인터페이스를 구현 하지 않았습니다.  대신 <xref:System.Security.Claims.ClaimsPrincipal?displayProperty=fullName> 및 <xref:System.Security.Claims.ClaimsIdentity?displayProperty=fullName> 이제 기본 클래스는 대부분의.net에서 주 이며 identity 클래스를 파생 합니다.  따라서 필요 하지 않습니다 전문적인된 클레임에 대 한 사용자 및 id 클래스와 마찬가지로 `Microsoft.IdentityModel.Claims.WindowsClaimsPrincipal` 및 `Microsoft.IdentityModel.Claims.WindowsClaimsIdentity` 소리치 더 4.5를 사용 하 여 <xref:System.Security.Principal.WindowsPrincipal?displayProperty=fullName> 및 <xref:System.Security.Principal.WindowsIdentity?displayProperty=fullName> 대신.  다른 마찬가지 소리치 더 3.5에 있던 다른 특별 한 클레임 사용자 및 id 클래스입니다.<br />-   `Microsoft.IdentityModel.Claims.ClaimsCollection` 클래스에 소리치 더 4.5 구현 되지 않았습니다.  컬렉션의 클레임 형식 열거 가능한 컬렉션으로 노출 되는 대신 <xref:System.Security.Claims.Claim?displayProperty=fullName>.<br />-   <xref:System.Security.Claims.ClaimsPrincipal?displayProperty=fullName>및 <xref:System.Security.Claims.ClaimsIdentity?displayProperty=fullName> 이제 LINQ 완벽 하 게 지원 되는 메서드를 제공 합니다.|  
|`Microsoft.IdentityModel.Configuration`|<xref:System.IdentityModel.Configuration?displayProperty=fullName>|일부 요소 및 클래스 이름이 변경 되었으며 일부 소리치 더 4.5에서 삭제 되었습니다. for example `Microsoft.IdentityModel.Configuraiton.ServiceConfiguration` is now <xref:System.IdentityModel.Configuration.IdentityConfiguration?displayProperty=fullName>.|  
|`Microsoft.IdentityModel.Protocols`|<xref:System.IdentityModel.Services?displayProperty=fullName>|\-|  
|`Microsoft.IdentityModel.Protocols.WSFederation`|<xref:System.IdentityModel.Services?displayProperty=fullName>|\-|  
|`Microsoft.IdentityModel.Protocols.WSFederation.Metadata`|<xref:System.IdentityModel.Metadata?displayProperty=fullName>|\-|  
|`Microsoft.IdentityModel.Protocols.WSIdentity`|소리치 더 4.5에서 구현 되지 않았습니다.|소리치 더 3.5 인치 소리치 더 4.5에서 구현 되지 않았습니다 Cardspace를 지 원하는 클래스를 포함 합니다.|  
|`Microsoft.IdentityModel.Protocols.WSTrust`|분할 사이 <xref:System.IdentityModel.Protocols.WSTrust?displayProperty=fullName> 및 <xref:System.ServiceModel.Security?displayProperty=fullName> 네임 스페이스.|Ws\-trust 아티팩트를 나타내는 클래스 들의 <xref:System.IdentityModel.Protocols.WSTrust?displayProperty=fullName> 네임 스페이스입니다. 예를 들어 있는 <xref:System.IdentityModel.Protocols.WSTrust.RequestSecurityToken> 클래스입니다.  WCF 서비스 계약, 서비스 호스트에 대 한 Ws\-trust 프로토콜을 사용 하 여 통신 하는 WCF 서비스를 사용 하는 채널을 나타내는 클래스 들의 <xref:System.ServiceModel.Security?displayProperty=fullName> 네임 스페이스입니다. 예를 들어 있는 <xref:System.ServiceModel.Security.WSTrustServiceHost> 클래스입니다.|  
|`Microsoft.IdentityModel.Protocols.WSTrust.Bindings`|소리치 더 4.5에서 구현 되지 않았습니다.|\-|  
|`Microsoft.IdentityModel.Protocols.XmlEncryption`|소리치 더 4.5에서 구현 되지 않았습니다.|소리치 더 3.5에서 XML 암호화 상수를 나타내는 클래스를 포함 합니다.  이러한 상수는 소리치 더 4.5에서 구현 되지 않습니다.|  
|`Microsoft.IdentityModel.Protocols.XmlSignature`|<xref:System.IdentityModel?displayProperty=fullName>|`EnvelopingSignature` 상수를 나타내는 클래스 및 구현 되어 있지 않습니다.|  
|`Microsoft.IdentityModel.SecurityTokenService`|분할 사이 <xref:System.IdentityModel?displayProperty=fullName>, <xref:System.IdentityModel.Protocols.WSTrust?displayProperty=fullName>, 및 <xref:System.IdentityModel.Tokens?displayProperty=fullName> 네임 스페이스.|\-|  
|`Microsoft.IdentityModel.Threading`|<xref:System.IdentityModel?displayProperty=fullName>|\-|  
|`Microsoft.IdentityModel.Tokens`|<xref:System.IdentityModel.Tokens?displayProperty=fullName>|\-|  
|`Microsoft.IdentityModel.Tokens.Saml11`|<xref:System.IdentityModel.Tokens?displayProperty=fullName>|\-|  
|`Microsoft.IdentityModel.Tokens.Saml2`|<xref:System.IdentityModel.Tokens?displayProperty=fullName>|\-|  
|`Microsoft.IdentityModel.Web`|<xref:System.IdentityModel.Services?displayProperty=fullName>|\-|  
|`Microsoft.IdentityModel.Web.Configuration`|<xref:System.IdentityModel.Services.Configuration?displayProperty=fullName>|수동 \(WS\-페더레이션\) 시나리오 대부분에 옮겨진 것에 대 한 구성을 제공 하는 클래스 <xref:System.IdentityModel.Services.Configuration?displayProperty=fullName>. 그러나 일부 이러한 클래스에는 <xref:System.IdentityModel.Services?displayProperty=fullName>.|  
|`Microsoft.IdentityModel.Web.Controls`|소리치 더 4.5에서 구현 되지 않았습니다.|클래스에서 `Microsoft.IdentityModel.Web.Controls` 페더레이션 수동 로그인 소리치 더 4.5에서 존재 하지 않는 컨트롤을 구현 합니다.|  
|`Microsoft.IdentityModel.WindowsTokenService`|소리치 더 4.5에서 구현 되지 않았습니다.|\-|  
  
## 참고 항목  
 [Windows Identity Foundation 4.5의 새로운 기능](../../../docs/framework/security/whats-new-in-wif.md)   
 [WIF 3.5를 사용하여 빌드된 응용 프로그램을 WIF 4.5로 마이그레이션하는 지침](../../../docs/framework/security/guidelines-for-migrating-an-application-built-using-wif-3-5-to-wif-4-5.md)