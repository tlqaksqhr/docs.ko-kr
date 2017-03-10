---
title: "#error(C# 참조) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "#error"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "#error 지시문[C#]"
ms.assetid: f2a7f3af-4cf9-4111-b369-70204d24b26b
caps.latest.revision: 10
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 10
---
# #error(C# 참조)
`#error`를 사용하면 코드의 특정 위치에서 오류를 생성할 수 있습니다.  예를 들면 다음과 같습니다.  
  
```  
#error Deprecated code in this method.  
```  
  
## 설명  
 `#error`는 일반적으로 조건부 지시문에 사용됩니다.  
  
 또한 [\#warning](../../../csharp/language-reference/preprocessor-directives/preprocessor-warning.md)으로 사용자 정의 경고를 생성할 수도 있습니다.  
  
## 예제  
  
```  
// preprocessor_error.cs  
// CS1029 expected  
#define DEBUG  
class MainClass   
{  
    static void Main()   
    {  
#if DEBUG  
#error DEBUG is defined  
#endif  
    }  
}  
```  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C\# 전처리기 지시문](../../../csharp/language-reference/preprocessor-directives/index.md)