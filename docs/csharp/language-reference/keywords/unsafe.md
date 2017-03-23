---
title: "unsafe(C# 참조) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "unsafe_CSharpKeyword"
  - "unsafe"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "unsafe 키워드[C#]"
ms.assetid: 7e818009-1c6e-4b9e-b769-3728a01586a0
caps.latest.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 19
---
# unsafe(C# 참조)
`unsafe` 키워드는 안전하지 않은 컨텍스트를 나타내며, 포인터에 관련된 모든 작업에 필요합니다.  자세한 내용은 [안전하지 않은 코드 및 포인터](../../../csharp/programming-guide/unsafe-code-pointers/index.md)를 참조하십시오.  
  
 형식이나 멤버의 선언에 `unsafe` 한정자를 사용할 수 있습니다.  따라서 형식이나 멤버의 전체 텍스트 범위가 안전하지 않은 컨텍스트로 취급됩니다.  예를 들어, 다음 예제는 `unsafe` 한정자를 사용해 선언한 메서드입니다.  
  
```  
  
      unsafe static void FastCopy(byte[] src, byte[] dst, int count)  
{  
    // Unsafe context: can use pointers here.  
}  
```  
  
 안전하지 않은 컨텍스트의 범위는 매개 변수 목록에서 메서드의 끝까지 확장되므로 매개 변수 목록에 포인터도 사용할 수 있습니다.  
  
```  
  
unsafe static void FastCopy ( byte* ps, byte* pd, int count ) {...}  
```  
  
 또한 안전하지 않은 블록을 사용해 이 블록 내에서 안전하지 않은 코드를 사용할 수도 있습니다.  예를 들면 다음과 같습니다.  
  
```  
  
      unsafe  
{  
    // Unsafe context: can use pointers here.  
}  
```  
  
 안전하지 않은 코드를 컴파일하려면 컴파일러 옵션 [\/unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md)를 지정해야 합니다.  안전하지 않은 코드는 공용 언어 런타임으로 확인할 수 없습니다.  
  
## 예제  
 [!code-cs[csrefKeywordsModifiers#22](../../../csharp/language-reference/keywords/codesnippet/CSharp/unsafe_1.cs)]  
  
## C\# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C\# 키워드](../../../csharp/language-reference/keywords/index.md)   
 [fixed 문](../../../csharp/language-reference/keywords/fixed-statement.md)   
 [안전하지 않은 코드 및 포인터](../../../csharp/programming-guide/unsafe-code-pointers/index.md)   
 [고정 크기 버퍼](../../../csharp/programming-guide/unsafe-code-pointers/fixed-size-buffers.md)