---
redirect_url: /dotnet/articles/csharp/programming-guide/exceptions/
caps.handback.revision: 33
---
# 예외 및 예외 처리(C# 프로그래밍 가이드)
C\# 언어에서는 프로그램 실행 중에 발생하는 예기치 않은 상황이나 예외 상황을 처리하기 위한 예외 처리 기능을 제공합니다.  예외 처리에는 성공하지 않을 수 있는 작업을 시도하고, 작업을 수행할 이유가 있는지 결정되었을 때 오류를 처리하고, 나중에 리소스를 정리하기 위한 `try`, `catch` 및 `finally` 키워드가 사용됩니다.  예외는 CLR\(공용 언어 런타임\), .NET Framework나 타사 라이브러리 또는 응용 프로그램 코드에서 발생할 수 있습니다.  이러한 예외는 `throw` 키워드를 사용하여 생성됩니다.  
  
 대부분의 경우 예외는 코드에서 직접 호출한 메서드가 아니라 호출 스택 아래쪽에 있는 다른 메서드에서 throw됩니다.  이런 경우 CLR에서는 스택을 해제하여 특정 예외 형식에 대한 `catch` 블록이 있는 메서드를 찾고, 찾은 경우 첫 번째 `catch` 블록을 실행합니다.  호출 스택에서 해당하는 `catch` 블록을 찾지 못한 경우 CLR은 프로세스를 종료하고 사용자에게 메시지를 표시합니다.  
  
 이 예제의 메서드에서는 0으로 나누기 여부를 테스트하고 오류를 catch합니다.  예외를 처리하지 않는다면 이 프로그램은 **DivideByZeroException was unhandled** 오류 메시지와 함께 종료됩니다.  
  
 [!code-cs[csProgGuideExceptions#18](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/exceptions-and-exception-handling_1.cs)]  
  
## 예외 개요  
 예외에는 다음과 같은 속성이 있습니다.  
  
-   예외는 모두 궁극적으로 `System.Exception`에서 파생되는 형식입니다.  
  
-   예외가 throw될 가능성이 있는 문 주위에 `try` 블록을 추가합니다.  
  
-   `try` 블록 내에서 예외가 발생한 경우 호출 스택에 있는 첫 번째 관련 예외 처리기로 제어 흐름이 이동합니다.  C\#에서 예외 처리기를 정의하는 데는 `catch` 키워드가 사용됩니다.  
  
-   발생한 예외에 대한 예외 처리기가 없으면 프로그램의 실행이 중지되고 오류 메시지가 나타납니다.  
  
-   예외를 처리할 수 없는 경우 예외를 catch하지 않고 응용 프로그램을 알려진 상태로 두어야 합니다.  `System.Exception`을 catch한 경우 `catch` 블록 끝에서 `throw` 키워드를 사용하여 다시 throw합니다.  
  
-   `catch` 블록에 예외 변수가 정의된 경우 이를 통해 발생한 예외 형식에 대한 자세한 정보를 확인할 수 있습니다.  
  
-   `throw` 키워드를 사용하면 프로그램에서 예외를 명시적으로 생성할 수 있습니다.  
  
-   예외 개체에는 호출 스택의 상태와 오류를 설명하는 텍스트를 비롯하여 오류에 대한 자세한 정보가 포함됩니다.  
  
-   `finally` 블록의 코드는 예외가 throw되어도 실행되므로  `finally` 블록을 사용하여 리소스를 해제합니다. 예를 들어, `try` 블록에 열려 있는 스트림이나 파일을 닫습니다.  
  
-   .NET Framework의 관리되는 예외는 Win32 구조적 예외 처리 메커니즘을 기반으로 구현됩니다.  자세한 내용은 [구조적 예외 처리](/visual-cpp/cpp/structured-exception-handling-c-cpp) 및 [A Crash Course on the Depths of Win32 Structured Exception Handling](http://go.microsoft.com/fwlink/?LinkId=119654)을 참조하십시오.  
  
## 관련 단원  
 예외와 예외 처리에 대한 자세한 내용은 다음 항목을 참조하십시오.  
  
-   [예외 사용](../../../csharp/programming-guide/exceptions/using-exceptions.md)  
  
-   [예외 처리](../../../csharp/programming-guide/exceptions/exception-handling.md)  
  
-   [예외 만들기 및 Throw](../../../csharp/programming-guide/exceptions/creating-and-throwing-exceptions.md)  
  
-   [컴파일러 생성 예외](../../../csharp/programming-guide/exceptions/compiler-generated-exceptions.md)  
  
-   [방법: try\/catch를 사용하여 예외 처리](../../../csharp/programming-guide/exceptions/how-to-handle-an-exception-using-try-catch.md)  
  
-   [방법: finally를 사용하여 정리 코드 실행](../../../csharp/programming-guide/exceptions/how-to-execute-cleanup-code-using-finally.md)  
  
## C\# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## 참고 항목  
 <xref:System.SystemException>   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C\# 키워드](../../../csharp/language-reference/keywords/index.md)   
 [throw](../../../csharp/language-reference/keywords/throw.md)   
 [try\-catch](../../../csharp/language-reference/keywords/try-catch.md)   
 [try\-finally](../../../csharp/language-reference/keywords/try-finally.md)   
 [try\-catch\-finally](../../../csharp/language-reference/keywords/try-catch-finally.md)   
 [예외](../Topic/Handling%20and%20Throwing%20Exceptions.md)   
 [예외 계층](../Topic/Exception%20Hierarchy.md)   
 [안정적인.NET 코드 작성](http://go.microsoft.com/fwlink/?LinkId=112400)   
 [특정 예외에 대해 미니](http://go.microsoft.com/fwlink/?LinkId=112408)