---
title: "방법: 보안 모드 설정 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "모드 속성"
  - "WCF, 보안"
  - "WCF, 보안 모드"
ms.assetid: 6e01dd9f-b5dd-4474-b24c-06e124de4ff7
caps.latest.revision: 22
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 22
---
# 방법: 보안 모드 설정
[!INCLUDE[indigo1](../../../includes/indigo1-md.md)] 보안에는 대부분의 미리 정의된 바인딩에서 발견되는 전송, 메시지, "메시지 자격 증명을 사용한 전송"의 세 가지 일반 보안 모드가 있습니다. 두 개의 추가 모드는 두 바인딩에만 해당됩니다. 즉, "전송\-자격 증명만" 모드는 <xref:System.ServiceModel.BasicHttpBinding>에서 사용되고, "모두" 모드는 <xref:System.ServiceModel.NetMsmqBinding>에서 사용됩니다.그러나 이 항목에서는 세 가지 일반 보안 모드\(<xref:System.ServiceModel.SecurityMode>, <xref:System.ServiceModel.SecurityMode>, <xref:System.ServiceModel.SecurityMode>\)에 대해 중점적으로 설명합니다.  
  
 모든 미리 정의된 바인딩이 이러한 모드를 모두 지원하는 것은 아닙니다.이 항목에서는 <xref:System.ServiceModel.WSHttpBinding> 및 <xref:System.ServiceModel.NetTcpBinding> 클래스를 사용하여 모드를 설정하고 프로그래밍 방식과 구성을 통한 모드 설정 방법에 대해 설명합니다.  
  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 보안[!INCLUDE[crabout](../../../includes/crabout-md.md)], [보안 개요](../../../docs/framework/wcf/feature-details/security-overview.md), [서비스에 보안 설정](../../../docs/framework/wcf/securing-services.md) 및 [서비스 및 클라이언트에 보안 설정](../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)을 참조하십시오.전송 모드 및 메시지[!INCLUDE[crabout](../../../includes/crabout-md.md)], [전송 보안](../../../docs/framework/wcf/feature-details/transport-security.md) 및 [메시지 보안](../../../docs/framework/wcf/feature-details/message-security-in-wcf.md)을 참조하십시오.  
  
### 코드에서 보안 모드를 설정하려면  
  
1.  사용 중인 바인딩 클래스의 인스턴스를 만듭니다.미리 정의된 바인딩 목록은 [시스템 제공 바인딩](../../../docs/framework/wcf/system-provided-bindings.md)을 참조하십시오.이 예제에서는 <xref:System.ServiceModel.WSHttpBinding> 클래스의 인스턴스를 만듭니다.  
  
