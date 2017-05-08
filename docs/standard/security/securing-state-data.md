---
title: "상태 데이터 보안 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "코드 보안, 상태 데이터"
  - "보안 코딩, 상태 데이터"
  - "보안[.NET Framework], 상태 데이터"
  - "상태 데이터 보안"
ms.assetid: 12671309-2877-43fe-a3df-6863507e712d
caps.latest.revision: 9
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 7
---
# 상태 데이터 보안
중요한 데이터를 처리하거나 보안 관련 사항을 결정해야 하는 응용 프로그램에서는 데이터를 자체적으로 제어해야 하며 악성 코드가 데이터에 직접 액세스하지 못하게 해야 합니다.  데이터를 메모리에서 보호하는 최상의 방법은 데이터를 동일한 어셈블리로 제한된 범위 사용하여 private 또는 internal 변수로 선언하는 것입니다.  그러나 이 데이터도 다음과 같이 액세스할 수 있습니다.  
  
-   리플렉션 메커니즘을 사용하면 개체를 참조할 수 있는 매우 신뢰되는 코드가 전용 멤버를 얻고 설정할 수 있습니다.  
  
-   serialization을 사용하면 매우 신뢰되는 코드가 serialize된 형식의 개체에서 해당 데이터에 액세스할 수 있을 경우 효과적으로 전용 멤버를 얻고 설정할 수 있습니다.  
  
-   디버깅할 때 이 데이터를 읽을 수 있습니다.  
  
 따라서 메서드나 속성이 실수로 해당 값을 노출하지 않도록 해야 합니다.  
  
 일부 경우에는 데이터를 클래스와 해당 클래스의 파생 클래스에서만 액세스할 수 있는 "protected"로 선언할 수 있습니다.  그러나 추가 노출 때문에 다음과 같은 예방 조치를 추가로 수행해야 합니다.  
  
-   파생 범위를 동일한 어셈블리로 제한하거나, [메서드 액세스 보안](../../../docs/framework/misc/securing-method-access.md)에서 설명한 대로 선언적 보안을 통해 코드에 특정 ID 또는 권한이 있어야만 클래스에서 파생시킬 수 있도록 함으로써 클래스에서 파생시킬 수 있는 코드를 제어합니다.  
  
-   파생된 모든 클래스가 비슷한 보호를 구현하거나 봉인되도록 합니다.  
  
## 참고 항목  
 [보안 코딩 지침](../../../docs/standard/security/secure-coding-guidelines.md)