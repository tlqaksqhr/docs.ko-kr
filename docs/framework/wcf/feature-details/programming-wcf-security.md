---
title: "WCF 보안 프로그래밍"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- message security [WCF], programming overview
ms.assetid: 739ec222-4eda-4cc9-a470-67e64a7a3f10
caps.latest.revision: 
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload:
- dotnet
ms.openlocfilehash: 4b296d9bf9b52dfc8e782f6e324be1de8c76d349
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="programming-wcf-security"></a>WCF 보안 프로그래밍
이 항목에서는 보안 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 응용 프로그램을 만드는 데 사용되는 기본 프로그래밍 작업에 대해 설명합니다. 이 항목에서는 인증, 기밀성 및 무결성을 이라고 통칭 *전송 보안*합니다. 이 항목에서는 권한 부여 (리소스 또는 서비스에 대 한 액세스 제어);를 설명 하지 권한 부여에 대 한 자세한 내용은 참조 [권한 부여](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)합니다.  
  
> [!NOTE]
>  에 대 한 관계에서 특히 보안 개념에 대 한 중요 한 사항을 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], msdn에서 집합의 패턴 및 실습 자습서를 참조 하십시오. [시나리오, 패턴 및 구현 지침에 대 한 향상 된 기능 WSE (Web Services) 3.0](http://go.microsoft.com/fwlink/?LinkID=88250).  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 보안 프로그래밍은 보안 모드, 클라이언트 자격 증명 형식 및 자격 증명 값을 설정하는 세 가지 단계로 구성됩니다. 코드 또는 구성을 통해 이러한 단계를 수행할 수 있습니다.  
  
## <a name="setting-the-security-mode"></a>보안 모드 설정  
 다음에서는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 보안 모드로 프로그래밍하는 일반 단계에 대해 설명합니다.  
  
1.  응용 프로그램 요구 사항에 적합한 미리 정의된 바인딩 중 하나를 선택합니다. 바인딩 선택 목록, 참조 [시스템 제공 바인딩](../../../../docs/framework/wcf/system-provided-bindings.md)합니다. 기본적으로 거의 모든 바인딩에서 보안을 사용할 수 있습니다. 한 가지 예외는는 <xref:System.ServiceModel.BasicHttpBinding> 클래스 (구성을 사용 하 여 [ \<basicHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md)).  
  
     선택한 바인딩에 따라 전송이 결정됩니다. 예를 들어, <xref:System.ServiceModel.WSHttpBinding>에서는 HTTP를 전송으로 사용하고 <xref:System.ServiceModel.NetTcpBinding>에서는 TCP를 사용합니다.  
  
2.  바인딩에 대한 보안 모드 중 하나를 선택합니다. 선택한 바인딩에 따라 사용 가능한 모드 선택 사항이 결정됩니다. 예를 들어, <xref:System.ServiceModel.WSDualHttpBinding>에서는 전송 보안을 허용하지 않으므로, 전송 보안은 옵션이 아닙니다. 마찬가지로 <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>과 <xref:System.ServiceModel.NetNamedPipeBinding>에서는 모두 메시지 보안을 허용하지 않습니다.  
  
     다음과 같은 세 가지 선택 옵션이 있습니다.  
  
    1.  `Transport`  
  
         전송 보안은 선택한 바인딩에서 사용하는 메커니즘에 종속됩니다. 예를 들어, `WSHttpBinding`을 사용하는 경우 보안 메커니즘은 SSL(Secure Sockets Layer)(또한 HTTPS에 대한 메커니즘)입니다. 일반적으로 전송 보안의 주요 이점은 사용 중인 전송에 관계 없이 처리 능력이 우수하다는 점입니다. 그러나 두 가지 제한이 있습니다. 첫째, 전송 메커니즘이 사용자를 인증하는 데 사용되는 자격 증명 형식을 지정합니다. 이는 서비스가 다른 형식의 자격 증명을 요구하는 다른 서비스와 상호 작용해야 하는 경우에만 단점이 됩니다. 둘째는 메시지 수준에서 보안이 적용되지 않기 때문에 종단 간 방식 대신 hop-by-hop 방식으로 보안이 구현됩니다. 이 제한은 클라이언트와 서비스 사이의 메시지 경로에 매개자가 포함되어 있는 경우에만 문제가 됩니다. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]어떤 사용할 전송, 참조 [전송 선택](../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)합니다. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]전송 보안을 사용 하 여 참조 [전송 보안 개요](../../../../docs/framework/wcf/feature-details/transport-security-overview.md)합니다.  
  
    2.  `Message`  
  
         메시지 보안은 모든 메시지에 메시지를 보안된 상태로 유지하는 데 필요한 헤더와 데이터가 포함되어 있음을 의미합니다. 헤더의 구성이 다양하므로 여러 자격 증명을 포함할 수 있습니다. 이는 전송 메커니즘이 제공할 수 없는 특정 자격 증명 형식을 요구하는 다른 서비스와 상호 작용할 경우나 서비스마다 다른 자격 증명 형식을 요구하는 여러 서비스에서 메시지를 사용해야 하는 경우에 유용합니다.  
  
         [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][메시지 보안](../../../../docs/framework/wcf/feature-details/message-security-in-wcf.md)합니다.  
  
    3.  `TransportWithMessageCredential`  
  
         이 선택 옵션에서는 전송 계층을 사용하여 메시지 전송을 보안하지만, 모든 메시지에 다른 서비스에 필요한 풍부한 자격 증명이 포함되어 있습니다. 이 옵션은 전송 보안의 성능 이점과 메시지 보안의 풍부한 자격 증명 이점을 결합합니다. <xref:System.ServiceModel.BasicHttpBinding>, <xref:System.ServiceModel.WSFederationHttpBinding>, <xref:System.ServiceModel.NetPeerTcpBinding> 및 <xref:System.ServiceModel.WSHttpBinding> 바인딩에서 이 옵션을 사용할 수 있습니다.  
  
