---
title: "예외 사용(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "예외 처리[C#], 예외 처리 정보"
  - "예외[C#], 예외 정보"
ms.assetid: 71472c62-320a-470a-97d2-67995180389d
caps.latest.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 15
---
# 예외 사용(C# 프로그래밍 가이드)
C\#의 경우 런타임에 발생하는 프로그램 오류는 예외라는 메커니즘을 사용하여 프로그램을 통해 전파됩니다.  예외는 오류를 발견한 코드에서 throw되고 오류를 수정할 수 있는 코드에서 catch됩니다.  예외는 .NET Framework CLR\(공용 언어 런타임\)을 통해 throw되거나 프로그램의 코드를 통해 throw될 수 있습니다.  throw된 예외는 예외에 대한 `catch` 문을 만날 때까지 호출 스택을 거슬러 올라가며 전파됩니다.  catch되지 않은 예외는 대화 상자를 표시하는 시스템에서 제공하는 제네릭 예외 처리기를 사용하여 처리됩니다.  
  
 예외를 나타내는 데는 <xref:System.Exception>에서 파생된 클래스가 사용됩니다.  예외의 형식을 식별하는 이 클래스에는 예외에 대한 자세한 정보가 있는 속성이 들어 있습니다.  예외를 throw하려면 예외 파생 클래스의 인스턴스를 만들고 선택적으로 예외의 속성을 구성한 다음 `throw` 키워드를 사용하여 개체를 throw해야 합니다.  예를 들면 다음과 같습니다.  
  
 [!code-cs[csProgGuideExceptions#1](../../../csharp/programming-guide/exceptions/codesnippet/csharp/using-exceptions_1.cs)]  
  
 예외가 throw되면 런타임에서는 현재 문이 `try` 블록 내에 있는지 검사합니다.  현재 문이 이 블록 내에 있으면 `try` 블록과 관련된 `catch` 블록을 모두 검사하여 예외를 catch할 수 있는지 확인합니다.  `Catch` 블록은 일반적으로 예외 형식을 지정합니다. `catch` 블록의 형식이 예외의 형식과 동일하거나 예외의 기본 클래스와 동일한 형식이면 `catch` 블록에서 메서드를 처리할 수 있습니다.  예를 들면 다음과 같습니다.  
  
 [!code-cs[csProgGuideExceptions#2](../../../csharp/programming-guide/exceptions/codesnippet/csharp/using-exceptions_2.cs)]  
  
 예외를 throw하는 문이 `try` 블록 안에 있지 않거나 이를 포함하는 `try` 블록에 대응하는 `catch` 블록이 없는 경우 런타임에서는 `catch` 블록과 `try` 문을 찾기 위해 호출 메서드를 검사합니다.  런타임은 호출 스택을 거슬러 올라가며 호환되는 `catch` 블록을 계속 찾습니다.  `catch` 블록을 찾아 실행한 후에는 제어가 `catch` 블록 다음에 있는 문으로 전달됩니다.  
  
 `try` 문에는 `catch` 블록이 여러 개 포함될 수 있습니다.  예외를 처리할 수 있는 첫 번째 `catch` 문이 실행되고 이후의 `catch` 문은 호환되는 문이어도 모두 무시됩니다.  따라서, 항상 가장 구체적인\(또는 가장 많이 파생되는\) 경우부터 가장 일반적인 경우의 순서로 catch 블록을 지정해야 합니다.  예를 들면 다음과 같습니다.  
  
 [!code-cs[csProgGuideExceptions#3](../../../csharp/programming-guide/exceptions/codesnippet/csharp/using-exceptions_3.cs)]  
  
 `catch` 블록을 실행하기 전에 런타임은 `finally` 블록을 확인합니다.  `Finally` 블록을 사용하면 취소된 `try` 블록에서 남겨질 수 있는 모호한 상태를 모두 정리할 수 있고 런타임에 가비지 수집기가 개체를 종결하기를 기다리지 않고도 그래픽 핸들, 데이터베이스 연결, 파일 스트림 등의 외부 리소스를 해제할 수 있습니다.  예를 들면 다음과 같습니다.  
  
 [!code-cs[csProgGuideExceptions#4](../../../csharp/programming-guide/exceptions/codesnippet/csharp/using-exceptions_4.cs)]  
  
 `WriteByte()`에서 예외를 throw한 경우 `file.Close()`를 호출하지 않으면 파일을 다시 열려고 하는 두 번째 `try` 블록의 코드가 실패하고 해당 파일은 잠금 상태로 유지됩니다.  `finally` 블록은 예외가 throw되는지 여부와 상관없이 실행되므로 위 예제에서 `finally` 블록을 사용하면 파일을 올바르게 닫고 오류를 방지할 수 있습니다.  
  
 예외가 throw된 후에 호출 스택에서 호환되는 `catch` 블록을 찾지 못하면 다음 세 가지 결과 중 하나가 발생합니다.  
  
-   예외가 소멸자 내에 있는 경우에는 소멸자가 취소되고 기본 생성자가 있으면 이 생성자가 호출됩니다.  
  
-   호출 스택에 정적 생성자 또는 정적 필드 이니셜라이저가 있는 경우에는 원래 예외가 새 예외의 <xref:System.Exception.InnerException%2A> 속성에 할당된 상태로 <xref:System.TypeInitializationException>이 throw됩니다.  
  
-   스레드의 시작 부분에 도달하면 스레드가 종료됩니다.  
  
## 참고 항목  
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [예외 및 예외 처리](../../../csharp/programming-guide/exceptions/exceptions-and-exception-handling.md)