---
title: "부분(메서드)(C# 참조) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "partialmethod_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "partial 메서드[C#]"
ms.assetid: 43f40242-17e0-4452-8573-090503ad3137
caps.latest.revision: 26
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 26
---
# 부분(메서드)(C# 참조)
부분 메서드\(Partial Method\)에는 부분 형식\(Partial Type\)의 일부분에 정의된 시그니처와 다른 형식의 부분에 정의된 구현이 있습니다.  클래스 디자이너는 부분 메서드를 사용하여 이벤트 처리기와 유사한 메서드 후크를 제공하여 개발자가 구현 여부를 결정할 수 있습니다.  개발자가 구현을 제공하지 않는 경우 컴파일러에서는 컴파일 타임에 시그니처를 제거합니다.  부분 메서드에는 다음과 같은 조건이 적용됩니다.  
  
-   부분 형식\(Partial Type\)의 두 부분에서 시그니처가 일치해야 합니다.  
  
-   해당 메서드는 void를 반환해야 합니다.  
  
-   어떠한 액세스 한정자도 사용할 수 없습니다.  부분 메서드\(Partial method\)는 암시적으로 private입니다.  
  
 다음 예제에서는 부분 클래스의 두 부분에서 정의된 부분 메서드를 보여 줍니다.  
  
 [!code-cs[csrefKeywordsContextual#9](../../../csharp/language-reference/keywords/codesnippet/csharp/partial-method_1.cs)]  
  
 자세한 내용은 [Partial 클래스 및 메서드](../../../csharp/programming-guide/classes-and-structs/partial-classes-and-methods.md)을 참조하십시오.  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [부분\(형식\)](../../../csharp/language-reference/keywords/partial-type.md)