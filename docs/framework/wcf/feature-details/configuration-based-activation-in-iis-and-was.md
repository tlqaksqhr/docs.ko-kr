---
title: "IIS 및 WAS에서 구성 기반 활성화 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6a927e1f-b905-4ee5-ad0f-78265da38238
caps.latest.revision: 13
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 13
---
# IIS 및 WAS에서 구성 기반 활성화
일반적으로 IIS\(인터넷 정보 서비스\)나 WAS\(Windows Process Activation Service\)에서 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 서비스를 호스팅할 때는 .svc 파일을 제공해야 합니다..svc 파일에는 서비스 이름과 선택적 사용자 지정 서비스 호스트 팩터리가 포함되어 있습니다.이 추가 파일을 사용하면 관리 효율성이 떨어지지만구성 기반 활성화 기능을 사용하면 .svc 파일이 필요 없기 때문에 이로 인한 관리 효율성 저하도 발생하지 않습니다.  
  
## 구성 기반 활성화  
 구성 기반 활성화는 이전에 .svc 파일에 있던 메타데이터를 가져와서 Web.config 파일에 저장합니다.\<`serviceHostingEnvironment`\> 요소에는 \<`serviceActivations`\> 요소가 있고,\<`serviceActivations`\> 요소에는 호스팅된 각 서비스마다 하나씩 \<`add`\> 요소가 하나 이상 있으며,\<`add`\> 요소에는 서비스의 상대 주소와 서비스 형식 또는 서비스 호스트 팩터리를 설정하는 데 사용할 수 있는 특성이 있습니다.다음 구성 예제 코드에서는 이 섹션을 사용하는 방법을 보여 줍니다.  
  
> [!NOTE]
>  각 \<`add`\> 요소는 서비스 또는 팩터리 특성을 지정해야 합니다.서비스 특성과 팩터리 특성을 모두 지정할 수 있습니다.  
  
```  
<serviceHostingEnvironment>  
  <serviceActivations>  
    <add relativeAddress="MyServiceAddress" service="Service" factory=”MyServiceHostFactory”/>  
  </serviceActivations>  
</serviceHostingEnvironment>  
```  
  
 Web.config 파일에 이 섹션이 있으면 응용 프로그램의 App\_Code 디렉터리에 서비스 소스 코드를 저장하거나 응용 프로그램의 Bin 디렉터리에 컴파일된 어셈블리를 저장할 수 있습니다.  
  
> [!NOTE]
>  -   구성 기반 활성화를 사용하는 경우 .svc 파일의 인라인 코드는 지원되지 않습니다.  
> -   `relativeAddress` 특성은 “\<sub\-directory\>\/service.svc” 또는 “~\/\<sub\-directory\/service.svc” 같은 상대 주소로 설정해야 합니다.  
> -   WCF와 연결된 알려진 확장명이 없는 상대 주소를 등록하면 구성 예외가 throw됩니다.  
> -   지정된 상대 주소는 가상 응용 프로그램의 루트를 기준으로 합니다.  
> -   구성의 계층적 모델로 인해 가상 응용 프로그램은 컴퓨터 또는 사이트 수준에서 등록된 상대 주소를 상속합니다.  
> -   구성 파일의 등록이 .svc, .xamlx, .xoml 또는 기타 파일의 설정보다 우선합니다.  
> -   IIS\/WAS에 보내진 URI의 ‘\\’\(백슬래시\)는 자동으로 ‘\/’\(슬래시\)로 변환됩니다.‘\\’가 포함된 상대 주소가 추가된 경우 IIS에 이 상대 주소를 사용하는 URI를 보내면 백슬래시가 슬래시로 변환되기 때문에 IIS가 이 URI를 상대 주소와 일치시킬 수 없습니다.따라서 IIS가 일치하는 항목을 찾을 수 없음을 나타내는 추적 정보를 보냅니다.  
  
## 참고 항목  
 <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection.ServiceActivations%2A>   
 [서비스 호스팅](../../../../docs/framework/wcf/hosting-services.md)   
 [워크플로 서비스 호스팅 개요](../../../../docs/framework/wcf/feature-details/hosting-workflow-services-overview.md)   
 [\<serviceHostingEnvironment\>](../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md)   
 [Windows Server AppFabric 호스팅 기능](http://go.microsoft.com/fwlink/?LinkId=201276)