---
title: "try-catch(C# 참조) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "try"
  - "try_CSharpKeyword"
  - "catch"
  - "catch_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "catch 키워드[C#]"
  - "try-catch 문[C#]"
ms.assetid: cb5503c7-bfa1-4610-8fc2-ddcd2e84c438
caps.latest.revision: 45
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 45
---
# try-catch(C# 참조)
try-catch 문은 `try` 블록에 이어 서로 다른 예외에 대한 처리기를 지정하는 하나 이상의 `catch` 절로 구성됩니다.  
  
## <a name="remarks"></a>설명  
 예외가 throw되면 CLR(공용 언어 런타임)에서는 이 예외를 처리하는 `catch` 문을 검색합니다. 현재 실행 중인 메서드에 `catch` 블록이 포함되지 않으면 CLR에서는 현재 메서드를 호출한 메서드 등에서 호출 스택까지 확인합니다. `catch` 블록을 찾을 수 없으면 CLR에서는 처리되지 않은 예외 메시지를 사용자에게 표시하고 프로그램의 예외를 중지합니다.  
  
 `try` 블록에는 예외를 가져올 수 있는 보호된 코드가 포함됩니다. 블록은 예외가 throw되거나 성공적으로 완료될 때까지 실행됩니다. 다음 예를 들어 캐스팅 하려고는 `null` 발생 시키는 개체는 <xref:System.NullReferenceException> 예외:  
  
```c#  
object o2 = null;  
try  
{  
    int i2 = (int)o2;   // Error  
}  
```  
  
 `catch` 절은 예외 형식을 catch하는 인수 없이 사용할 수 있지만 이 사용은 권장되지 않습니다. 일반적으로 복구하는 방법을 알고 있는 예외만 catch해야 합니다. 파생 된 개체 인수를 항상 지정 해야 따라서 <xref:System.Exception?displayProperty=fullName> 예:  
  
```c#  
catch (InvalidCastException e)   
{  
}  
```  
  
 같은 try-catch 문에서 특정 `catch` 절을 두 개 이상 사용할 수 있습니다. 이 경우 `catch` 절은 순서대로 검사되므로 `catch` 절의 순서가 중요합니다. 더 구체적인 예외를 덜 구체적인 예외보다 먼저 catch합니다. 나중에 나타나는 블록에 도달할 수 없도록 catch 블록 순서를 지정하면 컴파일러에서 오류가 발생합니다.  
  
 `catch` 인수를 사용하여 처리할 예외를 필터링할 수 있습니다.  예외를 추가로 검사하는 조건자 식을 사용하여 예외를 처리할지 결정할 수도 있습니다.  조건자 식에서 false를 반환하면 처리기 검색이 계속됩니다.  
  
```c#  
catch (ArgumentException e) when (e.ParamName == “…”)  
{  
}  
```  
  
 필터 덕분에 스택이 손상되지 않으므로 예외 필터는 catch하고 다시 throw하는 것이 좋습니다(아래 내용 참조).  나중에 나타나는 처리기가 스택을 덤프하면 예외가 다시 throw된 마지막 위치가 아니라 예외가 원래 발생한 위치를 확인할 수 있습니다.  예외 필터 식의 일반적으로 사용법은 로깅입니다.  로그에도 출력되는 항상 false를 반환하는 조건자 함수를 만들 수 있고, 예외를 처리하고 다시 throw할 필요 없이 진행되는 대로 예외를 기록할 수 있습니다.  
  
 A [throw](../../../csharp/language-reference/keywords/throw.md) 문을에서 사용할 수는 `catch` 블록에서 포착 되는 예외를 다시 throw 하는 `catch` 문. 다음 예제에서 소스 정보를 추출는 <xref:System.IO.IOException> 예외는 부모 메서드는 예외를 throw 합니다.  
  
```c#  
catch (FileNotFoundException e)  
{  
    // FileNotFoundExceptions are handled here.  
}  
catch (IOException e)  
{  
    // Extract some information from this exception, and then   
    // throw it to the parent method.  
    whenDo not initialize (e.Source != null)  
        Console.WriteLine("IOException source: {0}", e.Source);  
    throw;  
}  
```  
  
 하나의 예외를 catch하고 다른 예외를 throw할 수 있습니다. 이 작업을 할 때 다음 예제와 같이 내부 예외로 catch한 예외를 지정합니다.  
  
```c#  
catch (InvalidCastException e)   
{  
    // Perform some action here, and then throw a new exception.  
    throw new YourCustomException("Put your error message here.", e);  
}  
```  
  
 다음 예제와 같이 지정된 조건이 true이면 예외를 다시 throw할 수도 있습니다.  
  
```c#  
  
catch (InvalidCastException e)  
{  
    if (e.Data == null)  
    {  
        throw;  
    }  
    else  
    {  
        // Take some action.  
    }  
 }  
```  
  
 `try` 블록 내부에서 선언된 변수만 초기화합니다. 그렇지 않으면 블록의 예외가 완료되기 전에 다른 예외가 발생할 수 있습니다. 예를 들어 다음 코드 예제에서 `n` 변수는 `try` 블록 내부에서 초기화됩니다. `Write(n)` 문의 `try` 블록 외부에서 이 변수를 사용하려고 하면 컴파일러 오류가 발생합니다.  
  
```c#  
static void Main()   
{  
    int n;  
    try   
    {  
        // Do not initialize this variable here.  
        n = 123;  
    }  
    catch  
    {  
    }  
    // Error: Use of unassigned local variable 'n'.  
    Console.Write(n);  
}  
```  
  
 Catch 하는 방법에 대 한 자세한 내용은 참조 [try – catch – finally](../../../csharp/language-reference/keywords/try-catch-finally.md)합니다.  
  
## <a name="exceptions-in-async-methods"></a>비동기 메서드의 예외  
 비동기 메서드는으로 표시는 [비동기](../../../csharp/language-reference/keywords/async.md) 한정자 일반적으로 하나를 포함 하 고 식 또는 문으로 await 자세히 또는 합니다. Await 식이 적용 되는 [await](../../../csharp/language-reference/keywords/await.md) 연산자를 한 <xref:System.Threading.Tasks.Task> 또는 <xref:System.Threading.Tasks.Task%601>합니다.  
  
 컨트롤이 비동기 메서드의 `await`에 도달하면 대기 중인 작업이 완료될 때까지 메서드의 진행이 일시 중단됩니다. 작업이 완료되면 메서드가 실행이 다시 시작될 수 있습니다. 자세한 내용은 참조 [Async 및 Await를 사용한 비동기 프로그래밍](../Topic/Asynchronous%20Programming%20with%20Async%20and%20Await%20\(C%23%20and%20Visual%20Basic\).md) 및 [비동기 프로그램의 제어 흐름](../Topic/Control%20Flow%20in%20Async%20Programs%20\(C%23%20and%20Visual%20Basic\).md)합니다.  
  
 `await`가 적용되는 완료된 작업은 작업을 반환하는 메서드의 처리되지 않은 예외로 인해 오류 상태에 있을 수 있습니다. 작업을 기다리면 예외가 throw됩니다. 작업을 반환하는 비동기 프로세스가 취소되면 작업이 취소됨 상태로 종료될 수도 있습니다. 취소된 작업을 기다리면 `OperationCanceledException`이 throw됩니다. 비동기 프로세스를 취소 하는 방법에 대 한 자세한 내용은 참조 [비동기 응용 프로그램 미세 조정](../Topic/Fine-Tuning%20Your%20Async%20Application%20\(C%23%20and%20Visual%20Basic\).md)합니다.  
  
 예외를 catch하려면 `try` 블록에서 작업을 기다리고 연결된 `catch` 블록에서 예외를 catch합니다. 예제에 대해서는 "예제" 섹션을 참조하세요.  
  
 대기 중인 비동기 메서드에서 여러 예외가 발생했기 때문에 작업이 오류 상태에 있을 수 있습니다. 예를 들어 작업에 대 한 호출의 결과 수 <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName>합니다. 작업을 기다릴 때 예외 중 하나만 catch되고 catch될 예외를 예상할 수 없습니다. 예제에 대해서는 "예제" 섹션을 참조하세요.  
  
## <a name="example"></a>예제  
 다음 예제에서 `try` 블록에는 예외를 가져올 수 있는 `ProcessString` 메서드에 대한 호출이 포함됩니다. `catch` 절에는 화면에 메시지만 표시하는 예외 처리기가 포함됩니다. `throw` 문이 `MyMethod` 내부에서 호출되면 시스템에서는 `catch` 문을 검색하고 메시지 `Exception caught`를 표시합니다.  
  
 [!code-cs[csrefKeywordsExceptions#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/try-catch_1.cs)]  
  
## <a name="example"></a>예제  
 다음 예제에서는 두 catch 블록이 사용되고 먼저 나오는 가장 구체적인 예외가 catch됩니다.  
  
 가장 덜 구체적인 예외를 catch하려면 `ProcessString`의 throw 문을 `throw new Exception()` 문으로 바꿔야 합니다.  
  
 가장 덜 구체적인 catch 블록을 예제에 첫 번째로 배치하면 다음 오류 메시지가 표시됩니다. `A previous catch clause already catches all exceptions of this or a super type ('System.Exception')`.  
  
 [!code-cs[csrefKeywordsExceptions#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/try-catch_2.cs)]  
  
## <a name="example"></a>예제  
 다음 예제에서는 비동기 메서드에 대한 예외 처리를 보여 줍니다. 비동기 작업에서 throw하는 예외를 catch하려면 `try` 블록에 `await` 식을 배치하고 `catch` 블록에서 예외를 catch합니다.  
  
 예제에서 `throw new Exception` 줄의 주석 처리를 제거하여 예외 처리를 보여 줍니다. 작업의 `IsFaulted` 속성이 `True`로 설정되고, 작업의 `Exception.InnerException` 속성이 예외로 설정되고, 예외가 `catch` 블록에서 catch됩니다.  
  
 `throw new OperationCancelledException` 줄의 주석 처리를 제거하여 비동기 프로세스를 취소할 수 있을 때 발생하는 동작을 보여 줍니다. 작업의 `IsCanceled` 속성이 `true`로 설정되고, 예외가 `catch` 블록에서 catch됩니다. 이 예제에 적용되지 않는 몇몇 조건에서는 작업의 `IsFaulted` 속성이 `true`로 설정되고 `IsCanceled`가 `false`로 설정됩니다.  
  
 [!code-cs[csAsyncExceptions#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/try-catch_3.cs)]  
  
## <a name="example"></a>예제  
 다음 예제에서는 여러 작업에서 여러 예외가 발생할 수 있는 경우 예외 처리를 보여 줍니다. `try` 블록에 대 한 호출에서 반환 되는 작업을 기다리는 <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName>합니다. WhenAll이 적용된 작업 세 개가 완료되면 작업이 완료됩니다.  
  
 세 작업에서 각각 예외가 발생합니다. `catch` 블록에 있는 예외를 통해 반복 하는 `Exception.InnerExceptions` 속성에서 반환 된 작업의 <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName>합니다.  
  
 [!code-cs[csAsyncExceptions#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/try-catch_4.cs)]  
  
## <a name="c-language-specification"></a>C# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [C# 참조](../../../csharp/language-reference/index.md)   
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C# 키워드](../../../csharp/language-reference/keywords/index.md)   
 [try, throw 및 catch 문 (c + +)](/visual-cpp/cpp/try-throw-and-catch-statements-cpp)   
 [예외 처리문](../../../csharp/language-reference/keywords/exception-handling-statements.md)   
 [throw](../../../csharp/language-reference/keywords/throw.md)   
 [try-finally-](../../../csharp/language-reference/keywords/try-finally.md)   
 [방법: 명시적으로 예외 Throw](../Topic/How%20to:%20Explicitly%20Throw%20Exceptions.md)