---
title: "방법: 사전을 사용하여 이벤트 인스턴스 저장(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "이벤트[C#], 사전에 인스턴스 저장"
ms.assetid: 9512c64d-5aaf-40cd-b941-ca2a592f0064
caps.latest.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 16
---
# 방법: 사전을 사용하여 이벤트 인스턴스 저장(C# 프로그래밍 가이드)
각 이벤트에 대해 필드를 할당하는 대신 사전을 사용하여 이벤트 인스턴스를 저장하는 방법으로 많은 이벤트를 노출할 때 `accessor-declarations`를 사용할 수 있습니다.  이 방법은 많은 이벤트를 사용할 수 있지만 대부분의 이벤트가 구현되지 않을 것으로 예상할 때만 유용합니다.  
  
## 예제  
 [!code-cs[csProgGuideEvents#9](../../../csharp/programming-guide/events/codesnippet/csharp/how-to-use-a-dictionary-_1.cs)]  
  
## 참고 항목  
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [이벤트](../../../csharp/programming-guide/events/index.md)   
 [대리자](../../../csharp/programming-guide/delegates/index.md)