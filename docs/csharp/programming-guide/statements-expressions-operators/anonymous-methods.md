---
title: "무명 메서드(C# 프로그래밍 가이드) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
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
  - "무명 메서드[C#]"
  - "대리자[C#], 무명 메서드"
  - "메서드[C#], 무명"
ms.assetid: a62441fa-f0a3-4acb-9aa6-93762a635275
caps.latest.revision: 31
caps.handback.revision: 31
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 무명 메서드(C# 프로그래밍 가이드)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

2.0보다 이전 버전의 C\#에서는 [명명된 메서드](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md)를 사용하는 방법으로만 [대리자](../../../csharp/language-reference/keywords/delegate.md)를 선언할 수 있었습니다.  C\# 2.0에는 무명 메서드가 도입되었고 C\# 3.0 이상에서는 무명 메서드 대신 람다 식을 사용하여 인라인 코드를 작성하는 방법이 더 선호됩니다.  그러나 이 항목에서 설명하는 무명 메서드에 대한 내용은 람다 식에도 적용됩니다.  무명 메서드에는 람다 식에 없는 기능이 한 가지 있습니다.  무명 메서드를 사용하면 매개 변수 목록을 생략할 수 있으며,  이는 무명 메서드가 여러 시그니처를 가진 대리자로 변환될 수 있음을 의미합니다.  람다 식을 사용해서는 이렇게 할 수 없습니다.  람다 식에 대한 자세한 내용은 [람다 식](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)을 참조하십시오.  
  
 무명 메서드를 만드는 것은 본질적으로 코드 블록을 대리자 매개 변수로 전달하기 위한 방법입니다.  두 가지 예를 들겠습니다.  
  
 [!code-cs[csProgGuideDelegates#6](../../../csharp/programming-guide/delegates/codesnippet/CSharp/anonymous-methods_1.cs)]  
  
 [!code-cs[csProgGuideDelegates#5](../../../csharp/programming-guide/delegates/codesnippet/CSharp/anonymous-methods_2.cs)]  
  
 무명 메서드를 사용하면 별도의 메서드를 만들 필요가 없으므로 대리자를 인스턴스화하는 데 따르는 코딩 오버헤드를 줄일 수 있습니다.  
  
 예를 들어 메서드를 만드는 것이 불필요한 오버헤드가 되는 상황에서는 대리자 대신 코드 블록을 지정하는 것이 유용합니다.  새로운 스레드를 시작할 때가 좋은 예입니다.  다음 클래스는 스레드를 만들고 스레드에서 실행할 코드도 포함하므로 대리자를 위한 추가 메서드를 만들 필요가 없습니다.  
  
 [!code-cs[csProgGuideDelegates#7](../../../csharp/programming-guide/delegates/codesnippet/CSharp/anonymous-methods_3.cs)]  
  
## 설명  
 무명 메서드의 매개 변수 범위는 *무명 메서드 블록*입니다.  
  
 무명 메서드 블록 안에서 블록 밖을 대상으로 [goto](../../../csharp/language-reference/keywords/goto.md), [break](../../../csharp/language-reference/keywords/break.md) 또는 [continue](../../../csharp/language-reference/keywords/continue.md)와 같은 점프 문을 사용하면 오류가 발생합니다.  무명 메서드 블록 밖에서 블록 안을 대상으로 `goto`, `break` 또는 `continue`와 같은 점프 문을 사용해도 오류가 발생합니다.  
  
 지역 변수 및 매개 변수의 범위에 무명 메서드 선언이 포함되는 경우 이러한 변수를 무명 메서드의 *외부* 변수라고 합니다.  예를 들어, 다음 코드 단편에서 `n`은 외부 변수입니다.  
  
 [!code-cs[csProgGuideDelegates#8](../../../csharp/programming-guide/delegates/codesnippet/CSharp/anonymous-methods_4.cs)]  
  
 외부 변수에 `n` 라고  *캡처* 대리자를 만들 때.  무명 메서드를 참조 하는 대리자가 가비지 수집의 대상이 될 때까지 지역 변수와 달리 캡처된 변수의 수명은 확장 합니다.  
  
 무명 메서드에서는 외부 범위의 [ref](../../../csharp/language-reference/keywords/ref.md) 또는 [out](../../../csharp/language-reference/keywords/out.md) 매개 변수에 액세스할 수 없습니다.  
  
 *무명 메서드 블록*에서는 안전한 코드에만 액세스할 수 있습니다.  
  
 무명 메서드는 [is](../../../csharp/language-reference/keywords/is.md) 연산자의 왼쪽에 사용할 수 없습니다.  
  
## 예제  
 다음 예제에서는 대리자를 인스턴스화하는 두 가지 방법을 보여 줍니다.  
  
-   대리자를 무명 메서드에 연결  
  
-   대리자를 명명된 메서드\(`DoWork`\)에 연결  
  
 각각의 경우에서 대리자가 호출되면 메시지가 표시됩니다.  
  
 [!code-cs[csProgGuideDelegates#4](../../../csharp/programming-guide/delegates/codesnippet/CSharp/anonymous-methods_5.cs)]  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [대리자](../../../csharp/programming-guide/delegates/index.md)   
 [람다 식](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)   
 [안전하지 않은 코드 및 포인터](../../../csharp/programming-guide/unsafe-code-pointers/index.md)   
 [메서드](../../../fsharp/language-reference/members/methods.md)   
 [명명된 메서드와 익명 메서드의 대리자 비교](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md)