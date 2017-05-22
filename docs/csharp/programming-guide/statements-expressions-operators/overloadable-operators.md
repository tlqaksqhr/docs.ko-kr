---
title: "오버로드할 수 있는 연산자(C# 프로그래밍 가이드) | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- C# language, operator overloading
- operator overloading [C#]
ms.assetid: 390d9d01-79fc-40ab-9ed3-0bf448da1b6a
caps.latest.revision: 18
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
ms.sourcegitcommit: 400dfda51d978f35c3995f90840643aaff1b9c13
ms.openlocfilehash: 1d3f942dca761c4425ed8c2129b752dec349a40f
ms.contentlocale: ko-kr
ms.lasthandoff: 05/22/2017

---
# <a name="overloadable-operators-c-programming-guide"></a>오버로드할 수 있는 연산자(C# 프로그래밍 가이드)
C#에서는 [operator](../../../csharp/language-reference/keywords/operator.md) 키워드로 정적 멤버 함수를 정의하여 사용자 정의 형식에서 연산자를 오버로드할 수 있습니다. 그러나 일부 연산자는 오버로드할 수 없으며 일부는 다음 표에 나열된 제한 사항이 적용됩니다.  
  
|연산자|오버로드 가능성|  
|---------------|---------------------|  
|[+](../../../csharp/language-reference/operators/addition-operator.md), [-](../../../csharp/language-reference/operators/subtraction-operator.md), [!](../../../csharp/language-reference/operators/logical-negation-operator.md), [~](../../../csharp/language-reference/operators/bitwise-complement-operator.md), [++](../../../csharp/language-reference/operators/increment-operator.md), [--](../../../csharp/language-reference/operators/decrement-operator.md), [true](../../../csharp/language-reference/keywords/true.md), [false](../../../csharp/language-reference/keywords/false.md)|이러한 단항 연산자는 오버로드할 수 있습니다.|  
|[+](../../../csharp/language-reference/operators/addition-operator.md), [-](../../../csharp/language-reference/operators/subtraction-operator.md), [*](../../../csharp/language-reference/operators/multiplication-operator.md), [/](../../../csharp/language-reference/operators/division-operator.md), [%](../../../csharp/language-reference/operators/modulus-operator.md), [&](../../../csharp/language-reference/operators/and-operator.md), [&#124;](../../../csharp/language-reference/operators/or-operator.md), [^](../../../csharp/language-reference/operators/xor-operator.md), [<\<](../../../csharp/language-reference/operators/left-shift-operator.md), [>>](../../../csharp/language-reference/operators/right-shift-operator.md)|이러한 이항 연산자는 오버로드할 수 있습니다.|  
|[==](../../../csharp/language-reference/operators/equality-comparison-operator.md), [!=](../../../csharp/language-reference/operators/not-equal-operator.md), [\<](../../../csharp/language-reference/operators/less-than-operator.md), [>](../../../csharp/language-reference/operators/greater-than-operator.md), [\<=](../../../csharp/language-reference/operators/less-than-equal-operator.md), [>=](../../../csharp/language-reference/operators/greater-than-equal-operator.md)|비교 연산자는 오버로드할 수 있지만 이 표 다음에 오는 참고 사항을 참조하세요.|  
|[&&](../../../csharp/language-reference/operators/conditional-and-operator.md), [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md)|조건부 논리 연산자는 오버로드할 수 없지만 오버로드할 수 있는 `&` 및 `&#124;`를 사용하여 계산됩니다.|  
|[&#91;&#93;](../../../csharp/language-reference/operators/index-operator.md)|배열 인덱싱 연산자는 오버로드할 수 없지만 인덱서를 정의할 수 있습니다.|  
|[(T)x](../../../csharp/language-reference/operators/invocation-operator.md)|캐스트 연산자는 오버로드할 수 없지만 새 변환 연산자를 정의할 수 있습니다([explicit](../../../csharp/language-reference/keywords/explicit.md) 및 [implicit](../../../csharp/language-reference/keywords/implicit.md) 참조).|  
|[+=](../../../csharp/language-reference/operators/addition-assignment-operator.md), [-=](../../../csharp/language-reference/operators/subtraction-assignment-operator.md), [*=](../../../csharp/language-reference/operators/multiplication-assignment-operator.md), [/=](../../../csharp/language-reference/operators/division-assignment-operator.md), [%=](../../../csharp/language-reference/operators/modulus-assignment-operator.md), [&=](../../../csharp/language-reference/operators/and-assignment-operator.md), [&#124;=](../../../csharp/language-reference/operators/or-assignment-operator.md), [^=](../../../csharp/language-reference/operators/xor-assignment-operator.md), [<\<=](../../../csharp/language-reference/operators/left-shift-assignment-operator.md), [>>=](../../../csharp/language-reference/operators/right-shift-assignment-operator.md)|할당 연산자는 오버로드할 수 없지만 예를 들어 `+=`는 오버로드할 수 있는 `+`를 사용하여 계산됩니다.|  
|[=](../../../csharp/language-reference/operators/assignment-operator.md), [.](../../../csharp/language-reference/operators/member-access-operator.md), [?:](../../../csharp/language-reference/operators/conditional-operator.md), [??](../../../csharp/language-reference/operators/null-conditional-operator.md), [->](../../../csharp/language-reference/operators/dereference-operator.md), [=>](../../../csharp/language-reference/operators/lambda-operator.md), [f(x)](../../../csharp/language-reference/operators/invocation-operator.md), [as](../../../csharp/language-reference/keywords/as.md), [checked](../../../csharp/language-reference/keywords/checked.md), [unchecked](../../../csharp/language-reference/keywords/unchecked.md), [default](../../../csharp/programming-guide/generics/default-keyword-in-generic-code.md), [delegate](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md), [is](../../../csharp/language-reference/keywords/is.md), [new](../../../csharp/language-reference/keywords/new.md), [sizeof](../../../csharp/language-reference/keywords/sizeof.md), [typeof](../../../csharp/language-reference/keywords/typeof.md)|이러한 연산자는 오버로드할 수 없습니다.|  
  
> [!NOTE]
>  비교 연산자는 오버로드될 경우 쌍으로 오버로드되어야 합니다. 즉, `==`가 오버로드되면 `!=`도 오버로드되어야 합니다. 그 반대의 경우도 마찬가지이며, `<`와 `>`, `<=`와 `>=`의 경우도 유사합니다.  
  
 사용자 지정 클래스에서 연산자를 오버로드하려면 올바른 서명을 사용하여 클래스에 메서드를 만들어야 합니다. 메서드 이름은 "연산자 X"로 지정해야 하며, 여기서 X는 오버로드할 연산자의 이름 또는 기호입니다. 단항 연산자는 매개 변수가 하나이고, 이항 연산자는 매개 변수가 두 개입니다. 각각의 경우 한 매개 변수는 연산자를 선언하는 클래스나 구조체와 동일한 형식이어야 합니다.  
  
```csharp  
public static Complex operator +(Complex c1, Complex c2)  
    {  
        Return new Complex(c1.real + c2.real, c1.imaginary + c2.imaginary);  
    }  
  
```  
  
 일반적으로 식의 결과와 함께 바로 반환되는 정의가 있습니다.  이러한 상황에 `=>`를 사용하는 구문 바로 가기가 있습니다.  
  
```csharp  
public static Complex operator +(Complex c1, Complex c2) =>  
        new Complex(c1.real + c2.real, c1.imaginary + c2.imaginary);  
  
    // Override ToString() to display a complex number   
    // in the traditional format:  
    public override string ToString() => $"{this.real} + {this.imaginary}";  
  
```  
  
 자세한 내용은 [방법: 연산자 오버로드를 사용하여 복소수 클래스 만들기](../../../csharp/programming-guide/statements-expressions-operators/how-to-use-operator-overloading-to-create-a-complex-number-class.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [문, 식, 연산자](../../../csharp/programming-guide/statements-expressions-operators/index.md)   
 [연산자](../../../csharp/programming-guide/statements-expressions-operators/operators.md)   
 [C# 연산자](../../../csharp/language-reference/operators/index.md)   
 [Why are overloaded operators always static in C#?](http://go.microsoft.com/fwlink/?LinkId=112383)(오버로드된 연산자가 C#에서 항상 정적인 이유)

