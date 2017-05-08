---
title: "Windows 스토어 앱용 .NET을 위한 MEF 네임스페이스 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 7667770e-d163-4ad6-a303-085cf73db2f2
caps.latest.revision: 3
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 3
---
# Windows 스토어 앱용 .NET을 위한 MEF 네임스페이스
<xref:System.Composition?displayProperty=fullName> 및 자식 네임스페이스는 MEF\(Managed Extensibility Framework\)로 확장 가능한 [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] 응용 프로그램 개발을 위한 형식을 포함합니다.  이러한 네임스페이스는 [!INCLUDE[win8](../../../includes/win8-md.md)] 운영 체제에 대한 [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)] 하위 집합의 일부입니다.  
  
 이러한 네임스페이스는 .NET Framework로 분산된 핵심 클래스 라이브러리의 일부가 아닙니다.  이러한 네임스페이스를 설치하려면 [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)]에서 프로젝트를 열고 **프로젝트** 메뉴에서 **NuGet 패키지 관리**를 선택한 다음 Microsoft.Composition 패키지를 온라인으로 검색합니다.  
  
-   <xref:System.Composition?displayProperty=fullName>은 [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] 응용 프로그램용 코어 MEF를 구성하는 클래스를 제공합니다.  
  
-   <xref:System.Composition.Convention?displayProperty=fullName>는 전통적인 구성 모델의 MEF를 사용하여 지원하는 형식을 제공합니다.  
  
-   <xref:System.Composition.Hosting?displayProperty=fullName>는 호스트 응용 프로그램 개발자에게 유용한 MEF 형식을 제공합니다.  
  
-   <xref:System.Composition.Hosting.Core?displayProperty=fullName>는 컴퍼지션 엔진에서 내부적으로 사용하는 MEF 형식을 제공합니다.  
  
 [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)] 과 네임 스페이스의 형식 및 네임 스페이스가 포함하는 종류에 관한 자세한 내용은 Windows 개발자 센터의 [.NET for Windows Store apps overview](http://go.microsoft.com/fwlink/p/?LinkID=238312) 를 참조하십시오.  
  
## 참고 항목  
 [Windows 스토어 앱용 .NET 개요](http://go.microsoft.com/fwlink/p/?LinkID=238312)   
 [API를 지원하는 Windows 스토어 앱용 .NET](http://go.microsoft.com/fwlink/p/?LinkID=247912)   
 [MEF\(Managed Extensibility Framework\)](../../../docs/framework/mef/index.md)