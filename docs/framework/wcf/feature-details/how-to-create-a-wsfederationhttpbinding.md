---
title: "방법: WSFederationHttpBinding 만들기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, federation
- federation
ms.assetid: e54897d7-aa6c-46ec-a278-b2430c8c2e10
caps.latest.revision: "16"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 3314519e89a78f188d78a5e5af641d7c87ee1c46
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-wsfederationhttpbinding"></a>방법: WSFederationHttpBinding 만들기
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], <xref:System.ServiceModel.WSFederationHttpBinding> 클래스 ([\<wsFederationHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) 구성에서) 페더레이션된 서비스를 노출 하기 위한 메커니즘을 제공 합니다. 즉, 보안 토큰 서비스에서 발급된 보안 토큰을 사용하여 클라이언트가 인증해야 하는 서비스입니다. 이 항목에서는 코드와 구성 둘 다에서 <xref:System.ServiceModel.WSFederationHttpBinding>을 설정하는 방법을 보여 줍니다. 바인딩을 만들고 나면 해당 바인딩을 사용하도록 끝점을 설정할 수 있습니다.  
  
 기본 단계는 다음과 같이 간략하게 설명됩니다.  
  
1.  보안 모드를 선택합니다. <xref:System.ServiceModel.WSFederationHttpBinding>은 여러 홉을 통과하는 경우에도 메시지 수준에서 종단 간 보안을 제공하는 `Message`와 클라이언트 및 서비스가 HTTPS를 통해 직접 연결할 수 있는 경우 성능을 향상시키는 `TransportWithMessageCredential`을 지원합니다.  
  
    > [!NOTE]
    >  <xref:System.ServiceModel.WSFederationHttpBinding>은 보안 모드로 `None`도 지원합니다. 이 모드는 보안되지 않으며 디버깅 목적을 위해서만 제공됩니다. 서비스 끝점으로 배포 하는 경우는 <xref:System.ServiceModel.WSFederationHttpBinding> 로 설정 하는 보안 모드와 함께 `None`, 결과 클라이언트 바인딩에 (에 의해 생성 된는 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)) 되는 <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`>의 보안 모드와 함께 `None`합니다.  
  
     다른 시스템 제공 바인딩과 달리 `WSFederationHttpBinding`을 사용할 때는 클라이언트 자격 증명 형식을 선택할 필요가 없습니다. 이는 클라이언트 자격 증명 형식이 항상 발급된 토큰이기 때문입니다. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 지정된 발급자로부터 토큰을 받아서 서비스에 제공하여 클라이언트를 인증합니다.  
  
2.  페더레이션 클라이언트에서는 <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.IssuerAddress%2A> 속성을 보안 토큰 서비스의 URL로 설정합니다. <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.IssuerBinding%2A>을 보안 토큰 서비스와 통신하는 데 사용할 바인딩으로 설정합니다.  
  
3.  선택 사항입니다. <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.IssuedTokenType%2A> 속성을 토큰 형식의 URI(Uniform Resource Identifier)로 설정합니다. 연합 서비스에서는 서비스에 필요한 토큰 형식을 지정합니다. 페더레이션 클라이언트에서는 클라이언트가 보안 토큰 서비스에서 요청하는 토큰 형식을 지정합니다.  
  
     토큰 형식을 지정하지 않으면 클라이언트는 토큰 URI 없이 WS-Trust RST(요청 보안 토큰)를 생성하며 기본적으로 SAML(Security Assertions Markup Language) 1.1 토큰을 사용한 클라이언트 인증이 서비스에 필요합니다.  
  
     SAML 1.1 토큰에 대한 URI는 "http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAMLV1.1"입니다.  
  
4.  선택 사항입니다. 연합 서비스에서는 <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.IssuerMetadataAddress%2A> 속성을 보안 토큰 서비스의 메타데이터 URL로 설정합니다. 서비스의 클라이언트는 서비스가 메타데이터를 게시하도록 구성된 경우 메타데이터 끝점을 사용하여 적절한 바인딩/끝점 쌍을 선택할 수 있습니다. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]참조 메타 데이터를 게시 [메타 데이터 게시](../../../../docs/framework/wcf/feature-details/publishing-metadata.md)합니다.  
  
 발급된 토큰에서 증명 키로 사용되는 키의 형식, 클라이언트와 서비스 간에 사용할 알고리즘 모음, 서비스 자격 증명을 협상할지 또는 명시적으로 지정할지 여부, 서비스에서 발급된 토큰에 포함되어 있다고 예상하는 특정 클레임, 클라이언트가 보안 토큰 서비스에 보내는 요청에 추가해야 하는 추가 XML 요소 등의 다른 속성을 설정할 수도 있습니다.  
  
> [!NOTE]
>  `NegotiateServiceCredential` 속성은 `SecurityMode`가 `Message`로 설정된 경우에만 관련이 있습니다. `SecurityMode`를 `TransportWithMessageCredential`로 설정하면 `NegotiateServiceCredential` 속성은 무시됩니다.  
  
### <a name="to-configure-a-wsfederationhttpbinding-in-code"></a>코드에서 WSFederationHttpBinding을 구성하려면  
  
1.  <xref:System.ServiceModel.WSFederationHttpBinding>의 인스턴스를 만듭니다.  
  
2.  필요에 따라 <xref:System.ServiceModel.WSFederationHttpSecurity.Mode%2A> 속성을 <xref:System.ServiceModel.WSFederationHttpSecurityMode> 또는 <xref:System.ServiceModel.WSFederationHttpSecurityMode.Message>로 설정합니다. 이외의 알고리즘 모음이 경우 <xref:System.ServiceModel.Security.SecurityAlgorithmSuite.Basic256%2A> 필요한 경우 설정의 <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.AlgorithmSuite%2A> 속성에서 가져온 값을 <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>합니다.  
  
3.  <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.NegotiateServiceCredential%2A> 속성을 적절하게 설정합니다.  
  
4.  설정의 <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.IssuedKeyType%2A> 속성을 <xref:System.IdentityModel.Tokens.SecurityKeyType> `SymmetricKey` 또는 합니다.`AsymmetricKey` 필요에 따라 합니다.  
  
5.  <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.IssuedTokenType%2A> 속성을 적절한 값으로 설정합니다. 값을 설정하지 않으면 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 기본적으로 SAML 1.1 토큰을 나타내는 "http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAMLV1.1"로 설정됩니다.  
  
6.  로컬 발급자가 지정되지 않은 경우 클라이언트에서는 필수적 요소이고 서비스에서는 선택적 요소입니다. 보안 토큰 서비스의 주소 및 ID 정보를 포함하는 <xref:System.ServiceModel.EndpointAddress>를 만들고 <xref:System.ServiceModel.EndpointAddress> 인스턴스를 <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.IssuerAddress%2A> 속성에 할당합니다.  
  
7.  로컬 발급자가 지정되지 않은 경우 클라이언트에서는 필수적 요소이고 서비스에서는 사용되지 않습니다. 만들기는 <xref:System.ServiceModel.Channels.Binding> 에 대 한는 `SecurityTokenService` 할당는 <xref:System.ServiceModel.Channels.Binding> 인스턴스는 <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.IssuerBinding%2A> 속성입니다.  
  
8.  클라이언트에서는 사용되지 않고 서비스에서는 선택적 요소입니다. 보안 토큰 서비스의 메타데이터에 대한 <xref:System.ServiceModel.EndpointAddress> 인스턴스를 만들어 `IssuerMetadataAddress` 속성에 할당합니다.  
  
9. 클라이언트와 서비스 둘 다에서 선택적 요소입니다. 하나 이상의 <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement> 인스턴스를 만들어 <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A> 속성에서 반환된 컬렉션에 추가합니다.  
  
10. 클라이언트와 서비스 둘 다에서 선택적 요소입니다. 하나 이상의 <xref:System.Xml.XmlElement> 인스턴스를 만들어 <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.TokenRequestParameters%2A> 속성에서 반환된 컬렉션에 추가합니다.  
  
### <a name="to-create-a-federated-endpoint-in-configuration"></a>구성에서 연합 끝점을 만들려면  
  
1.  만들기는 [ \<wsFederationHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) 의 자식으로는 [ \<바인딩 >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) 응용 프로그램 구성 파일의 요소입니다.  
  
2.  만들기는 [ \<바인딩 >](../../../../docs/framework/misc/binding.md) 의 자식으로 [ \<wsFederationHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) 설정 하 고는 `name` 특성을 적절 한 값입니다.  
  
3.  만들기는 `<security>` 의 자식으로 [ \<바인딩 >](../../../../docs/framework/misc/binding.md) 요소입니다.  
  
4.  필요에 따라 `mode` 요소의 `<security>` 특성을 `Message` 또는 `TransportWithMessageCredential`의 값으로 설정합니다.  
  
5.  `<message>` 요소를 `<security>` 요소의 자식으로 만듭니다.  
  
6.  선택 사항입니다. `algorithmSuite` 요소의 `<message>` 특성을 적절한 값으로 설정합니다. 기본값은 `Basic256`입니다.  
  
7.  선택 사항입니다. 비대칭 증명 키가 필요한 경우 `issuedKeyType` 요소의 `<message>` 특성을 `AsymmetricKey`로 설정합니다. 기본값은 `SymmetricKey`입니다.  
  
8.  선택 사항입니다. `issuedTokenType` 요소의 `<message>` 특성을 설정합니다.  
  
9. 로컬 발급자가 지정되지 않은 경우 클라이언트에서는 필수적 요소이고 서비스에서는 선택적 요소입니다. `<issuer>` 요소를 `<message>` 요소의 자식으로 만듭니다.  
  
10. `address` 특성을 `<issuer>` 요소로 설정하고 보안 토큰 서비스에서 토큰 요청을 수락하는 주소를 지정합니다.  
  
11. 선택 사항입니다. `<identity>` 자식 요소를 추가하고 보안 토큰 서비스의 ID를 지정합니다.  
  
12. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Id 및 인증 서비스](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)합니다.  
  
13. 로컬 발급자가 지정되지 않은 경우 클라이언트에서는 필수적 요소이고 서비스에서는 사용되지 않습니다. 만들기는 [ \<바인딩 >](../../../../docs/framework/misc/binding.md) 보안 토큰 서비스와 통신 하는 데 사용할 수 있는 바인딩 섹션에 있는 요소입니다. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]참조는 바인딩을 만드는 [하는 방법: 구성에서 서비스 바인딩 지정](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md)합니다.  
  
14. `binding` 요소의 `bindingConfiguration` 및 `<issuer>` 특성을 설정하여 이전 단계에서 만든 바인딩을 지정합니다.  
  
15. 클라이언트에서는 사용되지 않고 서비스에서는 선택적 요소입니다. `<issuerMetadata>` 요소를 <`message`> 요소의 자식으로 만듭니다. 그런 다음 `address` 요소의 `<issuerMetadata>` 특성에서 보안 토큰 서비스가 해당 메타데이터를 게시할 주소를 지정합니다. 선택적으로 `<identity>` 자식 요소를 추가하고 보안 토큰 서비스의 ID를 지정합니다.  
  
16. 클라이언트와 서비스 둘 다에서 선택적 요소입니다. `<claimTypeRequirements>` 요소를 `<message>` 요소의 자식으로 추가합니다. 필수 및 선택적 클레임을 지정 추가 하 여 서비스를 사용 하 [ \<추가 >](../../../../docs/framework/configure-apps/file-schema/wcf/add-of-claimtyperequirements.md) 요소를 사용 하 여 `<claimTypeRequirements>` 요소 및 지정 된 클레임 형식는 `claimType` 특성입니다. `isOptional` 특성을 설정하여 지정된 클레임이 필수 또는 선택적 요소인지 지정합니다.  
  
## <a name="example"></a>예제  
 다음 코드 샘플에서는 명령적으로 `WSFederationHttpBinding`을 설정하는 코드를 보여 줍니다.  
  
 [!code-csharp[c_FederationBinding#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_federationbinding/cs/source.cs#2)] 
 [!code-vb[c_FederationBinding#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_federationbinding/vb/source.vb#2)]  
  
## <a name="see-also"></a>참고 항목  
 [페더레이션](../../../../docs/framework/wcf/feature-details/federation.md)  
 [Federation 샘플](../../../../docs/framework/wcf/samples/federation-sample.md)  
 [방법: 사용 안 함 보안 WSFederationHttpBinding에서 세션](../../../../docs/framework/wcf/feature-details/how-to-disable-secure-sessions-on-a-wsfederationhttpbinding.md)
