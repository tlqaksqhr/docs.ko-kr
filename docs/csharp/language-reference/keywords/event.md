---
title: "event(C# 참조)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- event
- remove
- event_CSharpKeyword
- add
dev_langs:
- CSharp
helpviewer_keywords:
- event keyword [C#]
ms.assetid: 7858fd85-153b-4259-85d0-6aa13c35f174
caps.latest.revision: 28
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 674e36625a68243afff75f6c5028309dc7aff02a
ms.contentlocale: ko-kr
ms.lasthandoff: 09/25/2017

---
# <a name="event-c-reference"></a>event(C# 참조)
`event` 키워드는 게시자 클래스에서 이벤트를 선언하는 데 사용됩니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 <xref:System.EventHandler>를 기본 대리자 형식으로 사용하는 이벤트를 선언하고 발생시키는 방법을 보여 줍니다. 제네릭 <xref:System.EventHandler%601> 대리자 형식을 사용하는 방법 및 이벤트를 구독하고 이벤트 처리기 메서드를 만드는 방법을 보여 주는 전체 코드 예제는 [방법: .NET Framework 지침을 따르는 이벤트 게시](../../../csharp/programming-guide/events/how-to-publish-events-that-conform-to-net-framework-guidelines.md)를 참조하세요.  
  
 [!code-cs[csrefKeywordsModifiers#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/event_1.cs)]  
  
 이벤트는 해당 이벤트가 선언되는 클래스(게시자 클래스) 또는 구조체 내에서만 호출할 수 있는 특수한 멀티캐스트 대리자입니다. 다른 클래스 또는 구조체에서 이벤트를 구독하는 경우 해당 이벤트 처리기 메서드는 게시자 클래스에서 이벤트를 발생시킬 때 호출됩니다. 자세한 내용 및 코드 예제는 [이벤트](../../../csharp/programming-guide/events/index.md) 및 [대리자](../../../csharp/programming-guide/delegates/index.md)를 참조하세요.  
  
 이벤트는 [public](../../../csharp/language-reference/keywords/public.md), [private](../../../csharp/language-reference/keywords/private.md), [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md) 또는 `protected internal`로 표시할 수 있습니다. 이러한 액세스 한정자는 클래스 사용자가 이벤트에 액세스하는 방법을 정의합니다. 자세한 내용은 [액세스 한정자](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)를 참조하세요.  
  
## <a name="keywords-and-events"></a>키워드 및 이벤트  
 이벤트에 적용되는 키워드는 다음과 같습니다.  
  
|키워드|설명|추가 정보|  
|-------------|-----------------|--------------------------|  
|[static](../../../csharp/language-reference/keywords/static.md)|클래스의 인스턴스가 없는 경우에도 언제든지 호출자가 이벤트를 사용할 수 있도록 설정합니다.|[정적 클래스 및 정적 클래스 멤버](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md)|  
|[virtual](../../../csharp/language-reference/keywords/virtual.md)|파생 클래스에서 [override](../../../csharp/language-reference/keywords/override.md) 키워드를 사용하여 이벤트 동작을 재정의할 수 있도록 합니다.|[상속](../../../csharp/programming-guide/classes-and-structs/inheritance.md)|  
|[sealed](../../../csharp/language-reference/keywords/sealed.md)|파생 클래스에 대해 더 이상 가상이 아니도록 지정합니다.||  
|[abstract](../../../csharp/language-reference/keywords/abstract.md)|컴파일러에서 `add` 및 `remove` 이벤트 접근자 블록을 생성하지 않으므로 파생 클래스는 자체 구현을 제공해야 합니다.||  
  
 이벤트는 [static](../../../csharp/language-reference/keywords/static.md) 키워드를 사용하여 정적 이벤트로 선언할 수 있습니다. 그러면 클래스의 인스턴스가 없는 경우에도 언제든지 호출자가 이벤트를 사용할 수 있습니다. 자세한 내용은 [정적 클래스 및 정적 클래스 멤버](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md)를 참조하세요.  
  
 이벤트는 [virtual](../../../csharp/language-reference/keywords/virtual.md) 키워드를 사용하여 가상 이벤트로 표시할 수 있습니다. 그러면 파생 클래스에서 [override](../../../csharp/language-reference/keywords/override.md) 키워드를 사용하여 이벤트 동작을 재정의할 수 있습니다. 자세한 내용은 [상속](../../../csharp/programming-guide/classes-and-structs/inheritance.md)을 참조하세요. 또한 가상 이벤트를 재정의하는 이벤트는 [sealed](../../../csharp/language-reference/keywords/sealed.md)일 수 있으며, 파생 클래스에 대해 더 이상 가상이 아니도록 지정합니다. 마지막으로 이벤트를 [abstract](../../../csharp/language-reference/keywords/abstract.md)로 선언할 수 있으며, 컴파일러에서 `add` 및 `remove` 이벤트 접근자 블록을 생성하지 않는다는 의미입니다. 따라서 파생 클래스는 자체 구현을 제공해야 합니다.  
  
## <a name="c-language-specification"></a>C# 언어 사양  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [C# 참조](../../../csharp/language-reference/index.md)   
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C# 키워드](../../../csharp/language-reference/keywords/index.md)   
 [add](../../../csharp/language-reference/keywords/add.md)   
 [remove](../../../csharp/language-reference/keywords/remove.md)   
 [한정자](../../../csharp/language-reference/keywords/modifiers.md)   
 [방법: 대리자 조합(멀티캐스트 대리자)](../../../csharp/programming-guide/delegates/how-to-combine-delegates-multicast-delegates.md)

