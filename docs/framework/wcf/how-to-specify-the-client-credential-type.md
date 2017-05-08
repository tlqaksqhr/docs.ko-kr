---
title: "방법: 클라이언트 자격 증명 형식 지정 | Microsoft Docs"
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
  - "보안 자격 증명, SOAP 메시지에 추가"
  - "WCF, 보안"
ms.assetid: 10f51bee-5f92-4c1a-9126-fa5418535d8f
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# 방법: 클라이언트 자격 증명 형식 지정
전송 또는 메시지 보안 모드를 설정한 후에는 클라이언트 자격 증명 형식을 설정할 수 있습니다.이 속성은 인증을 위한 서비스에 제공해야 할 자격 증명 유형을 지정합니다.보안 모드 설정\(클라이언트 자격 증명 유형을 설정하기 전에 필요한 단계\)에 대한 [!INCLUDE[crabout](../../../includes/crabout-md.md)]는 [방법: 보안 모드 설정](../../../docs/framework/wcf/how-to-set-the-security-mode.md)을 참조하십시오.  
  
### 클라이언트 자격 증명 형식을 코드로 설정하려면  
  
1.  서비스에서 사용할 바인딩의 인스턴스를 만듭니다.이 예제에서는 <xref:System.ServiceModel.WSHttpBinding> 바인딩을 사용합니다.  
  
2.  <xref:System.ServiceModel.WSHttpSecurity.Mode%2A> 속성을 적절한 값으로 설정합니다.이 예제에서는 메시지 모드를 사용합니다.  
  
3.  <xref:System.ServiceModel.MessageSecurityOverHttp.ClientCredentialType%2A> 속성을 적절한 값으로 설정합니다.이 예제에서는 Windows 인증\(<xref:System.ServiceModel.MessageCredentialType>\)을 사용하도록 값을 설정합니다.  
  
     [!code-csharp[c_ProgrammingSecurity#14](../../../samples/snippets/csharp/VS_Snippets_CFX/c_programmingsecurity/cs/source.cs#14)]
     [!code-vb[c_ProgrammingSecurity#14](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_programmingsecurity/vb/source.vb#14)]  
  
### 클라이언트 자격 증명 형식을 구성에 설정하려면  
  
1.  구성 파일에 [\<system.serviceModel\>](../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) 요소를 추가합니다.  
  
2.  [\<bindings\>](../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) 요소를 자식 요소로 추가합니다.  
  
3.  적절한 바인딩을 추가합니다.이 예제에서는 [\<wsHttpBinding\>](../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) 요소를 사용합니다.  
  
4.  [\<binding\>](../../../docs/framework/misc/binding.md) 요소를 추가하고 `name` 특성을 적절한 값으로 설정합니다.이 예제에서는 "SecureBinding"을 이름으로 사용합니다.  
  
5.  `<security>` 바인딩을 추가합니다.`mode` 특성을 적절한 값으로 설정합니다.이 예제에서는 `"Message"`로 설정합니다.  
  
6.  보안 모드의 결정에 따라 `<message>` 또는 `<transport>` 요소를 추가합니다.`clientCredentialType` 특성을 적절한 값으로 설정합니다.이 예제에서는 `"Windows"`를 사용합니다.  
  
    ```  
    <system.serviceModel>  
      <bindings>  
        <wsHttpBinding>  
          <binding name="SecureBinding">  
            <security mode="Message">  
                 <message clientCredentialType="Windows" />  
             </security>  
          </binding>  
        </wsHttpBinding>  
      </bindings>  
    </system.serviceModel>  
    ```  
  
## 참고 항목  
 [서비스에 보안 설정](../../../docs/framework/wcf/securing-services.md)   
 [방법: 보안 모드 설정](../../../docs/framework/wcf/how-to-set-the-security-mode.md)