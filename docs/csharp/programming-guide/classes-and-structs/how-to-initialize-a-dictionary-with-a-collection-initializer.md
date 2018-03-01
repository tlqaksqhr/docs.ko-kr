---
title: "방법: 컬렉션 이니셜라이저를 사용하여 사전 초기화(C# 프로그래밍 가이드)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- collection initializers [C#], with Dictionary
ms.assetid: 25283922-f8ee-40dc-a639-fac30804ec71
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 8b8de5fb85a839d52ad00ad552ef823d9817e9b7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-initialize-a-dictionary-with-a-collection-initializer-c-programming-guide"></a>방법: 컬렉션 이니셜라이저를 사용하여 사전 초기화(C# 프로그래밍 가이드)
@@@<xref:System.Collections.Generic.Dictionary`2> contains a collection of key/value pairs. Its <xref:System.Collections.Generic.Dictionary`2.Add*> 메서드는 키와 값에 대해 하나씩, 두 개의 매개 변수를 사용합니다. @@@<xref:System.Collections.Generic.Dictionary`2>, or any collection whose `Add` 메서드가 여러 매개 변수를 사용함)를 초기화하려면 다음 예제와 같이 각 매개 변수 집합을 중괄호로 묶습니다.  
  
## <a name="example"></a>예제  
 @@@다음 코드 예제에서 <xref:System.Collections.Generic.Dictionary`2> is initialized with instances of type `StudentName`.  
  
 [!code-csharp[csProgGuideLINQ#34](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-initialize-a-dictionary-with-a-collection-initializer_1.cs)]  
  
 컬렉션의 각 요소에는 두 쌍의 중괄호가 있습니다. 안쪽 중괄호는 `StudentName`에 대한 개체 이니셜라이저를 묶고, 바깥쪽 중괄호는 `students`<xref:System.Collections.Generic.Dictionary`2>에 추가할 키/값 쌍에 대한 이니셜라이저를 묶습니다. 마지막으로, 사전에 대한 전체 컬렉션 이니셜라이저가 중괄호로 묶여 있습니다.  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 코드를 실행하려면 클래스를 복사하여 [!INCLUDE[vs_current_short](~/includes/vs-current-short-md.md)]에서 생성된 Visual C# 콘솔 응용 프로그램 프로젝트에 붙여넣습니다. 기본적으로 이 프로젝트는 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 버전 3.5를 대상으로 하며, System.Core.dll에 대한 참조 및 System.Linq에 대한 using 지시문을 포함합니다. 이러한 요구 사항 중 하나 이상이 프로젝트에 없는 경우 수동으로 추가할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)  
 [개체 이니셜라이저 및 컬렉션 이니셜라이저](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)
