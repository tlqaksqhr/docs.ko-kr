---
title: "연습: 사용자 지정 클라이언트 및 서비스 자격 증명 만들기"
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
ms.assetid: 2b5ba5c3-0c6c-48e9-9e46-54acaec443ba
caps.latest.revision: "13"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 6eae3a91856feff83e8e199cf552a987d99d5ba2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-creating-custom-client-and-service-credentials"></a>연습: 사용자 지정 클라이언트 및 서비스 자격 증명 만들기
이 항목에서는 사용자 지정 클라이언트와 서비스 자격 증명을 구현하는 방법 및 응용 프로그램 코드로부터 사용자 지정 자격 증명을 사용하는 방법을 보여 줍니다.  
  
## <a name="credentials-extensibility-classes"></a>자격 증명 확장성 클래스  
 <xref:System.ServiceModel.Description.ClientCredentials> 및 <xref:System.ServiceModel.Description.ServiceCredentials> 클래스는 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 보안 확장성에 대한 주요 진입점입니다. 이러한 자격 증명 클래스는 API를 제공합니다. 이 API를 통해 응용 프로그램 코드에서는 자격 증명 정보를 설정하고, 자격 증명 형식을 보안 토큰으로 변환할 수 있습니다. (*보안 토큰* 양식 자격 증명 정보를 SOAP 메시지 내부에서 전송 하는 데 사용 됩니다.) 이러한 자격 증명 클래스의 책임은 다음과 같은 두 가지 영역으로 나눠 볼 수 있습니다.  
  
-   응용 프로그램에서 자격 증명 정보를 설정하도록 API 제공  
  
