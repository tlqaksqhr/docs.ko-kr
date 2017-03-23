---
title: "방법: 복사 생성자 작성(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "C# 언어, 복사 생성자"
  - "복사 생성자[C#]"
ms.assetid: fba899b5-fc41-428e-a745-3ebdbf37990a
caps.latest.revision: 20
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 20
---
# 방법: 복사 생성자 작성(C# 프로그래밍 가이드)
C\#는 개체에 대한 복사 생성자를 제공하지 않지만 사용자가 직접 작성할 수 있습니다.  
  
## 예제  
 다음 예에서 `Person` [클래스](../../../csharp/language-reference/keywords/class.md)는 해당 인수로 `Person` 인스턴스를 받아들이는 복사 생성자를 정의합니다.  인수의 속성 값은 `Person`의 새 인스턴스 속성에 할당됩니다.  코드는 클래스의 인스턴스 생성자에게 복사하려는 `Name` 및 `Age` 인스턴스 속성을 보내는 다른 복사 생성자를 포함합니다.  
  
 [!code-cs[csProgGuideObjects#16](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-write-a-copy-constructor_1.cs)]  
  
## 참고 항목  
 <xref:System.ICloneable>   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [클래스 및 구조체](../../../csharp/programming-guide/classes-and-structs/index.md)   
 [생성자](../../../csharp/programming-guide/classes-and-structs/constructors.md)   
 [소멸자](../../../csharp/programming-guide/classes-and-structs/destructors.md)