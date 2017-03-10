---
title: "event(C# 참조) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "event"
  - "remove"
  - "event_CSharpKeyword"
  - "add"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "event 키워드[C#]"
ms.assetid: 7858fd85-153b-4259-85d0-6aa13c35f174
caps.latest.revision: 28
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 28
---
# event(C# 참조)
`event` 키워드는 게시자 클래스에서 이벤트를 선언하는 데 사용합니다.  
  
## 예제  
 다음 예제에서는 <xref:System.EventHandler>를 내부 대리자 형식으로 사용하는 이벤트를 선언하고 발생시키는 방법을 보여 줍니다.  제네릭 <xref:System.EventHandler%601> 대리자 형식을 사용하는 방법과 이벤트를 구독하고 이벤트 처리기 메서드를 만드는 방법도 보여 주는 전체 코드 예제는 [방법: .NET Framework 지침을 따르는 이벤트 게시](../../../csharp/programming-guide/events/how-to-publish-events-that-conform-to-net-framework-guidelines.md)를 참조하십시오.  
  
 [!code-cs[csrefKeywordsModifiers#7](../../../csharp/language-reference/keywords/codesnippet/csharp/csrefKeywordsModifiers/csrefKeywordsModifiers.cs#7)]  
  
 이벤트는 해당 이벤트가 선언된 클래스나 구조체\(게시자 클래스\)에서만 호출할 수 있는 특수한 종류의 멀티캐스트 대리자입니다.  다른 클래스나 구조체가 이벤트를 구독할 경우 해당 이벤트 처리기 메서드는 게시자 클래스에서 이벤트를 발생시킬 때 호출됩니다.  자세한 내용 및 코드 예제를 보려면 [이벤트](../../../csharp/programming-guide/events/index.md) 및 [대리자](../../../csharp/programming-guide/delegates/index.md)를 참조하십시오.  
  
 이벤트는 [public](../../../csharp/language-reference/keywords/public.md), [private](../../../csharp/language-reference/keywords/private.md), [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md) 또는 `protected` `internal`로 표시할 수 있습니다.  이러한 액세스 한정자는 클래스 사용자가 이벤트에 액세스하는 방식을 정의합니다.  자세한 내용은 [액세스 한정자](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)를 참조하십시오.  
  
## 키워드 및 이벤트  
 이벤트에는 다음 키워드를 적용할 수 있습니다.  
  
|키워드|설명|자세한 내용|  
|---------|--------|------------|  
|[static](../../../csharp/language-reference/keywords/static.md)|클래스의 인스턴스가 없어도 언제든지 호출자가 이벤트를 사용할 수 있습니다.|[정적 클래스 및 정적 클래스 멤버](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md)|  
|[virtual](../../../csharp/language-reference/keywords/virtual.md)|파생 클래스에서 [override](../../../csharp/language-reference/keywords/override.md) 키워드를 사용하여 이벤트 동작을 재정의할 수 있습니다.|[상속](../../../csharp/programming-guide/classes-and-structs/inheritance.md)|  
|[sealed](../../../csharp/language-reference/keywords/sealed.md)|파생 클래스에 대해 더 이상 virtual이 아님을 지정합니다.||  
|[abstract](../../../csharp/language-reference/keywords/abstract.md)|컴파일러에서는 `add` 및 `remove` 이벤트 접근자 블록을 생성하지 않으므로 파생 클래스에서 고유한 구현을 제공해야 합니다.||  
  
 [static](../../../csharp/language-reference/keywords/static.md) 키워드를 사용하면 이벤트를 정적 이벤트로 선언할 수 있습니다.  이렇게 하면 클래스의 인스턴스가 없어도 언제든지 호출자가 이벤트를 사용할 수 있습니다.  자세한 내용은 [정적 클래스 및 정적 클래스 멤버](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md)를 참조하십시오.  
  
 [virtual](../../../csharp/language-reference/keywords/virtual.md) 키워드를 사용하면 이벤트를 가상 이벤트로 표시할 수 있습니다.  이렇게 하면 파생 클래스에서 [override](../../../csharp/language-reference/keywords/override.md) 키워드를 사용하여 이벤트 동작을 재정의할 수 있습니다.  자세한 내용은 [상속](../../../csharp/programming-guide/classes-and-structs/inheritance.md)를 참조하십시오.  가상 이벤트를 재정의하는 이벤트는 [sealed](../../../csharp/language-reference/keywords/sealed.md) 이벤트가 될 수도 있습니다. 이렇게 하면 파생 클래스에 대해 이 이벤트가 가상 이벤트가 아닌 것으로 지정됩니다.  마지막으로, 이벤트를 [abstract](../../../csharp/language-reference/keywords/abstract.md)로 선언할 수 있습니다. 이렇게 하면 컴파일러에서 `add` 및 `remove` 이벤트 접근자 블록이 생성되지 않습니다.  따라서 파생 클래스에서 자체 구현을 제공해야 합니다.  
  
## C\# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C\# 키워드](../../../csharp/language-reference/keywords/index.md)   
 [add](../../../csharp/language-reference/keywords/add.md)   
 [remove](../../../csharp/language-reference/keywords/remove.md)   
 [한정자](../../../csharp/language-reference/keywords/modifiers.md)   
 [방법: 대리자 조합\(멀티캐스트 대리자\)](../../../csharp/programming-guide/delegates/how-to-combine-delegates-multicast-delegates.md)