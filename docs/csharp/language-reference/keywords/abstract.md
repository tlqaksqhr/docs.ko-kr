---
title: "abstract(C# 참조) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "abstract"
  - "abstract_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "abstract 키워드[C#]"
ms.assetid: b0797770-c1f3-4b4d-9441-b9122602a6bb
caps.latest.revision: 24
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 24
---
# abstract(C# 참조)
`abstract` 한정자는 수정하는 항목에서 구현이 없거나 불완전하다는 것을 나타냅니다.  abstract 한정자는 클래스, 메서드, 속성, 인덱서 및 이벤트에 사용할 수 있습니다.  클래스 선언에 `abstract` 한정자를 사용하면 해당 클래스가 다른 클래스의 기본 클래스로만 사용됨을 나타냅니다.  abstract로 표시된 멤버나 abstract 클래스에 포함된 멤버는 해당 abstract 클래스에서 파생되는 클래스에 의해 구현되어야 합니다.  
  
## 예제  
 이 예제에서 `Square` 클래스는 `ShapesClass`에서 파생되므로 `Area`의 구현을 제공해야 합니다.  
  
 [!code-cs[csrefKeywordsModifiers#1](../../../csharp/language-reference/keywords/codesnippet/csharp/csrefKeywordsModifiers/csrefKeywordsModifiers.cs#1)]  
  
 추상 클래스에는 다음과 같은 특징이 있습니다.  
  
-   추상 클래스는 인스턴스화할 수 없습니다.  
  
-   추상 클래스에는 추상 메서드 및 접근자가 포함될 수 있습니다.  
  
-   두 개의 한정자가 반대되는 의미를 가지므로 추상 클래스는 [sealed](../../../csharp/language-reference/keywords/sealed.md) 한정자로 수정할 수 없습니다.  `sealed` 한정자는 클래스가 상속하지 않도록 하며 `abstract` 한정자에는 상속할 클래스가 필요합니다.  
  
-   추상 클래스에서 파생된 비 추상 클래스에는 상속된 모든 추상 메서드 및 접근자의 실제 구현이 포함되어야 합니다.  
  
 메서드 또는 속성 선언에 `abstract` 한정자를 사용하면 해당 메서드 또는 속성에 구현이 포함되지 않음을 나타냅니다.  
  
 추상 메서드에는 다음과 같은 특징이 있습니다.  
  
-   추상 메서드는 암시적으로 가상 메서드입니다.  
  
-   추상 메서드 선언은 추상 클래스에서만 허용됩니다.  
  
-   추상 메서드 선언에서는 실제 구현을 제공하지 않기 때문에 메서드 본문이 없습니다. 메서드 선언은 단순히 세미콜론으로 끝나며 시그니처 뒤에 중괄호\({ }\)가 없습니다.  예를 들면 다음과 같습니다.  
  
    ```  
    public abstract void MyMethod();  
    ```  
  
     구현은 비추상 클래스의 멤버인 재정의 메서드 [override](../../../csharp/language-reference/keywords/override.md)에 의해 제공됩니다.  
  
-   추상 메서드 선언에 [static](../../../csharp/language-reference/keywords/static.md) 또는 [virtual](../../../csharp/language-reference/keywords/virtual.md)한정자를 사용하면 오류가 발생합니다.  
  
 추상 속성은 추상 메서드와 비슷하게 작동하지만 선언 및 호출 구문에 차이가 있습니다.  
  
-   정적 속성에는 `abstract` 한정자를 사용할 수 없습니다.  
  
-   상속된 추상 속성은 [override](../../../csharp/language-reference/keywords/override.md) 한정자를 사용하는 속성 선언을 포함하는 방법을 통해 파생 클래스에서 재정의될 수 있습니다.  
  
 추상 클래스에 대한 자세한 내용은 [추상 및 봉인 클래스와 클래스 멤버](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md)를 참조하십시오.  
  
 추상 클래스는 모든 인터페이스 멤버에 대한 구현을 제공해야 합니다.  
  
 인터페이스를 구현하는 추상 클래스는 인터페이스 메서드를 추상 메서드에 매핑할 수도 있습니다.  예를 들면 다음과 같습니다.  
  
 [!code-cs[csrefKeywordsModifiers#2](../../../csharp/language-reference/keywords/codesnippet/csharp/csrefKeywordsModifiers/csrefKeywordsModifiers.cs#2)]  
  
## 예제  
 다음 예제에서 `DerivedClass` 클래스는 추상 클래스 `BaseClass`에서 파생되었습니다.  이 추상 클래스에는 추상 메서드 `AbstractMethod`와 두 개의 추상 속성 `X` 및 `Y`가 포함되어 있습니다.  
  
 [!code-cs[csrefKeywordsModifiers#3](../../../csharp/language-reference/keywords/codesnippet/csharp/csrefKeywordsModifiers/csrefKeywordsModifiers.cs#3)]  
  
 앞의 예제에서 다음과 같은 문으로 추상 클래스를 인스턴스화하려고 하면  
  
```  
BaseClass bc = new BaseClass();   // Error  
```  
  
 컴파일러에서 추상 클래스 'BaseClass'의 인스턴스를 만들 수 없다는 오류가 발생합니다.  
  
## C\# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [한정자](../../../csharp/language-reference/keywords/modifiers.md)   
 [virtual](../../../csharp/language-reference/keywords/virtual.md)   
 [override](../../../csharp/language-reference/keywords/override.md)   
 [C\# 키워드](../../../csharp/language-reference/keywords/index.md)