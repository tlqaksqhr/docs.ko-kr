---
title: "정규식의 스레드로부터의 안전성 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - ".NET Framework 정규식, 스레드"
  - "정규식으로 텍스트 구문 분석, 스레드"
  - "정규식과 패턴 일치, 스레드"
  - "정규식, 스레드"
  - "정규식으로 검색, 스레드"
ms.assetid: 7c4a167b-5236-4cde-a2ca-58646230730f
caps.latest.revision: 7
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 7
---
# 정규식의 스레드로부터의 안전성
<xref:System.Text.RegularExpressions.Regex> 클래스 자체는 스레드로부터 안전하며 읽기 전용이므로 변경할 수 없습니다.  즉, **Regex** 개체는 모든 스레드에 만들어질 수 있고 또한 스레드 간에 공유될 수 있으며 일치 메서드는 전역 상태에 전혀 영향을 주지 않으면서 모든 스레드에 대해 호출될 수 있습니다.  
  
 그러나 **Regex**에서 반환하는 **Match** 및 **MatchCollection**과 같은 결과 개체는 단일 스레드에서만 사용해야 합니다.  이들 개체의 대부분은 논리적으로는 변경할 수 없습니다. 하지만 성능 향상을 위해 일부 결과의 계산이 지연되는 경우가 있으므로, 호출자는 이들 개체에 대한 액세스를 serialize해야 합니다.  
  
 동기화된 메서드를 호출하면 **Regex** 결과 개체를 스레드로부터 안전하게 보호되는 인스턴스로 변환되어 이들 개체를 여러 스레드에서 공유할 수 있습니다.  열거자를 제외한 모든 정규식 클래스는 스레드로부터 안전하거나 동기화된 메서드를 통해 스레드로부터 안전한 개체로 변환될 수 있습니다.  
  
 여기서 열거자만 예외가 되는데,  응용 프로그램은 열거자에 대한 호출을 serialize해야 합니다.  둘 이상의 스레드에서 동시에 컬렉션을 열거하려면 열거자가 통과한 컬렉션의 루트 개체에 열거자 메서드를 동기화해야 합니다.  
  
## 참고 항목  
 [.NET Framework 정규식](../../../docs/standard/base-types/regular-expressions.md)