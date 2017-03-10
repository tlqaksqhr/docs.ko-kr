---
title: "virtual(C# 참조) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "virtual_CSharpKeyword"
  - "virtual"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "virtual 키워드[C#]"
ms.assetid: 5da9abae-bc1e-434f-8bea-3601b8dcb3b2
caps.latest.revision: 26
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 26
---
# virtual(C# 참조)
`virtual` 키워드는 메서드, 속성, 인덱서 또는 이벤트 선언을 한정하는 데 사용되며 파생 클래스에서 재정의될 수 있습니다.  예를 들어, 다음 메서드는 이 메서드를 상속하는 클래스에 의해 재정의될 수 있습니다.  
  
```  
public virtual double Area()   
{  
    return x * y;  
}  
```  
  
 가상 멤버의 구현은 파생 클래스의 [override 멤버](../../../csharp/language-reference/keywords/override.md)에 의해 변경될 수 있습니다.  `virtual` 키워드를 사용하는 방법에 대한 자세한 내용은 [Override 및 New 키워드를 사용하여 버전 관리](../../../csharp/programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) 및 [Override 및 New 키워드를 사용해야 하는 경우](../../../csharp/programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md)를 참조하십시오.  
  
## 설명  
 가상 메서드가 호출되면 재정의 함수에 대해 개체의 런타임 형식이 검사됩니다.  가장 많이 파생되는 클래스의 재정의 멤버가 호출되므로 멤버를 재정의한 파생 클래스가 없을 경우에는 원래 멤버가 호출될 수도 있습니다.  
  
 기본적으로 메서드는 비 가상 메서드이며  비 가상 메서드는 재정의할 수 없습니다.  
  
 `virtual` 한정자는 `static`, `abstract, private` 또는 `override` 한정자와 함께 사용할 수 없습니다.  다음 예제에서는 가상 속성을 보여 줍니다.  
  
 [!code-cs[csrefKeywordsModifiers#26](../../../csharp/language-reference/keywords/codesnippet/csharp/csrefKeywordsModifiers/csrefKeywordsModifiers.cs#26)]  
  
 가상 속성은 추상 메서드와 비슷하게 작동하지만 선언 및 호출 구문에 차이가 있습니다.  
  
-   정적 속성에는 `virtual` 한정자를 사용할 수 없습니다.  
  
-   상속된 가상 속성은 `override` 한정자를 사용하는 속성 선언을 포함하는 방법을 통해 파생 클래스에서 재정의될 수 있습니다.  
  
## 예제  
 이 예제에서 `Shape` 클래스에는 두 개의 좌표 `x` 및 `y`와 `Area()` 가상 메서드가 포함되어 있습니다.  또한 `Circle`, `Cylinder` 및 `Sphere` 등의 서로 다른 형상 클래스가 `Shape` 클래스를 상속하며 각 도형에 대한 표면적이 계산됩니다.  각 파생 클래스는 `Area()`에 대한 자체적인 재정의 구현을 포함합니다.  
  
 새 열 상속 된 클래스 `Circle`, `Sphere`, 및 `Cylinder` 모든 다음 선언에서와 같이 기본 클래스를 초기화 하는 생성자를 사용 합니다.  
  
```  
public Cylinder(double r, double h): base(r, h) {}  
```  
  
 다음 프로그램을 계산 하 고 적절 한 구현을 호출 하 여 각 그림에 대 한 적절 한 영역을 표시를 `Area()` 메서드와 연결 된 개체에 따라 방법을.  
  
 [!code-cs[csrefKeywordsModifiers#23](../../../csharp/language-reference/keywords/codesnippet/csharp/csrefKeywordsModifiers/csrefKeywordsModifiers.cs#23)]  
  
## C\# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [한정자](../../../csharp/language-reference/keywords/modifiers.md)   
 [C\# 키워드](../../../csharp/language-reference/keywords/index.md)   
 [다형성](../../../csharp/programming-guide/classes-and-structs/polymorphism.md)   
 [abstract](../../../csharp/language-reference/keywords/abstract.md)   
 [override](../../../csharp/language-reference/keywords/override.md)   
 [new](../../../csharp/language-reference/keywords/new.md)