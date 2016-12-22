---
title: "생성자(C# 프로그래밍 가이드) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "생성자[C#]"
  - "클래스[C#], 생성자"
  - "C# 언어, 생성자"
ms.assetid: df2e2e9d-7998-418b-8e7d-890c17ff6c95
caps.latest.revision: 23
caps.handback.revision: 23
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 생성자(C# 프로그래밍 가이드)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

[클래스](../../../csharp/language-reference/keywords/class.md)나 [구조체](../../../csharp/language-reference/keywords/struct.md)를 만들 때마다 해당 생성자가 호출됩니다.  클래스나 구조체에는 서로 다른 인수를 사용하는 여러 생성자가 있을 수 있습니다.  프로그래머는 생성자를 통해 기본값을 설정하고, 인스턴스화를 제한하며, 융통성 있고 읽기 쉬운 코드를 작성할 수 있습니다.  자세한 내용 및 예제를 보려면 [생성자 사용](../../../csharp/programming-guide/classes-and-structs/using-constructors.md) 및 [인스턴스 생성자](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md)를 참조하십시오.  
  
 사용자가 작성한 개체에 대해 생성자를 제공하지 않으면 C\#에서 기본적으로 개체를 인스턴스화하고 모든 멤버 변수에 기본값을 설정하는 생성자를 만듭니다. 기본값은 [기본값 표](../../../csharp/language-reference/keywords/default-values-table.md)에 나열되어 있습니다.  자세한 내용과 예제를 보려면 [인스턴스 생성자](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md)을 참조하십시오.  
  
 정적 클래스와 구조체에도 생성자가 있을 수 있습니다.  자세한 내용과 예제를 보려면 [정적 생성자](../../../csharp/programming-guide/classes-and-structs/static-constructors.md)을 참조하십시오.  
  
## 단원 내용  
 [생성자 사용](../../../csharp/programming-guide/classes-and-structs/using-constructors.md)  
  
 [인스턴스 생성자](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md)  
  
 [전용 생성자](../../../csharp/programming-guide/classes-and-structs/private-constructors.md)  
  
 [정적 생성자](../../../csharp/programming-guide/classes-and-structs/static-constructors.md)  
  
 [방법: 복사 생성자 작성](../Topic/How%20to:%20Write%20a%20Copy%20Constructor%20\(C%23%20Programming%20Guide\).md)  
  
## 참고 항목  
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [클래스 및 구조체](../../../csharp/programming-guide/classes-and-structs/index.md)   
 [소멸자](../../../csharp/programming-guide/classes-and-structs/destructors.md)   
 [static](../../../csharp/language-reference/keywords/static.md)   
 [이유는 이니셜라이저는 생성자로 반대 순서로 실행 합니까? 1부](http://go.microsoft.com/fwlink/?LinkId=112374)