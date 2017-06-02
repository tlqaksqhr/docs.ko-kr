---
title: "abstract(C# 참조) | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- abstract
- abstract_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- abstract keyword [C#]
ms.assetid: b0797770-c1f3-4b4d-9441-b9122602a6bb
caps.latest.revision: 24
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
ms.translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: acb9c5748addd75f741e97688fca707910b042a0
ms.contentlocale: ko-kr
ms.lasthandoff: 03/13/2017

---
# <a name="abstract-c-reference"></a>abstract(C# 참조)
`abstract` 한정자는 수정되는 항목에 누락되거나 불완전한 구현이 있음을 나타냅니다. abstract 한정자는 클래스, 메서드, 속성, 인덱서 및 이벤트와 함께 사용될 수 있습니다. 클래스 선언에서 `abstract` 한정자를 사용하여 클래스가 다른 클래스의 기본 클래스로만 사용됨을 나타냅니다. abstract로 표시되거나 추상 클래스에 포함된 멤버는 추상 클래스에서 파생 클래스에 의해 구현되어야 합니다.  
  
## <a name="example"></a>예제  
 이 예제에서 `Square` 클래스는 `ShapesClass`에서 파생되므로 `Area` 구현을 제공해야 합니다.  
  
 [!code-cs[csrefKeywordsModifiers#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/abstract_1.cs)]  
  
 다음 기능이 있는 추상 클래스:  
  
-   추상 클래스는 인스턴스화할 수 없습니다.  
  
-   추상 클래스에 추상 메서드 및 접근자가 포함될 수 있습니다.  
  
-   [sealed](../../../csharp/language-reference/keywords/sealed.md) 한정자를 사용하여 추상 클래스를 수정할 수는 없습니다. 두 한정자가 상반된 의미를 가지기 때문입니다. `sealed` 한정자를 사용하면 클래스가 상속되지 않고 `abstract` 한정자를 사용하려면 클래스가 상속되어야 합니다.  
  
-   추상 클래스에서 추상이 아닌 파생 클래스에는 모든 상속된 메서드 및 접근자의 실제 구현이 포함되어야 합니다.  
  
 메서드 또는 속성 선언에서 `abstract` 한정자를 사용하여 메서드 또는 속성에 구현이 포함되지 않음을 나타냅니다.  
  
 추상 메서드에는 다음과 같은 기능이 있습니다.  
  
-   추상 메서드는 암시적으로 가상 메서드입니다.  
  
-   추상 메서드 선언은 추상 클래스에서만 허용됩니다.  
  
-   추상 메서드 선언은 실제 구현을 제공하지 않으므로 메서드 본문이 없습니다. 메서드 선언은 세미콜론으로 끝나고 시그니처 뒤에 중괄호({ })가 없습니다. 예:  
  
    ```  
    public abstract void MyMethod();  
    ```  
  
     구현은 추상이 아닌 클래스의 멤버인 재정의 메서드 [override](../../../csharp/language-reference/keywords/override.md)에 의해 제공됩니다.  
  
-   추상 메서드 선언에서 [static](../../../csharp/language-reference/keywords/static.md) 또는 [virtual](../../../csharp/language-reference/keywords/virtual.md) 한정자를 사용하는 것은 오류입니다.  
  
 선언 및 호출 구문의 차이점을 제외하고 추상 속성은 추상 메서드처럼 동작합니다.  
  
-   정적 속성에서 `abstract` 한정자를 사용하는 것은 오류입니다.  
  
-   [override](../../../csharp/language-reference/keywords/override.md) 한정자를 사용하는 속성 선언을 포함하여 상속된 추상 속성을 파생 클래스에서 재정의할 수 있습니다.  
  
 추상 클래스에 대한 자세한 내용은 [추상 및 봉인 클래스와 클래스 멤버](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md)를 참조하세요.  
  
 추상 클래스는 모든 인터페이스 멤버에 대한 구현을 제공해야 합니다.  
  
 인터페이스를 구현하는 추상 클래스는 인터페이스 메서드를 추상 메서드에 매핑할 수 있습니다. 예:  
  
 [!code-cs[csrefKeywordsModifiers#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/abstract_2.cs)]  
  
## <a name="example"></a>예제  
 이 예제에서 `DerivedClass` 클래스는 추상 클래스 `BaseClass`에서 파생됩니다. 추상 클래스에는 추상 메서드 `AbstractMethod` 및 두 개의 추상 속성 `X` 및 `Y`가 포함됩니다.  
  
 [!code-cs[csrefKeywordsModifiers#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/abstract_3.cs)]  
  
 앞의 예제에서 다음과 같이 문을 사용하여 추상 클래스를 인스턴스화하려고 하면,  
  
```  
BaseClass bc = new BaseClass();   // Error  
```  
  
 컴파일러가 추상 클래스 'BaseClass'의 인스턴스를 만들 수 없다는 오류가 표시됩니다.  
  
## <a name="c-language-specification"></a>C# 언어 사양  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [C# 참조](../../../csharp/language-reference/index.md)   
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [한정자](../../../csharp/language-reference/keywords/modifiers.md)   
 [virtual](../../../csharp/language-reference/keywords/virtual.md)   
 [override](../../../csharp/language-reference/keywords/override.md)   
 [C# 키워드](../../../csharp/language-reference/keywords/index.md)
