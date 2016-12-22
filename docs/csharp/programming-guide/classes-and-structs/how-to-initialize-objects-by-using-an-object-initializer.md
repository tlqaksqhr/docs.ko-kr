---
title: "방법: 개체 이니셜라이저를 사용하여 개체 초기화(C# 프로그래밍 가이드) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
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
  - "개체 이니셜라이저[C#], 사용 방법"
  - "개체[C#], 초기화"
ms.assetid: 4b75ebb2-2e29-43de-929c-d736a8f27ce6
caps.latest.revision: 20
caps.handback.revision: 20
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 방법: 개체 이니셜라이저를 사용하여 개체 초기화(C# 프로그래밍 가이드)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

개체 이니셜라이저를 사용하면 형식의 생성자를 명시적으로 호출하지 않고도 선언적 방식으로 형식 개체를 초기화할 수 있습니다.  
  
 다음의 예제에서는 명명된 개체와 함께 개체 이니셜라이저를 사용하는 방법을 보여 줍니다.  컴파일러 프로세스는 먼저 기본 인스턴스 생성자에 액세스 하 고 다음 멤버 초기화를 처리 하 여 이니셜라이저 개체입니다.  따라서 기본 생성자가 클래스에서 `private`로 선언된 경우 공용 액세스가 필요한 개체 이니셜라이저가 실패합니다.  
  
 익명 형식을 정의 하는 경우에 개체 이니셜라이저를 사용 해야 합니다.  자세한 내용은 [방법: 쿼리에서 요소 속성의 하위 집합 반환](../../../csharp/programming-guide/classes-and-structs/how-to-return-subsets-of-element-properties-in-a-query.md)을 참조하십시오.  
  
## 예제  
 다음 예제에서는 개체 이니셜라이저를 사용하여 새 `StudentName` 형식을 초기화하는 방법을 보여 줍니다.  
  
 [!code-cs[csProgGuideLINQ#35](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-initialize-objects-by-using-an-object-initializer_1.cs)]  
  
## 예제  
 다음 예제에서는 컬렉션 이니셜라이저를 사용하여 컬렉션의 `StudentName` 형식을 초기화하는 방법을 보여 줍니다.  컬렉션 이니셜라이저는 일련의 쉼표로 구분된 개체 이니셜라이저입니다.  
  
 [!code-cs[csProgGuideLINQ#36](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-initialize-objects-by-using-an-object-initializer_2.cs)]  
  
## 코드 컴파일  
 이 코드를 실행하려면 [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)]에서 만들어진 Visual C\# 콘솔 응용 프로그램 프로젝트에 클래스를 복사하여 붙여넣습니다.  자세한 내용은 [How to: Create a LINQ Project](../Topic/How%20to:%20Create%20a%20LINQ%20Project.md)을 참조하십시오.  
  
## 참고 항목  
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [개체 및 컬렉션 이니셜라이저](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)