-   <xref:System.IdentityModel.Selectors.SecurityTokenManager> 구현을 위한 팩터리 역할 수행  
  
 <xref:System.ServiceModel.Description.ClientCredentials> 및 <xref:System.ServiceModel.Description.ServiceCredentials> 클래스는 모두 <xref:System.ServiceModel.Security.SecurityCredentialsManager> 반환에 대한 계약을 정의하는 추상 <xref:System.IdentityModel.Selectors.SecurityTokenManager> 클래스로부터 상속됩니다.  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]에 적합 하 게 하 고 자격 증명 클래스는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 보안 아키텍처 참조 [보안 아키텍처](http://msdn.microsoft.com/en-us/16593476-d36a-408d-808c-ae6fd483e28f)합니다.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 제공되는 기본 구현은 시스템 제공 자격 증명 형식을 지원하고, 이러한 자격 증명 형식을 처리할 수 있는 보안 토큰 관리자를 만듭니다.  
  
## <a name="reasons-to-customize"></a>사용자 지정해야 하는 이유  
 클라이언트 또는 서비스 자격 증명 클래스를 사용자 지정해야 하는 이유는 여러 가지가 있습니다. 가장 먼저 시스템 제공 자격 증명 형식의 처리와 관련하여 기본 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 보안 동작을 변경해야 하며, 주요 이유는 다음과 같습니다.  
  
-   다른 확장성 지점을 사용하여 변경할 수 없는 내용을 변경해야 합니다.  
  
-   새 자격 증명 형식을 추가해야 합니다.  
  
-   새 사용자 지정 보안 토큰 형식을 추가해야 합니다.  
  
 이 항목에서는 사용자 지정 클라이언트와 서비스 자격 증명을 구현하는 방법 및 응용 프로그램 코드로부터 이들을 사용하는 방법에 대해 설명합니다.  
  
## <a name="first-in-a-series"></a>시리즈의 첫 번째 단계  
 첫 번째 단계에서는 사용자 지정 자격 증명 클래스를 만들기만 하면 됩니다. 자격 증명을 사용자 지정하는 이유가 자격 증명 구축, 보안 토큰 serialization 또는 인증과 관련된 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 동작을 변경하려는 것이기 때문입니다. 이 단원의 다른 항목에서는 사용자 지정 serializer 및 인증자를 만드는 방법에 대해 설명합니다. 이와 관련하여 사용자 지정 자격 증명 클래스를 만드는 것이 이 시리즈의 첫 번째 항목입니다. 후속 작업(사용자 지정 serializer 및 인증자 만들기)은 사용자 지정 자격 증명을 만든 이후에야 수행할 수 있습니다. 이 항목을 기초로 한 추가 항목은 다음과 같습니다.  
  
-   [방법: 사용자 지정 보안 토큰 공급자 만들기](../../../../docs/framework/wcf/extending/how-to-create-a-custom-security-token-provider.md)  
  
-   [방법: 사용자 지정 보안 토큰 인증자 만들기](../../../../docs/framework/wcf/extending/how-to-create-a-custom-security-token-authenticator.md)  
  
-   [방법: 사용자 지정 토큰 만들기](../../../../docs/framework/wcf/extending/how-to-create-a-custom-token.md)합니다.  
  
## <a name="procedures"></a>절차  
  
#### <a name="to-implement-custom-client-credentials"></a>사용자 지정 클라이언트 자격 증명을 구현하려면  
  
1.  <xref:System.ServiceModel.Description.ClientCredentials> 클래스에서 파생된 새 클래스를 정의합니다.  
  
2.  선택 사항입니다. 새 자격 증명 형식에 대해 새 메서드 또는 속성을 추가합니다. 새 자격 증명 형식을 추가하지 않으려면 이 단계를 건너뜁니다. 다음 예제에서는 `CreditCardNumber` 속성을 추가합니다.  
  
3.  <xref:System.ServiceModel.Security.SecurityCredentialsManager.CreateSecurityTokenManager%2A> 메서드를 재정의합니다. 이 메서드는 사용자 지정 클라이언트 자격 증명을 사용할 때 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 보안 인프라에서 자동으로 호출합니다. 이 메서드는 <xref:System.IdentityModel.Selectors.SecurityTokenManager> 클래스 구현의 인스턴스를 만들고 반환합니다.  
  
    > [!IMPORTANT]
    >  <xref:System.ServiceModel.Security.SecurityCredentialsManager.CreateSecurityTokenManager%2A> 메서드를 재정의하여 사용자 지정 보안 토큰 관리자를 만든다는 점이 중요합니다. <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager>에서 파생된 보안 토큰 관리자는 <xref:System.IdentityModel.Selectors.SecurityTokenProvider>에서 파생된 사용자 지정 보안 토큰 공급자를 반환하여 실제 보안 토큰을 만들어야 합니다. 보안 토큰을 만들 때 이 방식을 따르지 않으면 <xref:System.ServiceModel.ChannelFactory> 개체를 캐시할 때(WCF 클라이언트 프록시의 기본 동작임) 응용 프로그램의 기능이 제대로 수행되지 않아 권한 상승 공격이 발생할 수 있습니다. 사용자 지정 자격 증명 개체는 <xref:System.ServiceModel.ChannelFactory>의 일부분으로 캐시됩니다. 그러나 사용자 지정 <xref:System.IdentityModel.Selectors.SecurityTokenManager>는 호출할 때마다 만들어지므로 토큰 생성 논리가 <xref:System.IdentityModel.Selectors.SecurityTokenManager>에 있는 한 보안 위협은 완화됩니다.  
  
4.  <xref:System.ServiceModel.Description.ClientCredentials.CloneCore%2A> 메서드를 재정의합니다.  
  
     [!code-csharp[c_CustomCredentials#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcredentials/cs/source.cs#1)]
     [!code-vb[c_CustomCredentials#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcredentials/vb/client/client.vb#1)]  
  
#### <a name="to-implement-a-custom-client-security-token-manager"></a>사용자 지정 클라이언트 보안 토큰 관리자를 구현하려면  
  
1.  <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager>에서 파생된 새 클래스를 정의합니다.  
  
2.  선택 사항입니다. 사용자 지정 <xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenProvider%28System.IdentityModel.Selectors.SecurityTokenRequirement%29> 구현을 만들어야 하는 경우 <xref:System.IdentityModel.Selectors.SecurityTokenProvider> 메서드를 재정의합니다. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]사용자 지정 보안 토큰 공급자 참조 [하는 방법: 사용자 지정 보안 토큰 공급자 만들기](../../../../docs/framework/wcf/extending/how-to-create-a-custom-security-token-provider.md)합니다.  
  
3.  선택 사항입니다. 사용자 지정 <xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenAuthenticator%28System.IdentityModel.Selectors.SecurityTokenRequirement%2CSystem.IdentityModel.Selectors.SecurityTokenResolver%40%29> 구현을 만들어야 하는 경우 <xref:System.IdentityModel.Selectors.SecurityTokenAuthenticator> 메서드를 재정의합니다. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]사용자 지정 보안 토큰 인증자 참조 [하는 방법: 사용자 지정 보안 토큰 인증자를 만들](../../../../docs/framework/wcf/extending/how-to-create-a-custom-security-token-authenticator.md)합니다.  
  
4.  선택 사항입니다. 사용자 지정 <xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenSerializer%2A>를 만들어야 하는 경우 <xref:System.IdentityModel.Selectors.SecurityTokenSerializer> 메서드를 재정의합니다. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]사용자 지정 보안 토큰 및 사용자 지정 보안 토큰 serializer 참조 [하는 방법: 사용자 지정 토큰 만들기](../../../../docs/framework/wcf/extending/how-to-create-a-custom-token.md)합니다.  
  
     [!code-csharp[c_CustomCredentials#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcredentials/cs/source.cs#2)]
     [!code-vb[c_CustomCredentials#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcredentials/vb/client/client.vb#2)]  
  
#### <a name="to-use-a-custom-client-credentials-from-application-code"></a>응용 프로그램 코드로부터 사용자 지정 클라이언트 자격 증명을 사용하려면  
  
1.  서비스 인터페이스를 나타내는 생성된 클라이언트의 인스턴스를 만들거나 사용자가 통신하려고 하는 서비스를 가리키는 <xref:System.ServiceModel.ChannelFactory>의 인스턴스를 만듭니다.  
  
2.  <xref:System.ServiceModel.Description.ServiceEndpoint.Behaviors%2A> 속성을 통해 액세스할 수 있는 <xref:System.ServiceModel.ChannelFactory.Endpoint%2A> 컬렉션으로부터 시스템 제공 클라이언트 자격 증명 동작을 제거합니다.  
  
3.  사용자 지정 클라이언트 자격 증명 클래스의 새 인스턴스를 만들고 이 인스턴스를 <xref:System.ServiceModel.Description.ServiceEndpoint.Behaviors%2A> 속성을 통해 액세스할 수 있는 <xref:System.ServiceModel.ChannelFactory.Endpoint%2A> 컬렉션에 추가합니다.  
  
     [!code-csharp[c_CustomCredentials#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcredentials/cs/source.cs#3)]
     [!code-vb[c_CustomCredentials#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcredentials/vb/client/client.vb#3)]  
  
 이전 절차는 응용 프로그램 코드에서 클라이언트 자격 증명을 사용하는 방법을 보여 줍니다. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 자격 증명은 응용 프로그램 구성 파일을 사용하여 구성할 수도 있습니다. 소스를 수정하고, 다시 컴파일하고, 다시 배포하지 않고도 응용 프로그램 매개 변수를 수정할 수 있기 때문에 종종 응용 프로그램 구성을 사용하는 것이 하드 코딩보다 좋습니다.  
  
 다음 절차에서는 사용자 지정 자격 증명을 구성하기 위해 지원을 제공하는 방법에 대해 설명합니다.  
  
#### <a name="creating-a-configuration-handler-for-custom-client-credentials"></a>사용자 지정 클라이언트 자격 증명에 대한 구성 처리기 만들기  
  
1.  <xref:System.ServiceModel.Configuration.ClientCredentialsElement>에서 파생된 새 클래스를 정의합니다.  
  
2.  선택 사항입니다. 응용 프로그램 구성을 통해 노출하려고 하는 모든 추가 구성 매개 변수에 대한 속성을 추가합니다. 아래 예제에서는 이름이 `CreditCardNumber`인 속성 하나를 추가합니다.  
  
3.  구성 요소를 사용하여 만들어진 사용자 지정 클라이언트 자격 증명 클래스의 형식을 반환하려면 <xref:System.ServiceModel.Configuration.BehaviorExtensionElement.BehaviorType%2A> 속성을 재정의합니다.  
  
4.  <xref:System.ServiceModel.Configuration.BehaviorExtensionElement.CreateBehavior%2A> 메서드를 재정의합니다. 이 메서드는 구성 파일로부터 로드된 설정을 기반으로 사용자 지정 자격 증명 클래스의 인스턴스를 만들고 반환합니다. 사용자 지정 클라이언트 자격 증명 인스턴스로 로드된 시스템 제공 자격 증명 설정을 검색하려면 이 메서드로부터 기본 <xref:System.ServiceModel.Configuration.ClientCredentialsElement.ApplyConfiguration%28System.ServiceModel.Description.ClientCredentials%29> 메서드를 호출합니다.  
  
5.  선택 사항입니다. 2단계에서 속성을 추가한 경우 구성 프레임워크에 대한 추가 구성 설정을 등록하여 이를 인식할 수 있도록 하려면 <xref:System.Configuration.ConfigurationElement.Properties%2A> 속성을 재정의해야 합니다. 사용자의 속성과 기본 클래스 속성을 조합하면 이 사용자 지정 클라이언트 자격 증명 구성 요소를 통해 시스템 제공 설정을 구성할 수 있습니다.  
  
     [!code-csharp[c_CustomCredentials#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcredentials/cs/source.cs#7)]
     [!code-vb[c_CustomCredentials#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcredentials/vb/service/service.vb#7)]  
  
 구성 처리기 클래스가 있으면 이를 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 구성 프레임워크로 통합할 수 있습니다. 이를 통해 다음 절차에서처럼 사용자 지정 클라이언트 자격 증명을 클라이언트 끝점 동작 요소에서 사용할 수 있습니다.  
  
#### <a name="to-register-and-use-a-custom-client-credentials-configuration-handler-in-the-application-configuration"></a>응용 프로그램 구성에서 사용자 지정 클라이언트 자격 증명 구성 처리기를 등록 및 사용하려면  
  
1.  추가 <`extensions`> 요소와 <`behaviorExtensions`> 요소를 구성 파일입니다.  
  
2.  추가 <`add`> 요소는 <`behaviorExtensions`> 요소는 `name` 특성을 적절 한 값으로.  
  
3.  `type` 특성을 정규화된 형식 이름으로 설정합니다. 또한 어셈블리 이름과 기타 어셈블리 특성을 포함시킵니다.  
  
    ```xml  
    <system.serviceModel>  
      <extensions>  
        <behaviorExtensions>  
          <add name="myClientCredentials" type="Microsoft.ServiceModel.Samples.MyClientCredentialsConfigHandler, CustomCredentials, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null" />  
        </behaviorExtensions>  
      </extensions>  
    <system.serviceModel>  
    ```  
  
4.  구성 처리기를 등록 한 후 사용자 지정 자격 증명 요소를 사용할 수는 시스템에서 제공 하는 대신 동일한 구성 파일 <`clientCredentials`> 요소입니다. 시스템 제공 속성 및 구성 처리기 구현에 추가한 새 속성을 모두 사용할 수 있습니다. 다음 예제에서는 `creditCardNumber` 특성을 사용하여 사용자 지정 속성의 값을 설정합니다.  
  
    ```xml  
    <behaviors>  
      <endpointBehaviors>  
        <behavior name="myClientCredentialsBehavior">  
          <myClientCredentials creditCardNumber="123-123-123"/>  
        </behavior>  
      </endpointBehaviors>  
    </behaviors>  
    ```  
  
#### <a name="to-implement-custom-service-credentials"></a>사용자 지정 서비스 자격 증명을 구현하려면  
  
1.  <xref:System.ServiceModel.Description.ServiceCredentials>에서 파생된 새 클래스를 정의합니다.  
  
2.  선택 사항입니다. 추가 중인 새 자격 증명 값에 대한 API를 제공하려면 새 속성을 추가합니다. 새 자격 증명 값을 추가하지 않으려면 이 단계를 건너뜁니다. 다음 예제에서는 `AdditionalCertificate` 속성을 추가합니다.  
  
3.  <xref:System.ServiceModel.Security.SecurityCredentialsManager.CreateSecurityTokenManager%2A> 메서드를 재정의합니다. 이 메서드는 사용자 지정 클라이언트 자격 증명을 사용할 때 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 인프라에서 자동으로 호출합니다. 이 메서드는 <xref:System.IdentityModel.Selectors.SecurityTokenManager> 클래스 구현의 인스턴스를 만들고 반환하며, 이에 대해서는 다음 절차에서 설명합니다.  
  
4.  선택 사항입니다. <xref:System.ServiceModel.Description.ServiceCredentials.CloneCore%2A> 메서드를 재정의합니다. 이는 새 속성 또는 내부 필드를 사용자 지정 클라이언트 자격 증명 구현에 추가하는 경우에만 필요합니다.  
  
     [!code-csharp[c_CustomCredentials#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcredentials/cs/source.cs#4)]
     [!code-vb[c_CustomCredentials#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcredentials/vb/service/service.vb#4)]  
  
#### <a name="to-implement-a-custom-service-security-token-manager"></a>사용자 지정 서비스 보안 토큰 관리자를 구현하려면  
  
1.  <xref:System.ServiceModel.Security.ServiceCredentialsSecurityTokenManager> 클래스에서 파생된 새 클래스를 정의합니다.  
  
2.  선택 사항입니다. 사용자 지정 <xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenProvider%2A> 구현을 만들어야 하는 경우 <xref:System.IdentityModel.Selectors.SecurityTokenProvider> 메서드를 재정의합니다. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]사용자 지정 보안 토큰 공급자 참조 [하는 방법: 사용자 지정 보안 토큰 공급자 만들기](../../../../docs/framework/wcf/extending/how-to-create-a-custom-security-token-provider.md)합니다.  
  
3.  선택 사항입니다. 사용자 지정 <xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenAuthenticator%2A> 구현을 만들어야 하는 경우 <xref:System.IdentityModel.Selectors.SecurityTokenAuthenticator> 메서드를 재정의합니다. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]사용자 지정 보안 토큰 인증자 참조 [하는 방법: 사용자 지정 보안 토큰 인증자를 만들](../../../../docs/framework/wcf/extending/how-to-create-a-custom-security-token-authenticator.md) 항목입니다.  
  
4.  선택 사항입니다. 사용자 지정 <xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenSerializer%28System.IdentityModel.Selectors.SecurityTokenVersion%29>를 만들어야 하는 경우 <xref:System.IdentityModel.Selectors.SecurityTokenSerializer> 메서드를 재정의합니다. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]사용자 지정 보안 토큰 및 사용자 지정 보안 토큰 serializer 참조 [하는 방법: 사용자 지정 토큰 만들기](../../../../docs/framework/wcf/extending/how-to-create-a-custom-token.md)합니다.  
  
     [!code-csharp[c_CustomCredentials#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcredentials/cs/source.cs#5)]
     [!code-vb[c_CustomCredentials#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcredentials/vb/service/service.vb#5)]  
  
#### <a name="to-use-custom-service-credentials-from-application-code"></a>응용 프로그램 코드로부터 사용자 지정 서비스 자격 증명을 사용하려면  
  
1.  <xref:System.ServiceModel.ServiceHost>의 인스턴스를 만듭니다.  
  
2.  <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A> 컬렉션으로부터 시스템 제공 서비스 자격 증명 동작을 제거합니다.  
  
3.  사용자 지정 서비스 자격 증명 클래스의 새 인스턴스를 만들고 이 인스턴스를 <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A> 컬렉션에 추가합니다.  
  
     [!code-csharp[c_CustomCredentials#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcredentials/cs/source.cs#6)]
     [!code-vb[c_CustomCredentials#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcredentials/vb/service/service.vb#6)]  
  
 위의 "`To create a configuration handler for custom client credentials`" 및 "`To register and use a custom client credentials configuration handler in the application configuration`" 절차에서 설명된 단계를 사용하여 구성에 대한 지원을 추가합니다. 유일한 차이점은 구성 처리기에 대한 기본 클래스로 <xref:System.ServiceModel.Configuration.ServiceCredentialsElement> 클래스 대신에 <xref:System.ServiceModel.Configuration.ClientCredentialsElement> 클래스를 사용하는 것입니다. 그런 다음 사용자 지정 서비스 자격 증명 요소는 시스템 제공 `<serviceCredentials>` 요소가 사용될 때 사용할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ServiceModel.Description.ClientCredentials>  
 <xref:System.ServiceModel.Description.ServiceCredentials>  
 <xref:System.ServiceModel.Security.SecurityCredentialsManager>  
 <xref:System.IdentityModel.Selectors.SecurityTokenManager>  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement>  
 <xref:System.ServiceModel.Configuration.ServiceCredentialsElement>  
 [방법: 사용자 지정 보안 토큰 공급자 만들기](../../../../docs/framework/wcf/extending/how-to-create-a-custom-security-token-provider.md)  
 [방법: 사용자 지정 보안 토큰 인증자 만들기](../../../../docs/framework/wcf/extending/how-to-create-a-custom-security-token-authenticator.md)  
 [방법: 사용자 지정 토큰 만들기](../../../../docs/framework/wcf/extending/how-to-create-a-custom-token.md)
