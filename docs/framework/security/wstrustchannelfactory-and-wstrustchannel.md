---
title: "WSTrustChannelFactory 및 WSTrustChannel | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 96cec467-e963-4132-b18b-7d0b3a2e979f
caps.latest.revision: 9
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 9
---
# WSTrustChannelFactory 및 WSTrustChannel
당신은 친숙 한 Windows 통신 Foundation \(WCF\)를 사용 하 여 이미 WCF 클라이언트는 페더레이션을 인식 이미 알 수 있습니다.  사용 하 여 WCF 클라이언트를 구성 하 여 한 <xref:System.ServiceModel.WSFederationHttpBinding> 또는 유사한 사용자 지정 바인딩, 페더레이션된 인증 서비스를 사용할 수 있습니다.  
  
 WCF는 내부적 보안 토큰 서비스 \(STS\)를 생성 하 고이 토큰을 사용 하 여 서비스를 인증 하는 토큰을 가져옵니다.  이 방법의 주요 제한은 서버와 클라이언트의 통신을 볼 수 없으므로입니다.  WCF는 바인딩의 발급 된 토큰 매개 변수를 기반으로 STS로 요청 보안 토큰을 \(RST\) 자동으로 만듭니다.  즉 클라이언트 없습니다 요청 별로 RST 매개 변수를 변경, 요청 보안 토큰 응답 \(RSTR\) 디스플레이 클레임 정보를 검사 또는 나중에 사용에 대 한 토큰을 캐시 합니다.  
  
 현재 WCF 클라이언트는 기본 페더레이션 시나리오에 적합 합니다.  그러나 Windows Identity 기초 \(WIF\)를 지 원하는 주요 시나리오 중 하나는 RST WCF 쉽게 허용 되지 않는 수준에서 제어할이 필요 합니다.  따라서 WIF에는 STS와의 통신을 통해 더 많은 제어를 제공 하는 기능이 추가 되었습니다.  
  
 WIF에서는 다음과 같은 페더레이션 시나리오를 지원합니다.  
  
-   WCF 클라이언트를 WIF 종속성 없이 사용 하 여 페더레이션된 서비스에 인증  
  
-   STS로의 RST ActAs 또는 OnBehalfOf 요소를 삽입 하는 WCF 클라이언트를 WIF를 사용 하면  
  
