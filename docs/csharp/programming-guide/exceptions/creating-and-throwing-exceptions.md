---
title: "예외 만들기 및 Throw(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "예외 catch[C#]"
  - "예외[C#], 만들기"
  - "예외[C#], throw"
  - "예외 throw[C#]"
ms.assetid: 6bbba495-a115-4c6d-90cc-1f4d7b5f39e2
caps.latest.revision: 28
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 28
---
# 예외 만들기 및 Throw(C# 프로그래밍 가이드)
예외는 프로그램을 실행하는 동안 오류가 발생한 경우 이를 알리는 데 사용됩니다.  오류를 설명하는 예외 개체가 작성된 다음 [throw](../../../csharp/language-reference/keywords/throw.md) 키워드를 사용하여 *throw*됩니다.  런타임에서는 가장 적합한 예외 처리기를 검색합니다.  
  
 프로그래머는 다음과 같은 조건 중 하나 이상이 true일 때 예외를 throw해야 합니다.  
  
-   메서드의 정의된 기능을 완료할 수 없는 경우.  
  
     메서드의 매개 변수 값이 잘못된 경우를 예로 들 수 있습니다.  
  
     [!code-cs[csProgGuideExceptions#12](../../../csharp/programming-guide/exceptions/codesnippet/csharp/creating-and-throwing-ex_1.cs)]  
  
-   개체 상태를 기준으로 개체에 대한 적절하지 않은 호출을 수행한 경우.  
  
     읽기 전용 파일에 쓰려고 하는 경우를 예로 들 수 있습니다.  개체 상태 때문에 작업을 수행할 수 없는 경우 <xref:System.InvalidOperationException>의 인스턴스나 이 클래스의 파생을 기반으로 한 개체가 throw됩니다.  다음은 <xref:System.InvalidOperationException> 개체를 throw하는 메서드의 예제입니다.  
  
     [!code-cs[csProgGuideExceptions#13](../../../csharp/programming-guide/exceptions/codesnippet/csharp/creating-and-throwing-ex_2.cs)]  
  
-   메서드에 대한 인수로 인해 예외가 발생하는 경우.  
  
     이 경우 원래 예외를 catch하고 <xref:System.ArgumentException> 인스턴스를 만들어야 합니다.  원래 예외를 <xref:System.ArgumentException>의 생성자에 <xref:System.Exception.InnerException%2A> 매개 변수로 전달해야 합니다.  
  
     [!code-cs[csProgGuideExceptions#14](../../../csharp/programming-guide/exceptions/codesnippet/csharp/creating-and-throwing-ex_3.cs)]  
  
 예외에는 <xref:System.Exception.StackTrace%2A>라는 속성이 있습니다.  이 문자열에는 현재 호출 스택에 포함된 메서드의 이름이 각 메서드에 대해 예외가 throw된 파일 이름 및 줄 번호와 함께 포함됩니다.  <xref:System.Exception.StackTrace%2A> 개체는 `throw` 문이 실행되는 지점에서 CLR\(공용 언어 런타임\)에 의해 자동으로 작성되므로 스택 추적을 시작해야 할 지점에서 예외가 throw됩니다.  
  
 모든 예외에는 <xref:System.Exception.Message%2A>라는 속성이 있습니다.  이 문자열에는 예외의 원인에 대한 설명을 설정해야 합니다.  메시지 텍스트에는 중요한 보안 정보가 포함되지 않도록 주의해야 합니다.  <xref:System.ArgumentException>에는 <xref:System.Exception.Message%2A> 이외에 <xref:System.ArgumentException.ParamName%2A>이라는 속성도 있으며, 이 속성에는 throw할 예외를 발생시킨 인수의 이름을 설정해야 합니다.  속성 setter의 경우 <xref:System.ArgumentException.ParamName%2A>은 `value`로 설정해야 합니다.  
  
 공용 메서드와 보호된 메서드 멤버는 해당 함수를 완료할 수 없을 때마다 예외를 throw해야 합니다.  throw되는 예외 클래스는 오류 조건에 맞는 가장 구체적인 예외여야 합니다.  이러한 예외는 클래스 기능의 일부로 문서화해야 하며 원본 클래스에 대한 업데이트나 파생 클래스는 역호환성을 위해 이와 동일한 동작을 유지해야 합니다.  
  
## 예외를 throw할 때 주의해야 할 사항  
 다음은 예외를 throw할 때 주의해야 할 사항입니다.  
  
-   예외는 일반적인 실행의 일부로 프로그램의 흐름을 변경하는 데 사용하면 안 됩니다.  예외는 오류를 보고하고 처리하는 용도로만 사용해야 합니다.  
  
-   예외는 반환 값이나 매개 변수로 반환하지 말고 반드시 throw해야 합니다.  
  
-   사용자가 직접 작성한 코드에서 <xref:System.Exception?displayProperty=fullName>, <xref:System.SystemException?displayProperty=fullName>, <xref:System.NullReferenceException?displayProperty=fullName> 또는 <xref:System.IndexOutOfRangeException?displayProperty=fullName>을 고의적으로 throw하면 안 됩니다.  
  
-   릴리스 모드가 아니라 디버그 모드에서 throw될 수 있는 예외는 만들면 안 됩니다.  개발 단계에서 런타임 오류를 식별하려면 Debug Assert를 대신 사용하십시오.  
  
## 예외 클래스 정의  
 프로그램에서는 앞서 언급한 경우를 제외하고 <xref:System> 네임스페이스에 미리 정의된 예외 클래스를 throw하거나 <xref:System.Exception>에서 파생된 고유한 예외 클래스를 만들 수 있습니다.  파생 클래스에서는 기본 생성자, 메시지 속성을 설정하는 생성자, <xref:System.Exception.Message%2A> 및 <xref:System.Exception.InnerException%2A> 속성을 모두 설정하는 생성자 등 적어도 네 개의 생성자를 정의해야 합니다.  네 번째 생성자는 예외를 serialize하는 데 사용됩니다.  새 예외 클래스는 serialize 가능해야 합니다.  예를 들면 다음과 같습니다.  
  
 [!code-cs[csProgGuideExceptions#15](../../../csharp/programming-guide/exceptions/codesnippet/csharp/creating-and-throwing-ex_4.cs)]  
  
 새 속성은 예외를 해결하는 데 유용한 데이터를 제공하는 경우 예외 클래스에만 추가해야 합니다.  새 속성을 파생된 예외 클래스에 추가하면 추가된 정보를 반환하도록 `ToString()`을 재정의해야 합니다.  
  
## C\# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## 참고 항목  
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [예외 및 예외 처리](../../../csharp/programming-guide/exceptions/exceptions-and-exception-handling.md)   
 [예외 계층](../Topic/Exception%20Hierarchy.md)   
 [예외 처리](../../../csharp/programming-guide/exceptions/exception-handling.md)