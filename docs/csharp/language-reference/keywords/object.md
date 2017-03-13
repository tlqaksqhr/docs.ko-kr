---
title: "object(C# 참조) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "object_CSharpKeyword"
  - "object"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "object 키워드[C#]"
ms.assetid: 93f60c0b-e17a-40a9-9362-cca5fb77b0e7
caps.latest.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 16
---
# object(C# 참조)
`object` 형식은 .NET Framework의 <xref:System.Object>에 대한 별칭입니다.  C\#의 통합된 형식 시스템에서는 미리 정의된 형식과 사용자가 정의한 형식, 참조 형식과 값 형식 같은 모든 형식이 <xref:System.Object>에서 직접 또는 간접적으로 상속됩니다.  `object` 형식의 변수에는 모든 형식의 값을 할당할 수 있습니다.  값 형식의 변수를 object 형식으로 변환하는 경우 이를 *boxing*이라고 합니다.  object 형식의 변수를 값 형식으로 변환하는 경우 이를 *unboxing*이라고 합니다.  자세한 내용은 [Boxing 및 Unboxing](../../../csharp/programming-guide/types/boxing-and-unboxing.md)을 참조하십시오.  
  
## 예제  
 다음 예제에서는 `object` 형식 변수에서 임의의 데이터 형식 값을 수용하는 방법과 `object` 형식 변수가 .NET Framework에서 <xref:System.Object> 메서드를 사용하는 방법에 대해 보여 줍니다.  
  
 [!code-cs[csrefKeywordsTypes#16](../../../csharp/language-reference/keywords/codesnippet/CSharp/object_1.cs)]  
  
## C\# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C\# 키워드](../../../csharp/language-reference/keywords/index.md)   
 [참조 형식](../../../csharp/language-reference/keywords/reference-types.md)   
 [값 형식](../../../csharp/language-reference/keywords/value-types.md)