-   WIF를 사용 하 여 단독으로 STS에서 토큰을 가져올 및 다음이 토큰으로 인증할 수 있는 WCF 클라이언트를 사용 합니다.  자세한 내용은 [ClaimsAwareWebService](http://go.microsoft.com/fwlink/?LinkID=248406) 샘플입니다.  
  
 첫 번째 시나리오는 쉽게 이해할 수 있습니다: 기존 WCF 클라이언트를 WIF 신뢰 당사자 및 Sts 계속 됩니다.  이 항목에서는 나머지 두 시나리오 설명 합니다.  
  
## ActAs 사용 하 여 기존 WCF 클라이언트를 개선 \/ OnBehalfOf  
 일반적인 identity 위임 시나리오에서 클라이언트가 백엔드 서비스를 호출 하는 중간 계층 서비스를 호출 합니다.  중간 계층 서비스 역할을, 또는 클라이언트 대신 작동 합니다.  
  
> [!TIP]
>  ActAs 및 OnBehalfOf 사이의 차이점은 무엇입니까?  
>   
>  Ws\-trust 프로토콜 관점:  
>   
>  1.  ActAs RST 요소는 요청 자가 토큰을 포함 하는 주장 두 가지 엔터티를 원한다는 것을 나타냅니다: 해당 요청자와 ActAs 요소의 토큰에 의해 표시 되는 외부 엔터티.  
> 2.  OnBehalfOf RST 요소 요청자 클레임에 대 한 하나의 엔터티가 포함 된 토큰을 원한다는 것을 나타냅니다: OnBehalfOf 요소에 토큰이 나타내는 외부 엔터티.  
>   
>  ActAs 기능은 주로 발급된 된 토큰의 마지막 수신자 수 전체 위임 체인을 검사 하 고 클라이언트 뿐만 아니라이 있지만 모든 중간 거점 복합 위임이 필요한 시나리오에서 사용 됩니다.  액세스 제어를 수행할 수 있습니다, 그리고 감사 및 기타 관련 전체 id 위임 체인을 기준으로 작업 합니다.  ActAs 기능은 인증 하 고 응용 프로그램\/비즈니스 논리 계층에서이 정보를 전달할 필요 없이 계층 간에 id에 대 한 정보를 전달 하려면 다중 계층 시스템에서 주로 사용 됩니다.  
>   
>  OnBehalfOf 기능 원래 클라이언트의 id만 중요 하 고는 사실상 Windows에서 사용할 identity 가장 기능 같은 있는 경우에 사용 됩니다.  OnBehalfOf를 사용할 경우 발급된 된 토큰의 마지막 수신자는 원래 클라이언트의 클레임만 볼 수 있습니다 및 중개자에 대 한 정보는 유지 되지 않습니다.  OnBehalfOf 기능을 사용 하는 일반적인 패턴은 하나 클라이언트 않고 직접 STS를 액세스할 수 없습니다 프록시 패턴 통신 프록시 게이트웨이 통해 합니다.  프록시 게이트웨이 호출자를 인증 하 고 호출자에 대 한 내용은 다음에 보내는 실제 STS 처리용 RST 메시지의 OnBehalfOf 요소에 저장 합니다.  결과 토큰 발급된 된 토큰의 수신자에 게 완전히 투명 하 게 프록시를 만들어 프록시 클라이언트와 관련 된 클레임만 들어 있습니다.WIF에서 지원 하지 않는 참고 \<wsse:SecurityTokenReference\> 또는 \<wsa:EndpointReferences\> 의 자식으로 \<wst:OnBehalfOf\>.  Ws\-trust 사양은 \(누구를 대신 하 여 프록시 역할\) 원래 요청자를 식별 하는 세 가지가 있습니다.  나타낼 수 있습니다.  
>   
>  -   보안 토큰 참조입니다.  참조 토큰을 메시지 또는 부재 중 검색된 가능한 밴드\)입니다.  
> -   끝점 참조입니다.  다시 대역외 데이터를 찾는 키로 사용 합니다.  
> -   보안 토큰입니다.  원래 요청자를 직접 식별합니다.  
>   
>  WIF는의 직접적인 자식 요소로 암호화 또는 암호화 된 보안 토큰을 지원 \<wst:OnBehalfOf\>.  
  
 이 정보는 RST ActAs 및 OnBehalfOf 토큰 요소를 사용 하 여 Ws\-trust 발급자에 전달 됩니다.  
  
 WCF는 바인딩에서 임의의 XML 요소는 시작에 추가할 수 있는 확장성 지점을 제공 합니다.  그러나 확장성 지점을 바인딩과 연결 때문에 RST 내용을 호출 별로 다양 하 게 요구 하는 경우 다시 만들어야 성능이 저하 되는 모든 호출에 대해 클라이언트.  WIF에서 확장 메서드를 사용 하는 `ChannelFactory` 클래스를 통해 개발자는 RST 대역에 가져온 모든 토큰을 연결할.  다음 코드 예제에서는 클라이언트 \(예: X.509, 사용자 이름 또는 보안 어설션 마크업 언어 \(SAML\) 토큰\)를 나타내는 토큰 발급자에 게 보낸 RST에 연결 하는 방법을 보여 줍니다.  
  
```  
IHelloService serviceChannel = channelFactory.CreateChannelActingAs<IHelloService>( clientSamlToken );  
serviceChannel.Hello(“Hi!”);  
```  
  
 WIF는 다음과 같은 이점을 제공합니다.  
  
-   채널 별로 RST는 수정할 수 있습니다. 따라서 중간 계층 서비스 다시 성능이 향상 되는 각 클라이언트에 대 한 채널 팩터리를 만들 필요가 없습니다.  
  
