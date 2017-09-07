---
title: "Main() 반환 값(C# 프로그래밍 가이드)"
ms.date: 2017-08-02
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- Main method [C#], return values
ms.assetid: c2f5a1d8-1676-4bea-bc7e-44a97e72d5bc
caps.latest.revision: 20
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: d019d1c5757a961c03439d756e808ae13fd8a67b
ms.openlocfilehash: 50943bdd0b7726145797faf82719537a388dad89
ms.contentlocale: ko-kr
ms.lasthandoff: 08/03/2017

---

# <a name="main-return-values-c-programming-guide"></a>Main() 반환 값(C# 프로그래밍 가이드)

`Main` 메서드는 `void`를 반환할 수 있습니다.

[!code-cs[csProgGuideMain#12](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/main-return-values_1.cs)]

`int`를 반환할 수도 있습니다.

[!code-cs[csProgGuideMain#13](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/main-return-values_2.cs)]

`Main`의 반환 값을 사용하지 않는 경우 `void`를 반환하면 코드가 다소 단순해집니다. 그러나 정수를 반환하면 프로그램이 실행 파일을 호출하는 다른 프로그램 또는 스크립트에 상태 정보를 전달할 수 있습니다. `Main`의 반환 값은 프로세스에 대한 종료 코드로 처리됩니다. 다음 예제에서는 `Main`의 반환 값을 어떻게 액세스할 수 있는지를 보여 줍니다.

## <a name="example"></a>예제

이 예제에서는 [.NET Core](../../../core/index.md) 명령줄 도구를 사용합니다. .NET Core 명령줄 도구에 대해 잘 모르는 경우 이 [시작 항목](../../../core/tutorials/using-with-xplat-cli.md)에서 알아볼 수 있습니다.

*program.cs* 에서 `Main` 메서드를 다음과 같이 수정합니다.

[!code-cs[csProgGuideMain#14](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/main-return-values_3.cs)]

Windows에서 프로그램을 실행하는 경우 `Main` 함수에서 반환된 값은 환경 변수에 저장됩니다. 이 환경 변수는 배치 파일에서 `ERRORLEVEL`을 사용하거나 PowerShell에서 `$LastExitCode`를 사용하여 검색할 수 있습니다.

[dotnet CLI](../../../core/tools/dotnet.md) `dotnet build` 명령을 사용하여 응용 프로그램을 빌드할 수 있습니다.

다음으로 응용 프로그램을 실행하고 결과를 표시하는 PowerShell 스크립트를 만듭니다. 다음 코드를 텍스트 파일에 붙여넣고 이 파일을 프로젝트가 포함된 폴더에 `test.ps1`로 저장합니다. PowerShell 프롬프트에 `test.ps1`을 입력하여 PowerShell 스크립트를 실행합니다.

코드에서 0을 반환하기 때문에 배치 파일이 성공했다고 보고합니다. 그러나 0이 아닌 값을 반환하도록 MainReturnValTest.cs를 변경한 다음 프로그램을 다시 컴파일하면 다음에 PowerShell 스크립트를 실행할 때 오류가 보고됩니다.

```powershell
dotnet run
if ($LastExitCode -eq 0) {
    Write-Host "Execution succeeded"
} else
{
    Write-Host "Execution Failed"
}
Write-Host "Return value = " $LastExitCode
```

## <a name="sample-output"></a>샘플 출력

```txt
Execution succeeded
Return value = 0
```

## <a name="async-main-return-values"></a>비동기 Main 반환 값

비동기 Main 반환 값은 `Main`에서 비동기 메서드를 호출하는 데 필요한 상용구 코드를 컴파일러에서 생성하는 코드로 이동합니다. 기존에는 이 구문을 작성하여 비동기 코드를 호출하고 비동기 작업이 완료될 때까지 프로그램이 실행되는지 확인해야 했습니다.

```csharp
public static void Main()
{
    AsyncConsoleWork().GetAwaiter().GetResult();
}

private static async Task<int> AsyncConsoleWork()
{
    // Main body here
    return 0;
}
```

이제는 이 구문을 다음으로 바꿀 수 있습니다.

[!code-csharp[AsyncMain](../../../../samples/snippets/csharp/main-arguments/program.cs#AsyncMain)]

새 구문의 장점은 컴파일러에서 항상 올바른 코드를 생성한다는 것입니다.

## <a name="compiler-generated-code"></a>컴파일러 생성 코드

응용 프로그램 진입점에서 `Task` 또는 `Task<int>`를 반환하는 경우 컴파일러는 응용 프로그램 코드에서 선언된 진입점 메서드를 호출하는 새 진입점을 생성합니다. 이 진입점이 `$GeneratedMain`이라고 가정하면 컴파일러는 이러한 진입점에 대해 다음 코드를 생성합니다.

- `static Task Main()` - 컴파일러에서 `private static void $GeneratedMain() => Main().GetAwaiter().GetResult();`에 해당하는 코드를 내보냅니다.
- `static Task Main(string[])` - 컴파일러에서 `private static void $GeneratedMain(string[] args) => Main(args).GetAwaiter().GetResult();`에 해당하는 코드를 내보냅니다.
- `static Task<int> Main()` - 컴파일러에서 `private static int $GeneratedMain() => Main().GetAwaiter().GetResult();`에 해당하는 코드를 내보냅니다.
- `static Task<int> Main(string[])` - 컴파일러에서 `private static int $GeneratedMain(string[] args) => Main(args).GetAwaiter().GetResult();`에 해당하는 코드를 내보냅니다.

> [!NOTE]
>예제에서 `Main` 메서드에 `async` 한정자를 사용하더라도 컴파일러는 동일한 코드를 생성합니다.

## <a name="see-also"></a>참고 항목
[C# 프로그래밍 가이드](../../programming-guide/index.md)
[C# 참조](../index.md)
[Main()과 명령줄 인수](index.md)
[방법: 명령줄 인수 표시](../../programming-guide/main-and-command-args/how-to-display-command-line-arguments.md)
[방법: foreach를 사용하여 명령줄 인수 액세스](../../programming-guide/main-and-command-args/how-to-access-command-line-arguments-using-foreach.md)

