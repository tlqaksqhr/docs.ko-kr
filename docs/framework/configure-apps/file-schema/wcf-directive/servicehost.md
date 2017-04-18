---
title: "@ServiceHost | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 96ba6967-00f2-422f-9aa7-15de4d33ebf3
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# @ServiceHost
서비스 호스트를 생성하는 데 사용되는 팩토리를 호스트할 서비스 및 .svc 파일에 제공된 호스팅 코드에 액세스하거나 이를 컴파일하는 데 필요한 다른 프로그래밍 요소에 연결합니다.  
  
## 구문  
  
```  
  
<% @ServiceHost   
Service = "Service, ServiceNamespace"   
Factory = "Factory, FactoryNamespace"  
Debug = "Debug"  
Language = "Language"   
CodeBehind = "CodeBehind"%>  
```  
  
## 특성  
  
#### 서비스  
 호스트되는 서비스의 CLR 형식 이름입니다.  이 이름은 하나 이상의 서비스 계약을 구현하는 형식의 정규화된 이름이어야 합니다.  
  
#### Factory  
 서비스 호스트를 인스턴스화하는 데 사용되는 서비스 호스트 팩터리의 CLR 형식 이름입니다.  이 특성은 선택적 요소입니다.  지정되지 않은 경우 <xref:System.ServiceModel.ServiceHost>의 인스턴스를 반환하는 <xref:System.ServiceModel.Activation.ServiceHostFactory> 기본값이 사용됩니다.  
  
#### 디버그  
 디버그 기호를 사용하여 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 서비스를 컴파일해야 할지 여부를 나타냅니다.  디버그 기호를 사용하여 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 서비스를 컴파일해야 하면 `true`이고, 그렇지 않으면 `false`입니다.  
  
#### 언어  
 파일\(.svc\) 내의 인라인 코드를 모두 컴파일할 때 사용되는 언어를 지정합니다.  C\#, Visual Basic .NET 및 JScript .NET을 각각 나타내는 C\#, VB 및 JS를 비롯한 모든 .NET 지원 언어를 값으로 나타낼 수 있습니다.  이 특성은 선택적 요소입니다.  
  
#### CodeBehind  
 XML Web services를 구현하는 클래스가 동일한 파일에 있지 않고, 어셈블리로 컴파일되어 있지 않으며, \\Bin 디렉터리에 저장된 경우 XML Web services를 구현하는 소스 파일을 지정합니다.  
  
## 설명  
 서비스를 호스트하는 데 사용되는 <xref:System.ServiceModel.ServiceHost>는 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 프로그래밍 모델 내의 확장 지점입니다.  팩터리 패턴은 호스팅 환경에서 직접 인스턴스화하면 안 되는 다형 형식이므로 <xref:System.ServiceModel.ServiceHost>를 인스턴스화하는 데 사용됩니다.  
  
 기본 구현에서는 <xref:System.ServiceModel.Activation.ServiceHostFactory>를 사용하여 <xref:System.ServiceModel.ServiceHost>의 인스턴스를 만듭니다.  그러나 [@ServiceHost](../../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) 지시문에 팩터리 구현의 CLR 형식 이름을 지정하여 파생 호스트를 반환하는 팩터리를 직접 입력할 수 있습니다.  
  
 기본 팩터리 대신 사용자 지정 서비스 호스트 팩터리를 사용하려면 다음과 같이 [@ServiceHost](../../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) 지시문에 형식 이름을 입력합니다.  
  
```  
<% @ServiceHost Factory=”DerivedFactory” Service=”MyService” %>  
```  
  
 팩터리 구현을 가능하면 간단하게 유지합니다.  사용자 지정 논리가 많은 경우 팩터리 내부 대신 호스트 내부에 해당 로직을 배치하면 코드를 재사용할 수 있습니다.  
  
 예를 들어, `MyService`에 AJAX 사용 끝점을 사용하려면 다음 예제에서처럼 [@ServiceHost](../../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) 지시문에 `Factory` 특성 값으로 기본 <xref:System.ServiceModel.Activation.ServiceHostFactory> 대신 <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>를 지정합니다.  
  
## 예제  
  
```  
<% @ServiceHost   
Service="MyService"  
Language="C#"  
Debug="true"  
Factory="WebScriptServiceHostFactory"  
%>  
```  
  
## 참고 항목  
 [사용자 지정 서비스 호스트](../../../../../docs/framework/wcf/samples/custom-service-host.md)