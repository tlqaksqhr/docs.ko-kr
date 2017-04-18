---
title: "&lt;protocolMapping&gt;의 &lt;add&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 08e62249-1641-41d1-91b1-66d7b46244e4
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# &lt;protocolMapping&gt;의 &lt;add&gt;
전송 프로토콜 체계\(예: http, net.tcp, net.pipe 등\) 및 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 바인딩 간의 기본 프로토콜 매핑을 나타냅니다.  런타임에 기본 끝점을 만들 때 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]에서는 구성된 매핑을 확인하여 특정 기본 주소에 사용할 바인딩을 결정합니다.  
  
## 구문  
  
```vb  
  
<protocolMapping>  
    <add binding="String”  
         bindingConfiguration="String”  
         scheme="http/net.msmq/net.pipe/net.tcp"/>  
</protocolMapping>  
  
```  
  
```csharp  
  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|요소|설명|  
|--------|--------|  
|바인딩|기본 끝점을 만드는 중에 끝점으로 사용할 바인딩 형식을 지정하는 문자열입니다.|  
|bindingConfiguration|참조할 바인딩 구성 섹션의 이름을 지정하는 문자열입니다.|  
|scheme|기본 끝점으로 사용될 전송 프로토콜 체계입니다.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<protocolMapping\>](../../../../../docs/framework/configure-apps/file-schema/wcf/protocolmapping.md)|전송 프로토콜 체계\(예: http, net.tcp, net.pipe 등\) 및 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 바인딩 간의 기본 프로토콜 매핑을 정의하기 위한 구성 섹션을 나타냅니다.|  
  
## 예제  
 다음 구성 예제는 machine.config 파일의 기본 프로토콜 매핑을 보여 줍니다.  machine.config 파일을 수정하여 컴퓨터 수준에서 기본 매핑을 재정의할 수 있습니다.  또는 응용 프로그램 범위 내에서 기본 매핑을 재정의하려는 경우 해당 응용 프로그램 구성 파일 내에서 이 섹션을 재정의하고 개별 프로토콜 체계에 대한 매핑을 변경할 수 있습니다.  
  
```  
  
<protocolMapping>  
        <add scheme="http" binding="basicHttpBinding"/>  
        <add scheme="net.tcp" binding="netTcpBinding"/>  
        <add scheme="net.pipe" binding="netNamedPipeBinding"/>  
        <add scheme="net.msmq" binding="netMsmqBinding"/>  
</protocolMapping>  
  
```  
  
## 참고 항목  
 [System.ServiceModel.Configuration.ProtocolMappingSection](assetId:///System.ServiceModel.Configuration.ProtocolMappingSection?qualifyHint=False&amp;autoUpgrade=True)   
 [System.ServiceModel.Configuration.ProtocolMappingElement](assetId:///System.ServiceModel.Configuration.ProtocolMappingElement?qualifyHint=False&amp;autoUpgrade=True)