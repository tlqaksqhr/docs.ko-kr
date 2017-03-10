---
title: "#define(C# 참조) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "#define"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "#define 지시문[C#]"
ms.assetid: 23638b8f-779c-450e-b600-d55682de7d01
caps.latest.revision: 22
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 22
---
# #define(C# 참조)
`#define`을 사용하여 기호를 정의합니다.  정의한 기호를 [\#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) 지시문에 전달되는 식으로 사용하면 식이 다음 예제에서 보여 주듯이 `true`가 됩니다.  
  
 `#`  `define`   `DEBUG`  
  
## 설명  
  
> [!NOTE]
>  `#define` 지시문은 C 및 C\+\+에서 일반적으로 수행되는 것처럼 상수 값을 선언하는 데 사용할 수 없습니다.  C\#의 상수는 클래스 또는 구조체의 정적 멤버로 정의하는 것이 좋습니다.  이러한 상수가 여러 개 있는 경우 별도의 "Constants" 클래스를 만들어 저장하는 것이 좋습니다.  
  
 기호를 사용하여 컴파일 조건을 지정할 수 있습니다.  이 기호를 [\#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) 또는 [\#elif](../../../csharp/language-reference/preprocessor-directives/preprocessor-elif.md)로 테스트할 수 있습니다.  또한 `conditional` 특성을 사용하여 조건부 컴파일을 수행할 수도 있습니다.  
  
 기호를 정의할 수는 있지만 해당 기호에 값을 대입할 수는 없습니다.  전처리기 지시문이 아닌 모든 명령을 사용하려면 `#define` 지시문이 먼저 파일에 나타나야 합니다.  
  
 또한 [\/define](../../../csharp/language-reference/compiler-options/define-compiler-option.md) 컴파일러 옵션으로 기호를 정의할 수도 있습니다.  또한 [\#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md)로 기호를 정의하지 않을 수도 있습니다.  
  
 `/define` 또는 `#define`으로 정의한 기호는 같은 이름의 변수와 충돌하지 않습니다.  즉, 변수 이름을 전처리기 지시문에 전달해서는 안 되며 기호는 전처리기 지시문으로만 계산할 수 있습니다.  
  
 `#define`을 사용하여 만든 기호의 범위는 해당 기호가 정의된 파일입니다.  
  
 다음 예제와 같이 파일 맨 위에 `#define` 지시문을 추가해야 합니다.  
  
```c#  
#define DEBUG  
//#define TRACE  
#undef TRACE  
  
using System;  
  
public class TestDefine  
{  
    static void Main()  
    {  
#if (DEBUG)  
        Console.WriteLine("Debugging is enabled.");  
#endif  
  
#if (TRACE)  
     Console.WriteLine("Tracing is enabled.");  
#endif  
    }  
}  
// Output:  
// Debugging is enabled.  
```  
  
 기호 정의를 해제하는 방법에 대한 예제는 [\#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md)을 참조하십시오.  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C\# 전처리기 지시문](../../../csharp/language-reference/preprocessor-directives/index.md)   
 [const](../../../csharp/language-reference/keywords/const.md)   
 [How to: Compile Conditionally with Trace and Debug](../Topic/How%20to:%20Compile%20Conditionally%20with%20Trace%20and%20Debug.md)   
 [\#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md)   
 [\#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md)