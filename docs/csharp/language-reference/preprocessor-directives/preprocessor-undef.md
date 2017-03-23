---
title: "#undef(C# 참조) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "#undef"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "#undef 지시문[C#]"
ms.assetid: 686c92d2-7194-4be4-b2f4-80091712d513
caps.latest.revision: 12
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 12
---
# #undef(C# 참조)
`#undef`를 사용하면 기호의 정의를 해제할 수 있습니다. 이때 정의 해제된 기호를 [\#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) 지시문의 식으로 사용하면 식이 `false`가 됩니다.  
  
 기호는 [\#define](../../../csharp/language-reference/preprocessor-directives/preprocessor-define.md) 지시문 또는 [\/define](../../../csharp/language-reference/compiler-options/define-compiler-option.md) 컴파일러 옵션으로 정의할 수 있습니다.  지시문이 아닌 모든 문을 사용하려면 `#undef` 지시문이 먼저 파일에 나타나야 합니다.  
  
## 예제  
  
```  
// preprocessor_undef.cs  
// compile with: /d:DEBUG  
#undef DEBUG  
using System;  
class MyClass   
{  
    static void Main()   
    {  
#if DEBUG  
        Console.WriteLine("DEBUG is defined");  
#else  
        Console.WriteLine("DEBUG is not defined");  
#endif  
    }  
}  
```  
  
  **DEBUG가 정의되지 않음**   
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C\# 전처리기 지시문](../../../csharp/language-reference/preprocessor-directives/index.md)