2.  `Security` 속성에서 반환하는 개체의 `Mode` 속성을 설정합니다.  
  
     [!code-csharp[c_SettingSecurityMode#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#1)]
     [!code-vb[c_SettingSecurityMode#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#1)]  
  
     또는 다음 코드에 표시된 것처럼 모드를 메시지로 설정합니다.  
  
     [!code-csharp[c_SettingSecurityMode#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#2)]
     [!code-vb[c_SettingSecurityMode#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#2)]  
  
     또는 다음 코드에 표시된 것처럼 모드를 메시지 자격 증명을 사용한 전송으로 설정합니다.  
  
     [!code-csharp[c_SettingSecurityMode#3](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#3)]
     [!code-vb[c_SettingSecurityMode#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#3)]  
  
3.  다음 코드에 표시된 것처럼 바인딩의 생성자에서 모드를 설정할 수도 있습니다.  
  
     [!code-csharp[c_SettingSecurityMode#4](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#4)]
     [!code-vb[c_SettingSecurityMode#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#4)]  
  
## ClientCredentialType 속성 설정  
 모드를 세 값 중 하나로 설정하면 `ClientCredentialType` 속성을 설정하는 방법이 결정됩니다.예를 들어, <xref:System.ServiceModel.WSHttpBinding> 클래스를 사용하여 모드를 `Transport`로 설정할 경우 <xref:System.ServiceModel.HttpTransportSecurity> 클래스의 <xref:System.ServiceModel.HttpTransportSecurity.ClientCredentialType%2A> 속성을 적절한 값으로 설정해야 합니다.  
  
#### 전송 모드에 대해 ClientCredentialType 속성을 설정하려면  
  
1.  바인딩의 인스턴스를 만듭니다.  
  
2.  `Mode` 속성을 `Transport`로 설정합니다.  
  
3.  `ClientCredential` 속성을 적절한 값으로 설정합니다.다음 코드에서는 속성을 `Windows`로 설정합니다.  
  
     [!code-csharp[c_SettingSecurityMode#5](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#5)]
     [!code-vb[c_SettingSecurityMode#5](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#5)]  
  
#### 메시지 모드에 대해 ClientCredentialType 속성을 설정하려면  
  
1.  바인딩의 인스턴스를 만듭니다.  
  
2.  `Mode` 속성을 `Message`로 설정합니다.  
  
3.  `ClientCredential` 속성을 적절한 값으로 설정합니다.다음 코드에서는 속성을 `Certificate`로 설정합니다.  
  
     [!code-csharp[c_SettingSecurityMode#6](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#6)]
     [!code-vb[c_SettingSecurityMode#6](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#6)]  
  
#### 구성에서 모드 및 ClientCredentialType 속성을 설정하려면  
  
1.  해당 바인딩 요소를 구성 파일의 [\<bindings\>](../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) 요소에 추가합니다.다음 예제에서는 [\<wsHttpBinding\>](../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) 요소를 추가합니다.  
  
2.  `<binding>` 요소를 추가하고 해당 `name` 특성을 적절한 값으로 설정합니다.  
  
3.  `<security>` 요소를 추가하고 `mode` 특성을 `Message`, `Transport` 또는 `TransportWithMessageCredential`로 설정합니다.  
  
4.  모드를 `Transport`로 설정한 경우 `<transport>` 요소를 추가하고 `clientCredential` 특성을 적절한 값으로 설정합니다.  
  
     다음 예제에서는 모드를 "`Transport"`로 설정한 다음 `<transport>` 요소의 `clientCredentialType` 특성을 "`Windows"`로 설정합니다.  
  
    ```  
    <wsHttpBinding>  
    <binding name="TransportSecurity">  
        <security mode="Transport" />  
           <transport clientCredentialType = "Windows" />  
        </security>  
    </binding>  
    </wsHttpBinding >  
    ```  
  
     또는 `security mode`를 "`Message"`로 설정한 다음 `<"message">` 요소를 설정합니다.이 예제에서는 `clientCredentialType`을 "`Certificate"`로 설정합니다.  
  
    ```  
    <wsHttpBinding>  
    <binding name="MessageSecurity">  
        <security mode="Message" />  
           <message clientCredentialType = "Certificate" />  
        </security>  
    </binding>  
    </wsHttpBinding >  
    ```  
  
     <xref:System.ServiceModel.BasicHttpSecurityMode> 값은 특별한 경우에 사용되며 이에 대해서는 아래에 설명되어 있습니다.  
  
### TransportWithMessageCredential 사용  
 보안 모드를 `TransportWithMessageCredential`로 설정하면 전송에서 전송 수준 보안을 제공하는 실제 메커니즘을 결정합니다.예를 들어, HTTP 프로토콜에서는 HTTP를 통한 SSL\(Secure Sockets Layer\)\(HTTPS\)을 사용합니다.따라서 전송 보안 개체\(예: <xref:System.ServiceModel.HttpTransportSecurity>\)의 `ClientCredentialType` 속성 설정은 무시됩니다.즉, 메시지 보안 개체\(`WSHttpBinding` 바인딩의 경우 <xref:System.ServiceModel.NonDualMessageSecurityOverHttp> 개체\)의 `ClientCredentialType`만 설정할 수 있습니다.  
  
 [!INCLUDE[crdefault](../../../includes/crdefault-md.md)] [방법: 전송 보안 및 메시지 자격 증명 사용](../../../docs/framework/wcf/feature-details/how-to-use-transport-security-and-message-credentials.md).  
  
## 참고 항목  
 [방법: SSL 인증서를 사용하여 포트 구성](../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md)   
 [방법: 전송 보안 및 메시지 자격 증명 사용](../../../docs/framework/wcf/feature-details/how-to-use-transport-security-and-message-credentials.md)   
 [전송 보안](../../../docs/framework/wcf/feature-details/transport-security.md)   
 [메시지 보안](../../../docs/framework/wcf/feature-details/message-security-in-wcf.md)   
 [보안 개요](../../../docs/framework/wcf/feature-details/security-overview.md)   
 [시스템 제공 바인딩](../../../docs/framework/wcf/system-provided-bindings.md)   
 [\<security\>](../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md)   
 [\<security\>](../../../docs/framework/configure-apps/file-schema/wcf/security-of-basichttpbinding.md)   
 [\<security\>](../../../docs/framework/configure-apps/file-schema/wcf/security-of-nettcpbinding.md)