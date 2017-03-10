---
redirect_url: /dotnet/articles/csharp/programming-guide/main-and-command-args/
caps.handback.revision: 30
---
# Main()과 명령줄 인수(C# 프로그래밍 가이드)
C\# 콘솔 응용 프로그램이나 Windows 응용 프로그램의 진입점은  `Main` 메서드입니다.  라이브러리와 서비스에서는 진입점으로 `Main` 메서드가 필요하지 않습니다.  응용 프로그램이 시작될 때 `Main` 메서드는 처음으로 호출되는 메서드입니다.  
  
 C\# 프로그램에는 진입점이 하나만 있을 수 있습니다.  `Main` 메서드가 있는 클래스가 두 개 이상 있는 경우 **\/main** 컴파일러 옵션을 통해 진입점으로 사용할 `Main` 메서드를 지정하여 프로그램을 컴파일해야 합니다.  자세한 내용은 [\/main \(Specify Location of Main Method\)](../../../csharp/language-reference/compiler-options/main-compiler-option.md)을 참조하십시오.  
  
 [!code-cs[csProgGuideMain#17](../../../csharp/programming-guide/inside-a-program/codesnippet/csharp/main-and-command-line-ar_1.cs)]  
  
## 개요  
  
-   `Main` 메서드는 프로그램 제어가 시작되고 끝나는 .exe 프로그램의 진입점입니다.  
  
-   `Main`은 클래스 또는 구조체 내부에 선언됩니다.  `Main`있어야  [정적](../../../csharp/language-reference/keywords/static.md) 않아야 하 고  [공용](../../../csharp/language-reference/keywords/public.md).  이전 예제에서 이 메서드에는 기본 액세스 수준인 [private](../../../csharp/language-reference/keywords/private.md)이 지정되었습니다. 이 메서드의 바깥쪽 클래스나 구조체는 정적일 필요가 없습니다.  
  
-   `Main`은 `void` 또는 `int` 반환 형식일 수 있습니다.  
  
-   `Main` 메서드는 명령줄 인수를 포함하는 `string[]` 매개 변수가 있거나 없는 상태로 선언할 수 있습니다.  [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs-md.md)]를 사용하여 Windows Forms 응용 프로그램을 만드는 경우 수동으로 매개 변수를 추가하거나 <xref:System.Environment> 클래스를 사용하여 명령줄 인수를 가져올 수 있습니다.  매개 변수 인덱스 0 명령줄 인수로 읽혀집니다. C 및 c \+ \+와 달리 프로그램의 이름은 첫 번째 명령줄 인수로 처리 되지 않습니다.  
  
## 단원 내용  
  
-   [명령줄 인수](../../../csharp/programming-guide/main-and-command-args/command-line-arguments.md)  
  
-   [방법: 명령줄 인수 표시](../../../csharp/programming-guide/main-and-command-args/how-to-display-command-line-arguments.md)  
  
-   [방법: foreach를 사용하여 명령줄 인수 액세스](../../../csharp/programming-guide/main-and-command-args/how-to-access-command-line-arguments-using-foreach.md)  
  
-   [Main\(\) 반환 값](../../../csharp/programming-guide/main-and-command-args/main-return-values.md)  
  
## C\# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## 참고 항목  
 [Command\-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [메서드](../../../csharp/programming-guide/classes-and-structs/methods.md)   
 [C\# 프로그램 내부](../../../csharp/programming-guide/inside-a-program/index.md)   
 [\<paveover\>C\# Sample Applications](http://msdn.microsoft.com/ko-kr/9a9d7aaa-51d3-4224-b564-95409b0f3e15)