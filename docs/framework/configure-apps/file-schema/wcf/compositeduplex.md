---
title: "&lt;compositeDuplex&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
ms.assetid: 725004d1-ce88-4405-a220-78e89844f81f
caps.latest.revision: 14
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 14
---
# &lt;compositeDuplex&gt;
서비스에서 클라이언트에 메시지를 돌려 보낼 수 있도록 클라이언트가 서비스에 대한 끝점을 공개해야 할 때 사용되는 바인딩 요소를 정의합니다.  
  
## 구문  
  
```  
  
<compositeDuplex clientBaseAddress="URI" />  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|clientBaseAddress|이중 모드에서 백 채널의 주소를 설정하는 URI입니다.  서비스에서는 이 주소를 사용하여 접속한 후 클라이언트와의 연결을 설정합니다.<br /><br /> 이 특성이 설정되지 않으면 기본 주소 “`full qualified name+default port\TemporaryIndigoAddress\guid`”가 생성됩니다.  기본값은 `null`입니다.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<binding\>](../../../../../docs/framework/misc/binding.md)|사용자 지정 바인딩의 모든 바인딩 기능을 정의합니다.|  
  
## 설명  
 이 구성 요소는 HTTP와 같이 원래는 이중 통신을 허용하지 않는 전송에 사용됩니다.  그에 반해 TCP는 기본적으로 이중 통신을 허용하므로, 이 바인딩 요소를 사용하지 않더라도 서비스에서 클라이언트로 회신 메시지를 보낼 수 있습니다.  
  
 서비스에서 접속하여 연결을 설정하려면 클라이언트가 주소를 공개해야 합니다.  이 클라이언트 주소는 `clientBaseAddress` 특성을 사용하여 제공합니다.  WCF\(Windows Communication Foundation\)에서는 ClientBaseAddress를 사용자가 명시적으로 설정하지 않은 경우 자동으로 생성됩니다.  
  
## 예제  
  
```  
<compositeDuplex clientBaseAddress="http://www.contoso.com" />  
```  
  
## 참고 항목  
 <xref:System.ServiceModel.Configuration.CompositeDuplexElement>   
 <xref:System.ServiceModel.Channels.CompositeDuplexBindingElement>   
 <xref:System.ServiceModel.Channels.CustomBinding>   
 [바인딩](../../../../../docs/framework/wcf/bindings.md)   
 [바인딩 확장](../../../../../docs/framework/wcf/extending/extending-bindings.md)   
 [사용자 지정 바인딩](../../../../../docs/framework/wcf/extending/custom-bindings.md)   
 [\<customBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)