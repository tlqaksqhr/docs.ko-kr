---
title: ".NET Framework의 네트워크 추적 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "네트워크 트래픽 캡처"
  - "디버깅[.NET Framework], 네트워크 추적"
  - "응용 프로그램 배포[.NET Framework], 네트워크 트래픽"
  - "인터넷, 네트워크 추적"
  - "메서드 호출"
  - "메서드, 네트워크 추적"
  - "네트워크 리소스"
  - "네트워크 추적"
  - "네트워크 추적, 네트워크 추적 정보"
  - "네트워크, 네트워크 추적"
  - "네트워킹"
  - "출력, 네트워크 추적"
  - "추적 사용 디버깅"
  - "추적[.NET Framework], 네트워크"
  - "트래픽 추적"
ms.assetid: e993b7c3-087f-45d8-9c02-9dded936d804
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# .NET Framework의 네트워크 추적
.NET Framework의 네트워크 추적은 메서드 호출에 대한 정보와 관리되는 응용 프로그램에서 생성된 네트워크 트래픽 정보에 대한 액세스를 제공합니다.  이 기능은 개발 도중 응용 프로그램을 디버깅하고 배포된 응용 프로그램을 분석할 때 유용합니다.  네트워크 추적에서 제공된 출력은 개발 단계 및 프로덕션 환경에서 여러 가지 사용 시나리오를 지원하도록 사용자 지정할 수 있습니다.  
  
 .NET Framework에서 네트워크 추적을 사용하려면 추적 출력의 대상을 선택하고 응용 프로그램 또는 컴퓨터 구성 파일에 네트워크 추적 구성 설정을 추가해야 합니다.  구성 파일과 구성 파일의 사용 방법에 대한 설명은 [구성 파일](../../../docs/framework/configure-apps/index.md)을 참조하십시오.  네트워크 추적을 사용하는 방법에 대한 자세한 내용은 [네트워크 추적 사용](../../../docs/framework/network-programming/enabling-network-tracing.md)을 참조하십시오.  구성 파일에 추가해야 하는 설정에 대한 자세한 내용은 [방법: 네트워크 추적 구성](../../../docs/framework/network-programming/how-to-configure-network-tracing.md)을 참조하십시오.  
  
 추적 기능이 사용될 때, **System.Net** 클래스에 의해 출력되는 추적 정보를 캡처할 수 있습니다.  추적 정보를 생성하는 네트워킹 클래스 멤버에는 해당 .NET Framework 클래스 라이브러리 설명서의 설명 섹션에 다음 내용이 포함되어 있습니다.  
  
> [!NOTE]
>  응용 프로그램에 네트워크 추적을 사용하도록 설정하면 이 멤버에서 추적 정보를 출력합니다.  자세한 내용은 네트워크 추적을 참조하십시오.  
  
## 참고 항목  
 [네트워크 추적 사용](../../../docs/framework/network-programming/enabling-network-tracing.md)   
 [방법: 네트워크 추적 구성](../../../docs/framework/network-programming/how-to-configure-network-tracing.md)   
 [네트워크 추적 해석](../../../docs/framework/network-programming/interpreting-network-tracing.md)   
 [Introduction to Instrumentation and Tracing](http://msdn.microsoft.com/ko-kr/e924e57c-33cf-4b0e-9e7f-a45d13e38f2c)