---
title: "방법: 새 열거형 메서드 만들기(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "열거형 확장성[C#]"
  - "열거형[C#]"
  - "확장 메서드[C#], 열거형"
ms.assetid: 100106f9-1e54-462c-8ebe-3892fe23b6eb
caps.latest.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 7
---
# 방법: 새 열거형 메서드 만들기(C# 프로그래밍 가이드)
확장 메서드를 사용하여 특정 열거형 형식에 특정한 기능을 추가할 수 있습니다.  
  
## 예제  
 다음 예제에서 `Grades` 열거형은 학생이 클래스에서 받을 수 있는 문자 등급을 나타냅니다.  `Passing`이라는 확장 메서드가 `Grades` 형식에 추가되어 이제 형식의 각 인스턴스는 통과 등급을 나타낼지 여부를 "알 수 있습니다".  
  
 [!code-cs[csProgGuideExtensionMethods#2](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-create-a-new-method-for-an-enumeration_1.cs)]  
  
 `Extensions` 클래스는 동적으로 업데이트된 정적 변수도 포함하고 확장 메서드의 반환 값이 변수의 현재 값을 반영합니다.  즉, 내부적으로는 확장 메서드가 정의된 정적 클래스에서 직접 호출됩니다.  
  
## 코드 컴파일  
 이 코드를 실행하려면 [!INCLUDE[vs_current_short](../../../csharp/programming-guide/classes-and-structs/includes/vs-current-short-md.md)]에서 만들어진 Visual C\# 콘솔 응용 프로그램 프로젝트에 코드를 복사하여 붙여넣습니다.  기본적으로 이 프로젝트는 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)]의 버전 3.5를 대상으로 하며 System.Core.dll에 대한 참조와 System.Linq에 대한 `using` 지시문이 있습니다.  프로젝트에서 이러한 요구 사항 중 하나 이상이 누락된 경우 수동으로 추가할 수 있습니다.  자세한 내용은 [How to: Create a LINQ Project](../Topic/How%20to:%20Create%20a%20LINQ%20Project.md)를 참조하십시오.  
  
## 참고 항목  
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [확장 메서드](../../../csharp/programming-guide/classes-and-structs/extension-methods.md)