---
title: "방법: 대리자 선언, 인스턴스화 및 사용(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "대리자[C#], 선언 및 인스턴스화"
ms.assetid: 61c4895f-f785-48f8-8bfe-db73b411c4ae
caps.latest.revision: 21
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 21
---
# 방법: 대리자 선언, 인스턴스화 및 사용(C# 프로그래밍 가이드)
C\# 1.0 이상에서는 다음 예제와 같이 대리자를 선언할 수 있습니다.  
  
 [!code-cs[csProgGuideDelegates#13](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_1.cs)]  
  
 [!code-cs[csProgGuideDelegates#14](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_2.cs)]  
  
 C\# 2.0에서는 비슷한 방법을 통해 다음 예제에서와 같이 이전 예제의 선언을 작성할 수 있습니다.  
  
 [!code-cs[csProgGuideDelegates#32](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_3.cs)]  
  
 C\# 2.0 이상에서는 다음 예제에서와 같이 무명 메서드를 사용하여 [대리자](../../../csharp/language-reference/keywords/delegate.md)를 선언하고 초기화할 수도 있습니다.  
  
 [!code-cs[csProgGuideDelegates#15](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_4.cs)]  
  
 C\# 3.0 이상에서는 다음 예제에서와 같이 람다 식을 사용하여 대리자를 선언하고 인스턴스화할 수도 있습니다.  
  
 [!code-cs[csProgGuideDelegates#31](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_5.cs)]  
  
 자세한 내용은 [람다 식](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)을 참조하십시오.  
  
 다음 예제에서는 대리자 선언, 인스턴스화 및 사용에 대해 설명합니다.  `BookDB` 클래스는 설명서 데이터베이스를 관리하는 설명서 저장소 데이터베이스를 캡슐화합니다.  데이터베이스에서 모든 페이퍼백 설명서를 찾아 각 설명서에 대해 대리자를 호출하는 `ProcessPaperbackBooks` 메서드를 표시합니다.  사용되는 `delegate` 형식의 이름은 `ProcessBookDelegate`입니다.  `Test` 클래스는 이 클래스를 사용하여 페이퍼백 설명서의 평균 가격과 제목을 인쇄합니다.  
  
 대리자를 사용하면 설명서 저장소 데이터베이스와 클라이언트 코드 사이의 기능을 잘 분리할 수 있도록 도와 줍니다.  클라이언트 코드는 설명서 저장 방법이나 설명서 저장소 코드의 페이퍼백 설명서 검색 방법을 알지 못합니다.  설명서 저장소 코드는 페이퍼백 설명서를 검색한 다음 어떤 프로세스를 실행하는지 알지 못합니다.  
  
## 예제  
 [!code-cs[csProgGuideDelegates#12](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_6.cs)]  
  
## 강력한 프로그래밍  
  
-   대리자 선언  
  
     다음 문은 새 대리자 형식을 선언합니다.  
  
     [!code-cs[csProgGuideDelegates#16](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_7.cs)]  
  
     각 대리자 형식은 인수의 형식과 수 그리고 캡슐화할 수 있는 메서드 반환 값의 형식에 대해 설명합니다.  인수 형식이나 반환 값 형식의 새 집합이 필요할 때마다 새 대리자 형식을 선언해야 합니다.  
  
-   대리자 인스턴스화  
  
     대리자 형식을 선언한 후에는 대리자 개체를 만들어 특정 메서드와 결합해야 합니다.  위의 예제에서는 다음 예제와 같이 `ProcessPaperbackBooks` 메서드에 `PrintTitle` 메서드를 전달하여 이 작업을 수행합니다.  
  
     [!code-cs[csProgGuideDelegates#17](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_8.cs)]  
  
     이렇게 하면 [정적](../../../csharp/language-reference/keywords/static.md) 메서드 `Test.PrintTitle`과 결합된 새 대리자 개체가 작성됩니다.  마찬가지로 `totaller` 개체에 대한 비정적 메서드 `AddBookToTotal`은 다음 예제와 같이 전달됩니다.  
  
     [!code-cs[csProgGuideDelegates#18](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_9.cs)]  
  
     두 가지 경우 모두에서 새 대리자 개체는 `ProcessPaperbackBooks` 메서드로 전달됩니다.  
  
     대리자 개체는 변경할 수 없으므로 대리자를 만든 후에는 이와 결합된 메서드를 변경할 수 없습니다.  
  
-   대리자 호출  
  
     대리자 개체를 만들면 대리자 개체는 일반적으로 대리자를 호출할 다른 코드에 전달됩니다.  대리자 개체의 이름을 사용하여 대리자 개체를 호출하면 괄호 안의 인수가 대리자로 전달됩니다.  다음은 대리자 호출을 보여 주는 예제입니다.  
  
     [!code-cs[csProgGuideDelegates#19](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_10.cs)]  
  
     대리자는 이 예제에서와 같이 동기적으로 호출할 수도 있고 `BeginInvoke` 및 `EndInvoke` 메서드를 사용하여 비동기적으로 호출할 수도 있습니다.  
  
## 참고 항목  
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [이벤트](../../../csharp/programming-guide/events/index.md)   
 [대리자](../../../csharp/programming-guide/delegates/index.md)