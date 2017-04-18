---
title: "응용 프로그램 도메인 및 어셈블리를 사용한 프로그래밍 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-bcl"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "응용 프로그램 도메인, 프로그래밍"
  - "어셈블리[.NET Framework], 프로그래밍"
  - "응용 프로그램 프로그래밍 도메인"
  - "어셈블리 프로그래밍"
ms.assetid: 96d3b8e3-bef8-4da0-9a81-9841e23a94e9
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# 응용 프로그램 도메인 및 어셈블리를 사용한 프로그래밍
Microsoft Internet Explorer, ASP.NET 및 Windows 셸 등의 호스트는 공용 언어 런타임을 프로세스에 로드하고, 이 프로세스에서 [응용 프로그램 도메인](../../../docs/framework/app-domains/application-domains.md)을 만든 다음, .NET Framework  응용 프로그램을 실행할 때 응용 프로그램 도메인에서 사용자 코드를 로드하고 실행합니다.  대부분의 경우 이 작업은 런타임 호스트에서 수행하므로, 사용자는 응용 프로그램 도메인을 만들거나 이 도메인에 어셈블리를 로드할 필요가 없습니다.  
  
 하지만, 사용자가 공용 언어 런타임을 호스팅할 응용 프로그램을 만들거나, 프로그래밍 방식으로 언로드하려는 도구나 코드를 만들거나, 또는 즉시 언로드하고 다시 로드할 수 있는 플러그형 구성 요소를 만드는 경우, 이 사용자는 고유한 응용 프로그램 도메인을 만들게 됩니다.  비록 사용자가 런타임 호스트를 만들지는 않더라도, 이 단원에서는 응용 프로그램 도메인과 이 도메인에 로드되는 어셈블리를 사용하는 방법에 대한 중요한 정보를 제공합니다.  
  
## 단원 내용  
 [응용 프로그램 도메인 및 어셈블리 방법 항목](../../../docs/framework/app-domains/application-domains-and-assemblies-how-to-topics.md)  
 개념 설명서에 있는 방법 항목 중 응용 프로그램 도메인과 어셈블리를 사용한 프로그래밍에 관련된 모든 항목에 대한 링크를 제공합니다.  
  
 [응용 프로그램 도메인 사용](../../../docs/framework/app-domains/use.md)  
 응용 프로그램 도메인을 만들고 구성하고 사용하기 위한 예제를 제공합니다.  
  
 [어셈블리를 사용한 프로그래밍](../../../docs/framework/app-domains/programming-with-assemblies.md)  
 어셈블리의 특성을 만들고 서명하고 설정하는 방법에 대해 설명합니다.  
  
## 관련 단원  
 [동적 메서드 및 어셈블리 생성](../../../docs/framework/reflection-and-codedom/emitting-dynamic-methods-and-assemblies.md)  
 동적 어셈블리를 만드는 방법에 대해 설명합니다.  
  
 [공용 언어 런타임의 어셈블리](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)  
 어셈블리에 대해 개념적으로 설명합니다.  
  
 [응용 프로그램 도메인](../../../docs/framework/app-domains/application-domains.md)  
 응용 프로그램 도메인에 대해 개념적으로 설명합니다.  
  
 [리플렉션 개요](../../../docs/framework/reflection-and-codedom/reflection.md)  
 **Reflection** 클래스를 사용하여 어셈블리와 관련된 정보를 얻는 방법에 대해 설명합니다.