---
title: "방법: 신뢰할 수 있는 세션 내에서 메시지 보안 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: aee33e50-936f-4486-9ca8-c1520c19a62d
caps.latest.revision: 8
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 8
---
# 방법: 신뢰할 수 있는 세션 내에서 메시지 보안
이 항목에서는 기본적이지는 않지만 신뢰할 수 있는 세션을 지원하는 시스템 제공 바인딩 중 하나를 사용하여 이러한 세션 내에서 교환된 메시지의 메시지 수준 보안을 사용하도록 설정하는 데 필요한 단계에 대해 간략하게 설명합니다.코드를 사용하여 명령적으로 또는 구성 파일에서 선언적으로 안전하고 신뢰할 수 있는 세션을 사용할 수 있습니다.이 절차에서는 클라이언트와 서비스 구성 파일을 사용하여 안전하고 신뢰할 수 있는 세션을 사용할 수 있습니다.  
  
 이 절차는 다음 세 가지 주요 작업으로 구성됩니다.  
  
1.  클라이언트 및 서비스가 신뢰할 수 있는 세션 내에서 메시지를 교환하도록 지정합니다.  
  
2.  신뢰할 수 있는 세션 내에서 메시지 수준 보안이 필요합니다.  
  
3.  클라이언트가 서비스에서 인증받는 데 사용해야 하는 클라이언트 자격 증명 형식을 지정합니다.  
  
 첫 번째 작업에서는 끝점 구성 요소에 "MessageSecurity"라고 명명된 바인딩 구성\(이 예제의 경우\)을 참조하는 `bindingConfiguration` 특성을 포함하는 것이 중요합니다. [\<binding\>](../../../../docs/framework/misc/binding.md) 구성 요소는 [reliableSession](http://msdn.microsoft.com/ko-kr/9c93818a-7dfa-43d5-b3a1-1aafccf3a00b) 요소의 `enabled` 특성을 `true`로 설정하여 신뢰할 수 있는 세션을 사용하도록 이 이름을 참조할 수 있습니다.`ordered` 특성을 `true`로 설정하여 신뢰할 수 있는 세션 내에서 순서가 지정된 배달 보증을 사용하는 것이 필요할 수 있습니다.  
  
 이 구성 절차에 기반한 예제의 소스 복사에 대해서는 [WS 신뢰할 수 있는 세션](../../../../docs/framework/wcf/samples/ws-reliable-session.md)을 참조하십시오.  
  
 두 번째 작업의 주요 항목은 클라이언트 및 서비스의 \<`binding`\> 요소에 포함된 \<`security`\> 요소의 `mode` 특성을 `Message`로 설정하여 수행합니다.  
  
 세 번째 작업의 주요 항목은 클라이언트 및 서비스의 \<`security`\> 요소에 포함된 \<`message`\> 요소의 `clientCredentialType` 특성을 `Certificate`로 설정하여 수행합니다.  
  
> [!NOTE]
>  신뢰할 수 있는 세션에 메시지 보안을 사용할 때 클라이언트가 인증되지 않은 경우 신뢰할 수 있는 메시징은 첫 번째 오류 발생 시 예외를 throw하는 대신 시간 제한이 발생할 때까지 클라이언트를 인증하려고 시도합니다.  
  
### 신뢰할 수 있는 세션을 사용하도록 WSHttpBinding으로 서비스를 구성하려면  
  
1.  이 절차에 대해서는 [방법: 신뢰할 수 있는 세션 내에서 메시지 교환](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md)에서 설명합니다.  
  
### 신뢰할 수 있는 세션을 사용하도록 WSHttpBinding으로 클라이언트를 구성하려면  
  
1.  이 절차에 대해서는 [방법: 신뢰할 수 있는 세션 내에서 메시지 교환](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md)에서 설명합니다.  
  
### 구성에서 모드 및 ClientCredentialType을 설정하려면  
  
1.  해당 바인딩 요소를 구성 파일의 [\<bindings\>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) 요소에 추가합니다.다음 예제에서는 [\<wsHttpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) 요소를 추가합니다.  
  
2.  \<`binding`\> 요소를 추가하고 해당 `name` 특성을 적절한 값으로 설정합니다.  
  
3.  `<security>` 요소를 추가하고 `mode` 특성을 `Message`로 설정합니다.  
  
     다음 예제에서는 모드를 `Message`로 설정한 다음 \<`message`\> 요소의 `clientCredentialType` 특성을 "`Certificate`로 설정합니다.  
  
    ```  
    <wsHttpBinding>  
    <binding name="MessageSecurity">  
        <security mode="Message" />  
           <message clientCredentialType = " Certificate" />  
        </security>  
    </binding>  
    </wsHttpBinding >  
    ```