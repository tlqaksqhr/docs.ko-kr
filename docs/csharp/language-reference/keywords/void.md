---
title: "void(C# 참조) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "void_CSharpKeyword"
  - "void"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "void 키워드[C#]"
ms.assetid: 0d2d8a95-fe20-4fbd-bf5d-c1e54bce71d4
caps.latest.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 15
---
# void(C# 참조)
방법에 대 한 반환 형식으로 사용 하는 경우 `void` 메서드 값을 반환 하지 않음을 지정 합니다.  
  
 `void`메서드의 매개 변수 목록에 사용할 수 없습니다.  매개 변수가 없으면서 값을 반환하지 않는 메서드는 다음과 같이 선언됩니다.  
  
```  
public void SampleMethod()  
{  
    // Body of the method.  
}  
  
```  
  
 또한 `void`는 알 수 없는 형식에 대한 포인터를 선언하기 위해 안전하지 않은 컨텍스트에서 사용합니다.  자세한 내용은 [포인터 형식](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)을 참조하십시오.  
  
 `void`는 .NET Framework <xref:System.Void?displayProperty=fullName> 형식의 별칭입니다.  
  
## C\# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C\# 키워드](../../../csharp/language-reference/keywords/index.md)   
 [참조 형식](../../../csharp/language-reference/keywords/reference-types.md)   
 [값 형식](../../../csharp/language-reference/keywords/value-types.md)   
 [메서드](../../../csharp/programming-guide/classes-and-structs/methods.md)   
 [안전하지 않은 코드 및 포인터](../../../csharp/programming-guide/unsafe-code-pointers/index.md)