---
title: "is(C# 참조) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "is_CSharpKeyword"
  - "is"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "is 키워드[C#]"
ms.assetid: bc62316a-d41f-4f90-8300-c6f4f0556e43
caps.latest.revision: 20
caps.handback.revision: 20
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# is(C# 참조)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

지정된 형식과 개체가 호환되는지 검사합니다.  예를 들어 다음 코드에서는 개체가 `MyObject` 형식의 인스턴스이거나 `MyObject`에서 파생된 형식인지 확인할 수 있습니다.  
  
```  
if (obj is MyObject)  
{  
}  
```  
  
 지정된 식이 null이 아니고 예외를 throw하지 않은 채 지정된 개체를 지정된 형식으로 캐스팅할 수 있는 경우 `is` 식은 `true`가 됩니다.  
  
 식이 항상 `true`이거나 항상 `false`인 것으로 알려져 있는 경우 `is` 키워드는 컴파일 타임 경고를 발생시키지만 런타임에는 일반적으로 형식 호환성을 확인합니다.  
  
 `is` 연산자는 오버로드되지 않습니다.  
  
 `is` 연산자는 참조 변환, boxing 변환 및 unboxing 변환만 고려하고  사용자 정의 변환 같은 다른 변환은 고려되지 않습니다.  
  
 무명 메서드는 `is` 연산자의 왼쪽에 사용할 수 없습니다.  이 예외에는 람다 식이 포함됩니다.  
  
## 예제  
 [!code-cs[csrefKeywordsOperator#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/is_1.cs)]  
  
## C\# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C\# 키워드](../../../csharp/language-reference/keywords/index.md)   
 [typeof](../../../csharp/language-reference/keywords/typeof.md)   
 [as](../../../csharp/language-reference/keywords/as.md)   
 [연산자 키워드](../../../csharp/language-reference/keywords/operator-keywords.md)