---
title: "부분(형식)(C# 참조) | Microsoft Docs"
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
  - "partialtype"
  - "partialtype_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "partial 형식[C#]"
ms.assetid: 27320743-a22e-4c7b-b0b3-53afe3607334
caps.latest.revision: 24
caps.handback.revision: 24
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 부분(형식)(C# 참조)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

부분 형식\(Partial Type\) 정의를 사용하면 클래스, 구조체 또는 인터페이스의 정의를 여러 파일로 분할할 수 있습니다.  
  
 File1.cs:  
  
 [!code-cs[csrefKeywordsContextual#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/partial-type_1.cs)]  
  
 File2.cs에서 선언은 다음과 같습니다.  
  
 [!code-cs[csrefKeywordsContextual#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/partial-type_2.cs)]  
  
## 설명  
 클래스, 구조체 또는 인터페이스 형식을 여러 파일로 분할하면 대형 프로젝트에서 또는 [Windows Forms Designer](http://msdn.microsoft.com/ko-kr/3c3d61f8-f36c-4d41-b9c3-398376fabb15)에서 제공된 것과 같이 자동으로 생성된 코드로 작업할 때 유용할 수 있습니다.  부분 형식에는 [부분 메서드](../../../csharp/language-reference/keywords/partial-method.md)가 포함될 수 있습니다.  자세한 내용은 [Partial 클래스 및 메서드](../../../csharp/programming-guide/classes-and-structs/partial-classes-and-methods.md)를 참조하십시오.  
  
## C\# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [한정자](../../../csharp/language-reference/keywords/modifiers.md)   
 [제네릭 소개](../../../csharp/programming-guide/generics/introduction-to-generics.md)