-   이것은 기존 WCF 클라이언트를 사용 하 여 쉬운 업그레이드 identity 위임 의미 체계를 사용 하려는 기존 WCF 중간 계층 서비스에 대 한 수 있습니다.  
  
 그러나 STS와 클라이언트의 통신을 볼 수 없으므로 계속 됩니다.  세 번째 시나리오에서 살펴보겠습니다.  
  
## 발급자와 직접 통신 및 발급된 된 토큰을 사용 하 여 인증  
 일부 고급 시나리오의 경우 WCF 클라이언트 향상 만으로는 부족 합니다.  일반적으로 WCF를 사용 하는 개발자를 사용 하 여 메시지에 메시지를 계약 하 고 클라이언트 쪽 처리 \/ 발급자 응답을 수동으로 구문 분석 합니다.  
  
 WIF 소개의 <xref:System.ServiceModel.Security.WSTrustChannelFactory> 및 <xref:System.ServiceModel.Security.WSTrustChannel> Ws\-trust 발급자와 직접 통신 하는 클라이언트를 사용 하는 클래스입니다.  <xref:System.ServiceModel.Security.WSTrustChannelFactory> 및 <xref:System.ServiceModel.Security.WSTrustChannel> 다음 코드 예제와 같이 클래스 발급자와 클라이언트 사이의 흐름 RST 및 RSTR 강력한 형식의 개체를 사용 합니다.  
  
```  
WSTrustChannelFactory trustChannelFactory = new WSTrustChannelFactory( stsBinding, stsAddress );  
WSTrustChannel channel = (WSTrustChannel) trustChannelFactory.CreateChannel();  
RequestSecurityToken rst = new RequestSecurityToken(RequestTypes.Issue);  
rst.AppliesTo = new EndpointAddress(serviceAddress);  
RequestSecurityTokenResponse rstr = null;  
SecurityToken token = channel.Issue(rst, out rstr);  
```  
  
 `out` 매개 변수는 <xref:System.ServiceModel.Security.WSTrustChannel.Issue%2A> 메서드를 사용 하면 클라이언트 쪽 검사 RSTR에 액세스할 수 있습니다.  
  
 지금까지 우리만 봤는 토큰을 얻는 방법.  반환 되는 토큰은 <xref:System.ServiceModel.Security.WSTrustChannel> 개체는 `GenericXmlSecurityToken` 는 당사자에 게 인증에 필요한 정보를 모두 포함 하.  다음 코드 예제에서는이 토큰을 사용 하는 방법을 보여 줍니다.  
  
```  
IHelloService serviceChannel = channelFactory.CreateChannelWithIssuedToken<IHelloService>( token ); serviceChannel.Hello(“Hi!”);  
```  
  
 <xref:System.ServiceModel.ChannelFactory%601.CreateChannelWithIssuedToken%2A> 에서 확장 메서드는 `ChannelFactory` 개체에 게 알립니다 WIF 토큰 대역을 갖고 해야 발급자 일반 WCF 호출을 중지 하는 당사자에 게 인증을 획득 하는 토큰을 사용 하는 대신.  이 이점이 있습니다.  
  
-   토큰 발급 프로세스를 통해 완벽 한 제어를 하면 됩니다.  
  
-   ActAs 지원 \/ OnBehalfOf 시나리오 직접 보내는 시작에서 이러한 속성을 설정 합니다.  
  
-   동적 클라이언트 신뢰를 RSTR의 콘텐츠를 기반으로 결정할 수 있습니다.  
  
-   수 있습니다 캐시에서 반환 되는 토큰을 다시 사용 하는 <xref:System.ServiceModel.Security.WSTrustChannel.Issue%2A> 메서드.  
  
-   <xref:System.ServiceModel.Security.WSTrustChannelFactory>및 <xref:System.ServiceModel.Security.WSTrustChannel> WCF 모범 사례에 따라 채널 캐싱, 오류 및 복구 기능에 대 한 제어를 허용 합니다.  
  
## 참고 항목  
 [WIF 기능](../../../docs/framework/security/wif-features.md)