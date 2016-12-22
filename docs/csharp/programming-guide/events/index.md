---
title: "이벤트(C# 프로그래밍 가이드) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "클래스 [C#], 이벤트"
  - "C# 언어, 이벤트"
  - "이벤트[C#]"
ms.assetid: a8e51b22-d294-44fb-9539-0072f06c4cb3
caps.latest.revision: 43
caps.handback.revision: 43
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 이벤트(C# 프로그래밍 가이드)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

[클래스](../../../csharp/language-reference/keywords/class.md)나 개체에서는 특정 상황이 발생할 때 이벤트를 통해 다른 클래스나 개체에 이를 알려줄 수 있습니다. 이벤트를 보내거나 *발생시키는* 클래스를 *게시자*라고 하며 이벤트를 받거나 *처리하는* 클래스를 *구독자*라고 합니다.  
  
 일반적인 C\# Windows Forms 또는 웹 응용 프로그램, 단추 및 목록 상자 같은 컨트롤에 의해 발생하는 이벤트를 구독합니다. 컨트롤이 게시하는 이벤트를 찾아보고 처리할 이벤트를 선택하려면 [!INCLUDE[csprcs](../../../csharp/includes/csprcs_md.md)] IDE\(통합 개발 환경\)를 사용할 수 있습니다. IDE는 빈 이벤트 처리기 메서드 및 이벤트를 구독하기 위한 코드를 자동으로 추가합니다. 자세한 내용은 [방법: 이벤트 구독 및 구독 취소](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md)을 참조하세요.  
  
## 이벤트 개요  
 이벤트에는 다음과 같은 속성이 있습니다.  
  
-   게시자는 이벤트 발생 시기를 결정합니다. 구독자는 이벤트에 대한 응답으로 수행할 작업을 결정합니다.  
  
-   한 이벤트에는 여러 구독자가 있을 수 있습니다. 구독자는 여러 게시자의 여러 이벤트를 처리할 수 있습니다.  
  
-   구독자가 없는 이벤트는 발생하지 않습니다.  
  
-   이벤트는 일반적으로 그래픽 사용자 인터페이스에서 단추 클릭이나 메뉴 선택 같은 사용자 작업을 표시하는 데 사용됩니다.  
  
-   이벤트에 여러 구독자가 있는 경우 이벤트 처리기는 이벤트가 발생할 때 동기적으로 호출됩니다. 이벤트를 비동기적으로 호출하려면 [Calling Synchronous Methods Asynchronously](../Topic/Calling%20Synchronous%20Methods%20Asynchronously.md)를 참조하세요.  
  
-   [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] 클래스 라이브러리에서 이벤트는 <xref:System.EventHandler> 대리자 및 <xref:System.EventArgs> 기본 클래스를 기반으로 합니다.  
  
## 관련 단원  
 자세한 내용은 다음을 참조하세요.  
  
-   [방법: 이벤트 구독 및 구독 취소](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md)  
  
-   [방법: .NET Framework 지침을 따르는 이벤트 게시](../../../csharp/programming-guide/events/how-to-publish-events-that-conform-to-net-framework-guidelines.md)  
  
-   [방법: 파생 클래스에서 기본 클래스 이벤트 발생](../../../csharp/programming-guide/events/how-to-raise-base-class-events-in-derived-classes.md)  
  
-   [방법: 인터페이스 이벤트 구현](../../../csharp/programming-guide/events/how-to-implement-interface-events.md)  
  
-   [스레드 동기화](../Topic/Thread%20Synchronization%20\(C%23%20and%20Visual%20Basic\).md)  
  
-   [방법: 사전을 사용하여 이벤트 인스턴스 저장](../../../csharp/programming-guide/events/how-to-use-a-dictionary-to-store-event-instances.md)  
  
-   [방법: 사용자 지정 이벤트 접근자 구현](../../../csharp/programming-guide/events/how-to-implement-custom-event-accessors.md)  
  
## C\# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## 중요 설명서 장  
 [C\# 3.0 Cookbook, Third Edition: More than 250 solutions for C\# 3.0 programmers](http://go.microsoft.com/fwlink/?LinkId=195369)의 [Delegates, Events, and Lambda Expressions](http://go.microsoft.com/fwlink/?LinkId=195395)  
  
 [Delegates and Events](http://go.microsoft.com/fwlink/?LinkId=195418) in [Learning C\# 3.0: Master the fundamentals of C\# 3.0](http://go.microsoft.com/fwlink/?LinkId=195412)  
  
## 참고 항목  
 <xref:System.EventHandler>   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [대리자](../../../csharp/programming-guide/delegates/index.md)   
 [Windows Forms에서 이벤트 처리기 만들기](../Topic/Creating%20Event%20Handlers%20in%20Windows%20Forms.md)   
 [Multithreaded Programming with the Event\-based Asynchronous Pattern](../Topic/Multithreaded%20Programming%20with%20the%20Event-based%20Asynchronous%20Pattern.md)