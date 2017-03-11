---
title: "#if(C# 참조) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "#if"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "#if 지시문[C#]"
ms.assetid: 48cabbff-ca82-491f-a56a-eeccd528c7c2
caps.latest.revision: 17
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 17
---
# #if(C# 참조)
C\# 컴파일러는 `#if` 지시문 뒤에 [\#endif](../../../csharp/language-reference/preprocessor-directives/preprocessor-endif.md) 지시문이 오는 것을 발견할 때 지정한 기호가 정의된 경우에만 지시문 사이의 코드를 컴파일합니다.  C 및 C\+\+와 달리, 기호에 숫자 값을 할당할 수는 없습니다. C\#의 \#if 문은 Boolean이며, 기호가 정의되었는지 여부만 테스트합니다.  다음 예제를 참조하십시오.  
  
```  
#define DEBUG  
// ...  
#if DEBUG  
    Console.WriteLine("Debug version");  
#endif  
```  
  
 [\=\=](../../../csharp/language-reference/operators/equality-comparison-operator.md)\(같음\), [\!\=](../../../csharp/language-reference/operators/not-equal-operator.md)\(같지 않음\) 연산자는 [true](../../../csharp/language-reference/keywords/true.md) 또는 [false](../../../csharp/language-reference/keywords/false.md)를 테스트하는 경우에만 사용할 수 있습니다.  True는 기호가 정의되었음을 의미합니다.  `#if DEBUG` 문은 `#if (DEBUG == true)`와 의미가 같습니다.  연산자를 사용할 수 있습니다  [& &](../../../csharp/language-reference/operators/conditional-and-operator.md) \(와\)  [&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md) \(or\), and [\!](../../../csharp/language-reference/operators/logical-negation-operator.md) \(not\) 여러 기호가 정의 되었는지 여부를 평가할 수 있습니다.  괄호를 사용하여 기호와 연산자를 그룹화할 수도 있습니다.  
  
## 설명  
 `#if`와 함께 [\#else](../../../csharp/language-reference/preprocessor-directives/preprocessor-else.md), [\#elif](../../../csharp/language-reference/preprocessor-directives/preprocessor-elif.md), [\#endif](../../../csharp/language-reference/preprocessor-directives/preprocessor-endif.md), [\#define](../../../csharp/language-reference/preprocessor-directives/preprocessor-define.md) 및 [\#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md) 지시문을 사용하면 하나 이상의 기호가 있는지 여부에 따라 코드를 포함하거나 제외할 수 있습니다.  이것은 코드를 디버그 빌드용으로 컴파일하거나 특정 구성용으로 컴파일할 때 유용할 수 있습니다.  
  
 `#if` 지시문으로 시작한 조건부 지시문은 명시적으로 `#endif` 지시문으로 종료해야 합니다.  
  
 `#define`을 사용하면 기호를 정의할 수 있습니다. 이때 정의한 기호를 `#if` 지시문에 전달되는 식으로 사용하면 식이 `true`가 됩니다.  
  
 또한 [\/define](../../../csharp/language-reference/compiler-options/define-compiler-option.md) 컴파일러 옵션으로 기호를 정의할 수도 있습니다.  또한 [\#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md)로 기호를 정의하지 않을 수도 있습니다.  
  
 `/define` 또는 `#define`으로 정의한 기호는 같은 이름의 변수와 충돌하지 않습니다.  즉, 변수 이름을 전처리기 지시문에 전달해서는 안 되며 기호는 전처리기 지시문으로만 계산할 수 있습니다.  
  
 `#define`으로 만든 기호의 범위는 해당 기호가 정의된 파일입니다.  
  
## 예제  
  
```  
// preprocessor_if.cs  
#define DEBUG #define MYTEST  
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
  
  **DEBUG 및 MYTEST가 정의되어 있음**   
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C\# 전처리기 지시문](../../../csharp/language-reference/preprocessor-directives/index.md)