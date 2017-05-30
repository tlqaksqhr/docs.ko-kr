---
title: "#if(C# 참조) | Microsoft Docs"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '#if'
dev_langs:
- CSharp
helpviewer_keywords:
- '#if directive [C#]'
ms.assetid: 48cabbff-ca82-491f-a56a-eeccd528c7c2
caps.latest.revision: 17
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
ms.sourcegitcommit: a780a11d8dd238187eb82933359bbb151bb3c333
ms.openlocfilehash: 4fc51446d297015d9e492703c9b1868c3b513c53
ms.contentlocale: ko-kr
ms.lasthandoff: 05/22/2017

---
# <a name="if-c-reference"></a>#if(C# 참조)
C# 컴파일러는 `#if` 지시문과 [#endif](../../../csharp/language-reference/preprocessor-directives/preprocessor-endif.md) 지시문이 차례로 확인되면 지정된 기호가 정의되어 있어야 지시문 사이의 코드를 컴파일합니다.  C 및 C++와 달리 기호에 숫자 값을 할당할 수는 없습니다. C#의 #if 문은 부울이며 기호가 정의되었는지 여부만을 테스트합니다. 예를 들면 다음과 같습니다.  
  
```  
#define DEBUG  
// ...  
#if DEBUG  
    Console.WriteLine("Debug version");  
#endif  
```  
  
 [==](../../../csharp/language-reference/operators/equality-comparison-operator.md)(같음), [!=](../../../csharp/language-reference/operators/not-equal-operator.md)(같지 않음) 연산자는 [true](../../../csharp/language-reference/keywords/true.md) 또는 [false](../../../csharp/language-reference/keywords/false.md)를 테스트할 때만 사용할 수 있습니다. true가 반환되면 기호가 정의된 것입니다. `#if DEBUG` 문의 의미는 `#if (DEBUG == true)`와 같습니다. [&&](../../../csharp/language-reference/operators/conditional-and-operator.md)(및), [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md)(또는), [!](../../../csharp/language-reference/operators/logical-negation-operator.md)(아님) 연산자를 사용하면 여러 기호가 정의되었는지 여부를 평가할 수 있습니다. 기호와 연산자를 괄호로 묶을 수도 있습니다.  
  
## <a name="remarks"></a>설명  
 `#if`를 [#else](../../../csharp/language-reference/preprocessor-directives/preprocessor-else.md), [#elif](../../../csharp/language-reference/preprocessor-directives/preprocessor-elif.md), [#endif](../../../csharp/language-reference/preprocessor-directives/preprocessor-endif.md), [#define](../../../csharp/language-reference/preprocessor-directives/preprocessor-define.md) 및 [#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md) 지시문과 함께 사용하면 하나 이상의 기호 유무에 따라 코드를 포함하거나 제거할 수 있습니다. 따라서 코드를 디버그 빌드용으로 컴파일하거나 특정 구성용으로 컴파일할 때 유용할 수 있습니다.  
  
 `#if` 지시문으로 시작되는 조건부 지시문은 `#endif` 지시문을 사용하여 명시적으로 종료해야 합니다.  
  
 `#define`을 사용하면 기호를 정의할 수 있습니다. 그러면 `#if` 지시문으로 전달되는 식으로 해당 기호를 사용하는 경우 식이 `true`로 평가됩니다.  
  
 [/define](../../../csharp/language-reference/compiler-options/define-compiler-option.md) 컴파일러 옵션으로 기호를 정의할 수도 있습니다. [#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md)로 기호 정의를 해제할 수 있습니다.  
  
 `/define` 또는 `#define`으로 정의하는 기호는 동일한 이름의 변수와 충돌하지 않습니다. 즉, 변수 이름이 전처리기 지시문에 전달되지 않아야 하며 전처리기 지시문을 통해서만 기호를 평가할 수 있습니다.  
  
 `#define`을 사용하여 만든 기호의 범위는 해당 기호가 정의된 파일입니다.  
  
## <a name="example"></a>예제  
  
```  
// preprocessor_if.cs  
#define DEBUG#define MYTEST  
using System;  
public class MyClass   
{  
    static void Main()   
    {  
#if (DEBUG && !MYTEST)  
        Console.WriteLine("DEBUG is defined");  
#elif (!DEBUG && MYTEST)  
        Console.WriteLine("MYTEST is defined");  
#elif (DEBUG && MYTEST)  
        Console.WriteLine("DEBUG and MYTEST are defined");  
#else  
        Console.WriteLine("DEBUG and MYTEST are not defined");  
#endif  
    }  
}  
```  
  
 **DEBUG and MYTEST are defined**   
## <a name="see-also"></a>참고 항목  
 [C# 참조](../../../csharp/language-reference/index.md)   
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C# 전처리기 지시문](../../../csharp/language-reference/preprocessor-directives/index.md)
