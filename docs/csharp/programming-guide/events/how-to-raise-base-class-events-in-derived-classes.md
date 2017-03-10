---
title: "방법: 파생 클래스에서 기본 클래스 이벤트 발생(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "이벤트[C#], 파생 클래스에서"
ms.assetid: 2d20556a-0aad-46fc-845e-f85d86ea617a
caps.latest.revision: 24
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 24
---
# 방법: 파생 클래스에서 기본 클래스 이벤트 발생(C# 프로그래밍 가이드)
다음의 간단한 예제에서는 기본 클래스의 이벤트를 선언할 때 해당 이벤트가 파생 클래스에서도 발생할 수 있도록 하는 일반적인 방법을 보여 줍니다.  이 패턴은 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)] 클래스 라이브러리의 Windows Forms 클래스에서 광범위하게 사용됩니다.  
  
 다른 클래스의 기본 클래스로 사용할 수 있는 클래스를 만드는 경우 이벤트는 이를 선언한 클래스 내에서만 호출할 수 있는 특별한 형식의 대리자라는 사실을 염두에 두어야 합니다.  파생 클래스는 기본 클래스 내에서 선언된 이벤트를 직접 호출할 수 없습니다.  일부 경우에는 기본 클래스에 의해서만 발생시킬 수 있는 이벤트가 필요하기도 하지만, 대부분의 경우에는 파생 클래스에서 기본 클래스 이벤트를 호출할 수 있도록 해야 합니다.  이렇게 하려면 기본 클래스에서 이벤트를 래핑하는 보호 호출 메서드를 만듭니다.  이 호출 메서드를 호출하거나 재정의하면 파생 클래스에서 이벤트를 간접적으로 호출할 수 있습니다.  
  
> [!NOTE]
>  기본 클래스에 가상 이벤트를 선언하고 파생 클래스에서 이를 재정의하지 마십시오.  C\#컴파일러핸들이 정확 하 게 수행 하며 파생 된이벤트에 대 한 구독자를기본 클래스이벤트에 실제로 가입 하는 것인지 예측할 수 없습니다.  
  
## 예제  
 [!code-cs[csProgGuideEvents#1](../../../csharp/programming-guide/events/codesnippet/csharp/how-to-raise-base-class-_1.cs)]  
  
## 참고 항목  
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [이벤트](../../../csharp/programming-guide/events/index.md)   
 [대리자](../../../csharp/programming-guide/delegates/index.md)   
 [액세스 한정자](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)   
 [Windows Forms에서 이벤트 처리기 만들기](../Topic/Creating%20Event%20Handlers%20in%20Windows%20Forms.md)