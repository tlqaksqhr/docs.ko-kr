---
title: "static(C# 참조) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "static"
  - "static_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "static 키워드[C#]"
ms.assetid: 5509e215-2183-4da3-bab4-6b7e607a4fdf
caps.latest.revision: 26
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 26
---
# static(C# 참조)
`static` 한정자는 특정 개체가 아니라 해당 형식 자체에 속하는 정적 멤버를 선언하는 데 사용됩니다.  `static` 한정자는 클래스, 필드, 메서드, 속성, 연산자, 이벤트 및 생성자와 함께 사용할 수 있지만 클래스 이외의 형식, 소멸자 또는 인덱서와는 함께 사용할 수 없습니다.  자세한 내용은 [정적 클래스 및 정적 클래스 멤버](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md)를 참조하십시오.  
  
## 예제  
 다음 클래스는 `static`으로 선언되며 `static` 메서드만 포함합니다.  
  
 [!code-cs[csrefKeywordsModifiers#18](../../../csharp/language-reference/keywords/codesnippet/CSharp/static_1.cs)]  
  
 상수 또는 형식 선언은 암시적으로 정적 멤버입니다.  
  
 정적 멤버는 인스턴스를 통해 참조할 수 없으며  대신 형식 이름을 통해 참조됩니다.  예를 들어, 다음 클래스를 확인해 보십시오.  
  
 [!code-cs[csrefKeywordsModifiers#19](../../../csharp/language-reference/keywords/codesnippet/CSharp/static_2.cs)]  
  
 정적 멤버 `x`를 참조하려면 동일한 범위에서 멤버에 액세스 가능하지 않은 경우 정규화된 이름 `MyBaseC.MyStruct.x`을 사용합니다.  
  
```c#  
Console.WriteLine(MyBaseC.MyStruct.x);  
```  
  
 클래스의 인스턴스에는 해당 클래스의 모든 인스턴스 필드에 대한 별도의 복사본이 포함되지만 각 정적 필드의 복사본은 한 개만 있습니다.  
  
 [this](../../../csharp/language-reference/keywords/this.md)를 사용하여 정적 멤버 또는 속성 접근자를 참조할 수 없습니다.  
  
 클래스에 `static` 키워드가 적용되면 해당 클래스의 모든 멤버가 정적 멤버여야 합니다.  
  
 클래스와 정적 클래스는 정적 생성자를 가질 수 있습니다.  정적 생성자는 프로그램이 시작된 후 클래스가 인스턴스되기 전에 호출됩니다.  
  
> [!NOTE]
>  `static` 키워드는 C\+\+에서보다 더 제한적으로 사용됩니다.  C\+\+ 키워드와 비교하려면 [정적](/visual-cpp/misc/static-cpp)을 참조하십시오.  
  
 정적 멤버를 설명하기 위해 회사의 직원을 나타내는 클래스가 있다고 가정합니다.  또한 이 클래스에 직원 수를 계산하는 메서드와 직원 수를 저장하기 위한 필드가 포함되어 있다고 가정합니다.  이 메서드와 필드는 모두 어떤 인스턴스 직원에도 속해 있지 않으며  대신 회사 클래스에 속해 있습니다.  따라서 이 메서드 및 필드는 해당 클래스의 정적 멤버로 선언되어야 합니다.  
  
## 예제  
 이 예제에서는 새 직원의 이름 및 ID를 읽고 직원 카운터를 1씩 증가시키고 새로운 직원 수와 새 직원에 대한 정보를 표시합니다.  간단하게 설명하기 위해 이 프로그램은 키보드를 통해 직원의 현재 수를 읽어 들입니다.  실제 응용 프로그램에서는 이 정보를 파일에서 읽어 들입니다.  
  
 [!code-cs[csrefKeywordsModifiers#20](../../../csharp/language-reference/keywords/codesnippet/CSharp/static_3.cs)]  
  
## 예제  
 이 예제에서는 아직 선언되지 않은 다른 정적 필드를 사용하여 정적 필드를 초기화할 수 있지만 그 결과는 정적 필드에 명시적으로 값을 할당하기 전까지 정의되지 않은 상태임을 보여 줍니다.  
  
 [!code-cs[csrefKeywordsModifiers#21](../../../csharp/language-reference/keywords/codesnippet/CSharp/static_4.cs)]  
  
## C\# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C\# 키워드](../../../csharp/language-reference/keywords/index.md)   
 [한정자](../../../csharp/language-reference/keywords/modifiers.md)   
 [정적 클래스 및 정적 클래스 멤버](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md)