3.  HTTP(HTTPS)에 대해 전송 보안을 사용하려면 SSL 인증서를 사용하여 호스트를 구성하고 포트에서 SSL을 사용하도록 설정해야 합니다. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][HTTP 전송 보안](../../../../docs/framework/wcf/feature-details/http-transport-security.md)합니다.  
  
4.  <xref:System.ServiceModel.WSHttpBinding>을 사용하고 보안 세션을 설정할 필요가 없는 경우 <xref:System.ServiceModel.NonDualMessageSecurityOverHttp.EstablishSecurityContext%2A> 속성을 `false`로 설정합니다.  
  
     클라이언트와 서비스에서 대칭 키를 사용하여 채널을 만들 때(클라이언트와 서버가 대화 상자가 닫힐 때까지 대화 기간 동안 동일한 키를 사용), 보안 세션이 발생합니다.  
  
## <a name="setting-the-client-credential-type"></a>클라이언트 자격 증명 형식 설정  
 클라이언트 자격 증명 형식을 적절하게 선택합니다. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][자격 증명 유형을 선택 하면](../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)합니다. 다음과 같은 클라이언트 자격 증명 형식을 사용할 수 있습니다.  
  
-   `Windows`  
  
-   `Certificate`  
  
-   `Digest`  
  
-   `Basic`  
  
-   `UserName`  
  
-   `NTLM`  
  
-   `IssuedToken`  
  
 모드 설정 방법에 따라 자격 증명 형식을 설정해야 합니다. 다음 구성 예제에 표시된 것처럼 `wsHttpBinding`을 선택하고 모드를 "Message"로 설정한 경우 메시지 요소의 `clientCredentialType` 특성 값을 `None`, `Windows`, `UserName`, `Certificate`, `IssuedToken` 중 하나로 설정할 수 있습니다.  
  
```xml  
<system.serviceModel>  
<bindings>  
  <wsHttpBinding>  
    <binding name="myBinding">  
      <security mode="Message"/>  
      <message clientCredentialType="Windows"/>  
    </binding>  
</bindings>  
</system.serviceModel>  
```  
  
 코드  
  
 [!code-csharp[c_WsHttpService#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wshttpservice/cs/source.cs#1)]
 [!code-vb[c_WsHttpService#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wshttpservice/vb/source.vb#1)]  
  
## <a name="setting-service-credential-values"></a>서비스 자격 증명 값 설정  
 클라이언트 자격 증명 형식을 선택한 경우 사용할 서비스 및 클라이언트에 대한 실제 자격 증명을 설정해야 합니다. 서비스에서 자격 증명은 <xref:System.ServiceModel.Description.ServiceCredentials> 클래스를 사용하여 설정하고 <xref:System.ServiceModel.ServiceHostBase.Credentials%2A> 클래스의 <xref:System.ServiceModel.ServiceHostBase> 속성에 의해 반환됩니다. 사용 중인 바인딩은 서비스 자격 증명 형식, 선택한 보안 모드 및 클라이언트 자격 증명 형식을 함축합니다. 다음 코드에서는 서비스 자격 증명에 대한 인증서를 설정합니다.  
  
 [!code-csharp[c_tcpService#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_tcpservice/cs/source.cs#3)]
 [!code-vb[c_tcpService#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_tcpservice/vb/source.vb#3)]  
  
## <a name="setting-client-credential-values"></a>클라이언트 자격 증명 값 설정  
 클라이언트에서 클라이언트 자격 증명 값은 <xref:System.ServiceModel.Description.ClientCredentials> 클래스를 사용하여 설정하고 <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A> 클래스의 <xref:System.ServiceModel.ClientBase%601> 속성에 의해 반환됩니다. 다음 코드에서는 TCP 프로토콜을 사용하여 인증서를 클라이언트에 대한 자격 증명으로 설정합니다.  
  
 [!code-csharp[c_TcpClient#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_tcpclient/cs/source.cs#1)]
 [!code-vb[c_TcpClient#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_tcpclient/vb/source.vb#1)]  
  
## <a name="see-also"></a>참고 항목  
 [기본 WCF 프로그래밍](../../../../docs/framework/wcf/basic-wcf-programming.md)  
 [일반적인 보안 시나리오](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md)
