---
title: "readonly(C# 참조) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "readonly_CSharpKeyword"
  - "readonly"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "readonly 키워드[C#]"
ms.assetid: 2f8081f6-0de2-4903-898d-99696c48d2f4
caps.latest.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 16
---
# readonly(C# 참조)
`readonly` 키워드는 필드에 사용할 수 있는 한정자입니다.  필드 선언에 `readonly` 한정자가 포함되어 있으면 선언의 일부로 대입하거나 동일한 클래스의 생성자에서 대입하는 경우에만 선언을 통해 정의한 필드에 값을 대입할 수 있습니다.  
  
## 예제  
 이 예제에서 `year` 필드는 클래스 생성자에서 값이 할당된 경우라도 `ChangeYear` 메서드로 값을 변경할 수 없습니다.  
  
 [!code-cs[csrefKeywordsModifiers#14](../../../csharp/language-reference/keywords/codesnippet/CSharp/readonly_1.cs)]  
  
 다음 경우에만 `readonly` 필드에 값을 대입할 수 있습니다.  
  
-   다음과 같이 변수가 선언에서 초기화된 경우 값을 대입할 수 있습니다.  
  
    ```  
    public readonly int y = 5;  
    ```  
  
-   인스턴스 필드의 경우 필드 선언이 포함된 클래스의 인스턴스 생성자에서 값을 대입할 수 있으며, 정적 필드의 경우에는 필드 선언이 포함된 클래스의 정적 생성자에서 값을 대입할 수 있습니다.  위의 두 경우는 `readonly` 필드를 [out](../../../csharp/language-reference/keywords/out.md) 또는 [ref](../../../csharp/language-reference/keywords/ref.md) 매개 변수로 전달할 수 있는 유일한 경우이기도 합니다.  
  
> [!NOTE]
>  `readonly` 키워드는 [const](../../../csharp/language-reference/keywords/const.md) 키워드와 다릅니다.  `const` 필드는 필드를 선언할 때만 초기화될 수 있습니다.  `readonly` 필드는 필드를 선언할 때 또는 생성자에서 초기화될 수 있습니다.  따라서 `readonly` 필드의 값은 사용된 생성자에 따라 다릅니다.  또한 `const` 필드는 컴파일 타임 상수인 반면 `readonly` 필드는 다음 예제에서와 같이 런타임 상수로도 사용할 수 있습니다.  
  
```  
public static readonly uint timeStamp = (uint)DateTime.Now.Ticks;  
```  
  
## 예제  
 [!code-cs[csrefKeywordsModifiers#15](../../../csharp/language-reference/keywords/codesnippet/CSharp/readonly_2.cs)]  
  
 앞의 예제에서 다음과 같은 문을 사용하면  
  
 `p2.y = 66;        // Error`  
  
 다음과 같은 컴파일러 오류 메시지가 발생합니다.  
  
 `The left-hand side of an assignment must be an l-value`  
  
 이 오류는 상수에 값을 대입할 때 발생하는 오류와 동일합니다.  
  
## C\# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C\# 키워드](../../../csharp/language-reference/keywords/index.md)   
 [한정자](../../../csharp/language-reference/keywords/modifiers.md)   
 [const](../../../csharp/language-reference/keywords/const.md)   
 [필드](../../../csharp/programming-guide/classes-and-structs/fields.md)