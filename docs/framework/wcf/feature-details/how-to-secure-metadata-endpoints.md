---
title: "방법: 메타데이터 끝점 보안 설정 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9f71b6ae-737c-4382-8d89-0a7b1c7e182b
caps.latest.revision: 13
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 13
---
# 방법: 메타데이터 끝점 보안 설정
서비스의 메타데이터에는 악의적인 사용자가 활용할 수 있는 응용 프로그램에 대한 중요한 정보가 들어 있습니다.또한 서비스의 소비자는 서비스의 메타데이터를 가져오기 위한 보안 메커니즘이 필요할 수도 있습니다.따라서 보안 끝점을 사용하여 메타데이터를 게시해야 하는 경우가 있습니다.  
  
 일반적으로 메타데이터 끝점의 보안은 응용 프로그램 끝점의 보안을 위해 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]에 정의된 표준 보안 메커니즘을 통해 이루어집니다.\([!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][보안 개요](../../../../docs/framework/wcf/feature-details/security-overview.md).\)  
  
 이 항목에서는 SSL\(Secure Sockets Layer\) 인증서 즉, HTTPS 끝점으로 보안되는 끝점을 만드는 방법에 대해 단계별로 설명합니다.  
  
### 코드에 보안 HTTPS GET 메타데이터 끝점을 만들려면  
  
1.  적절한 X.509 인증서를 사용하여 포트를 구성합니다.인증서는 신뢰할 수 있는 기관에서 가져와야 하며 "서비스 인증"의 용도로 사용해야 합니다. HttpCfg.exe 도구를 사용하여 인증서를 포트에 첨부해야 합니다.[방법: SSL 인증서를 사용하여 포트 구성](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md)을 참조하십시오.  
  
    > [!IMPORTANT]
    >  인증서의 주체 또는 인증서의 DNS\(Domain Name System\)는 컴퓨터의 이름과 일치해야 합니다.이는 HTTPS 메커니즘에서 수행하는 첫 번째 단계 중 하나로서 인증서가 호출된 주소와 동일한 URI\(Uniform Resource Identifier\)에 발급되었는지 확인하는 단계이므로 중요합니다.  
  
2.  <xref:System.ServiceModel.Description.ServiceMetadataBehavior> 클래스의 새 인스턴스를 만듭니다.  
  
3.  <xref:System.ServiceModel.Description.ServiceMetadataBehavior> 클래스의 <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A> 속성을 `true`로 설정합니다.  
  
4.  <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetUrl%2A> 속성을 적절한 URL로 설정합니다.절대 주소를 지정하는 경우 URL은 "https:\/\/" 스키마로 시작해야 합니다.상대 주소를 지정하는 경우 서비스 호스트의 HTTPS 기본 주소를 입력해야 합니다.이 속성을 설정하지 않으면 기본 주소는 ""이거나 바로 서비스의 HTTPS 기본 주소로 설정됩니다.  
  
5.  다음 코드에서처럼 <xref:System.ServiceModel.Description.ServiceDescription> 클래스의 <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A> 속성이 반환하는 동작 컬렉션에 인스턴스를 추가합니다.  
  
     [!code-csharp[c_HowToSecureEndpoint#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtosecureendpoint/cs/source.cs#1)]
     [!code-vb[c_HowToSecureEndpoint#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtosecureendpoint/vb/source.vb#1)]  
  
### 구성에 보안 HTTPS GET 메타데이터 끝점을 만들려면  
  
1.  [\<behaviors\>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) 요소를 서비스 구성 파일의 [\<system.serviceModel\>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) 요소에 추가합니다.  
  
2.  [\<serviceBehaviors\>](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) 요소를 [\<behaviors\>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) 요소에 추가합니다.  
  
3.  [\<behavior\>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) 요소를 `<serviceBehaviors>` 요소에 추가합니다.  
  
4.  `<behavior>` 요소의 `name` 특성을 적절한 값으로 설정합니다.`name` 특성이 필요합니다.아래 예제에서는 `mySvcBehavior` 값을 사용합니다.  
  
5.  [\<serviceMetadata\>](../../../../docs/framework/configure-apps/file-schema/wcf/servicemetadata.md)를 `<behavior>` 요소에 추가합니다.  
  
6.  `<serviceMetadata>` 요소의 `httpsGetEnabled` 특성을 `true`로 설정합니다.  
  
7.  `<serviceMetadata>` 요소의 `httpsGetUrl` 특성을 적절한 값으로 설정합니다.절대 주소를 지정하는 경우 URL은 "https:\/\/" 스키마로 시작해야 합니다.상대 주소를 지정하는 경우 서비스 호스트의 HTTPS 기본 주소를 입력해야 합니다.이 속성을 설정하지 않으면 기본 주소는 ""이거나 바로 서비스의 HTTPS 기본 주소로 설정됩니다.  
  
8.  서비스에 해당 동작을 사용하려면 [\<service\>](../../../../docs/framework/configure-apps/file-schema/wcf/service.md) 요소의 `behaviorConfiguration` 특성을 동작 요소의 이름 특성 값으로 설정합니다.다음 구성 코드에서는 자세한 예제를 보여 줍니다.  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>  
    <configuration>  
     <system.serviceModel>  
      <behaviors>  
       <serviceBehaviors>  
        <behavior name="mySvcBehavior">  
         <serviceMetadata httpsGetEnabled="true"   
              httpsGetUrl="https://localhost:8036/calcMetadata" />  
        </behavior>  
       </serviceBehaviors>  
      </behaviors>  
     <services>  
      <service behaviorConfiguration="mySvcBehavior"   
            name="Microsoft.Security.Samples.Calculator">  
       <endpoint address="http://localhost:8037/ServiceModelSamples/calculator"  
       binding="wsHttpBinding" bindingConfiguration=""     
       contract="Microsoft.Security.Samples.ICalculator" />  
      </service>  
     </services>  
    </system.serviceModel>  
    </configuration>  
    ```  
  
## 예제  
 다음 예제에서는 <xref:System.ServiceModel.ServiceHost> 클래스의 인스턴스를 만들고 끝점을 추가합니다.그런 다음 코드는 <xref:System.ServiceModel.Description.ServiceMetadataBehavior> 클래스의 인스턴스를 만들고, 속성을 설정하여 보안 메타데이터 교환 지점을 만듭니다.  
  
 [!code-csharp[c_HowToSecureEndpoint#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtosecureendpoint/cs/source.cs#0)]
 [!code-vb[c_HowToSecureEndpoint#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtosecureendpoint/vb/source.vb#0)]  
  
## 코드 컴파일  
 코드 예제에서는 다음 네임스페이스를 사용합니다.  
  
-   <xref:System.ServiceModel?displayProperty=fullName>  
  
-   <xref:System.ServiceModel.Description?displayProperty=fullName>  
  
## 참고 항목  
 <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A>   
 <xref:System.ServiceModel.Description.ServiceMetadataBehavior>   
 <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetUrl%2A>   
 [방법: SSL 인증서를 사용하여 포트 구성](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md)   
 [인증서 작업](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)   
 [메타데이터 관련 보안 고려 사항](../../../../docs/framework/wcf/feature-details/security-considerations-with-metadata.md)   
 [서비스 및 클라이언트에 보안 설정](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)