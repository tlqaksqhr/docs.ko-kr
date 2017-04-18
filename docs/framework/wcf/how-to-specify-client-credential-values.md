---
title: "방법: 클라이언트 자격 증명 값 지정 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 82293d7f-471a-4549-8f19-0be890e7b074
caps.latest.revision: 28
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 28
---
# 방법: 클라이언트 자격 증명 값 지정
서비스는 [!INCLUDE[indigo1](../../../includes/indigo1-md.md)]를 사용하여 클라이언트가 서비스를 인증하는 방법을 지정할 수 있습니다.  예를 들면 서비스는 클라이언트가 인증서를 사용하여 인증하도록 규정할 수 있습니다.  
  
### 클라이언트 자격 증명 형식을 결정하려면  
  
1.  서비스의 메타데이터 끝점에서 메타데이터를 검색합니다.  메타데이터는 보통 사용자가 선택한 프로그래밍 언어로 된 클라이언트 코드\(기본적으로 Visual C\#\)와 XML 구성 파일의 두 파일로 구성됩니다.  메타데이터를 검색하는 방법 중 하나는 Svcutil.exe 도구를 사용해 클라이언트 코드와 클라이언트 구성을 반환하는 것입니다.  자세한 내용은 [메타데이터 검색](../../../docs/framework/wcf/feature-details/retrieving-metadata.md) 및 [ServiceModel Metadata 유틸리티 도구\(Svcutil.exe\)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)를 참조하세요.  
  
2.  XML 구성 파일을 엽니다.  Svcutil.exe 도구를 사용하는 경우 이 파일의 기본 이름은 Output.config입니다.  
  
3.  **mode** 특성이 있는 **\<security\>** 요소\(**\<security mode \=** `MessageOrTransport`**\>**\)를 찾습니다. 여기서 `MessageOrTransport`는 보안 모드 중 하나로 설정됩니다.  
  
4.  모드 값과 일치하는 자식 요소를 찾습니다.  예를 들어 모드가 **Message**로 설정된 경우 **\<security\>** 요소에 포함된 **\<message\>** 요소를 찾습니다.  
  
5.  **clientCredentialType** 특성에 할당된 값을 확인하십시오.  실제 값은 사용하는 모드\(Transport\/Message\)에 따라 다릅니다.  
  
 다음 XML 코드는 메시지 보안을 사용하며 인증서를 사용해 클라이언트를 인증하도록 하는 클라이언트의 구성을 보여 줍니다.  
  
```  
<security mode="Message">  
    <transport clientCredentialType="Windows" proxyCredentialType="None"  
        realm="" />  
     <message clientCredentialType="Certificate" negotiateServiceCredential="true"  
    algorithmSuite="Default" establishSecurityContext="true" />  
</security>  
```  
  
## 예제: 인증서를 클라이언트 자격 증명으로 사용하는 TCP Transport 모드  
 이 예제에서는 보안 모드를 Transport 모드로 설정하고 클라이언트 자격 증명 값을 X.509 인증서로 설정합니다.  다음 절차에서는 코드와 구성에 클라이언트에 대한 클라이언트 자격 증명 값을 설정하는 방법을 보여 줍니다.  여기서는 [ServiceModel Metadata 유틸리티 도구\(Svcutil.exe\)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)를 사용하여 서비스에서 메타데이터\(코드 및 구성\)를 반환한 것으로 가정합니다.  [!INCLUDE[crdefault](../../../includes/crdefault-md.md)] [방법: 클라이언트 만들기](../../../docs/framework/wcf/how-to-create-a-wcf-client.md).  
  
#### 코드에 클라이언트에 대한 클라이언트 자격 증명 값을 지정하려면  
  
1.  [ServiceModel Metadata 유틸리티 도구\(Svcutil.exe\)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)를 사용하여 서비스에서 코드 및 구성을 생성합니다.  
  
2.  생성된 코드를 사용하여 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 클라이언트의 인스턴스를 만듭니다.  
  
3.  클라이언트 클래스에서 <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A> 클래스의 <xref:System.ServiceModel.ClientBase%601> 속성을 적절한 값으로 설정합니다.  이 예제에서는 <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A> 클래스의 <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential> 메서드를 사용하여 속성을 X.509 인증서로 설정합니다.  
  
     [!code-csharp[c_TcpService#4](../../../samples/snippets/csharp/VS_Snippets_CFX/c_tcpservice/cs/source.cs#4)]
     [!code-vb[c_TcpService#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_tcpservice/vb/source.vb#4)]  
  
     <xref:System.Security.Cryptography.X509Certificates.X509FindType> 클래스의 열거를 사용할 수 있습니다.  주체 이름은 만료 날짜로 인해 인증서가 변경된 경우 여기서 사용됩니다.  주체 이름을 사용하면 인프라에서 인증서를 다시 찾을 수 있습니다.  
  
#### 구성에 클라이언트에 대한 클라이언트 자격 증명 값을 지정하려면  
  
1.  [\<behavior\>](../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) 요소를 [\<behaviors\>](../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) 요소에 추가합니다.  
  
2.  [\<clientCredentials\>](../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) 요소를 [\<behaviors\>](../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) 요소에 추가합니다.  필수 `name` 특성을 적절한 값으로 설정해야 합니다.  
  
3.  [\<clientCertificate\>](../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md) 요소를 [\<clientCredentials\>](../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) 요소에 추가합니다.  
  
4.  다음 코드에서처럼 `storeLocation`, `storeName`, `x509FindType` 및 `findValue` 특성을 적절한 값으로 설정합니다.  인증서[!INCLUDE[crabout](../../../includes/crabout-md.md)] [인증서 작업](../../../docs/framework/wcf/feature-details/working-with-certificates.md)을 참조하세요.  
  
    ```  
    <behaviors>  
       <endpointBehaviors>  
          <behavior name="endpointCredentialBehavior">  
            <clientCredentials>  
              <clientCertificate findValue="Contoso.com"   
                                 storeLocation="LocalMachine"  
                                 storeName="TrustedPeople"  
                                 x509FindType="FindBySubjectName" />  
            </clientCredentials>  
          </behavior>  
       </endpointBehaviors>  
    </behaviors>  
    ```  
  
5.  클라이언트를 구성할 때 다음 코드에서처럼 `behaviorConfiguration` 요소의 `<endpoint>` 특성을 설정하여 동작을 지정합니다.  끝점 요소는 [\<client\>](../../../docs/framework/configure-apps/file-schema/wcf/client.md) 요소의 자식입니다.  또한 `bindingConfiguration` 특성을 클라이언트에 대한 바인딩으로 설정하여 바인딩 구성 이름을 지정합니다.  생성된 구성 파일을 사용하는 경우 바인딩의 이름이 자동으로 생성됩니다.  이 예제에서 이름은 `"tcpBindingWithCredential"`입니다.  
  
    ```  
    <client>  
      <endpoint name =""  
                address="net.tcp://contoso.com:8036/aloha"  
                binding="netTcpBinding"  
                bindingConfiguration="tcpBindingWithCredential"  
                behaviorConfiguration="endpointCredentialBehavior" />  
    </client>  
    ```  
  
## 참고 항목  
 <xref:System.ServiceModel.NetTcpBinding>   
 <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A>   
 <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential>   
 <xref:System.ServiceModel.ClientBase%601>   
 <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential>   
 [WCF 보안 프로그래밍](../../../docs/framework/wcf/feature-details/programming-wcf-security.md)   
 [자격 증명 형식 선택](../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)   
 [ServiceModel Metadata 유틸리티 도구\(Svcutil.exe\)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)   
 [인증서 작업](../../../docs/framework/wcf/feature-details/working-with-certificates.md)   
 [방법: 클라이언트 만들기](../../../docs/framework/wcf/how-to-create-a-wcf-client.md)   
 [\<netTcpBinding\>](../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md)   
 [\<security\>](../../../docs/framework/configure-apps/file-schema/wcf/security-of-nettcpbinding.md)   
 [\<message\>](../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-nettcpbinding.md)   
 [\<behavior\>](../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)   
 [\<behaviors\>](../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md)   
 [\<clientCertificate\>](../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md)   
 [\<clientCredentials\>](../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)