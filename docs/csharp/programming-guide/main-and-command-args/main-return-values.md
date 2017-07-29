---
title: "Main() 반환 값(C# 프로그래밍 가이드)"
ms.date: 2015-07-20
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
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: a24a0db126945d122db7a0c8d373d0c91e5da8a2
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="main-return-values-c-programming-guide"></a>Main() 반환 값(C# 프로그래밍 가이드)
`Main` 메서드는 `void`를 반환할 수 있습니다.  
  
 [!code-cs[csProgGuideMain#12](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/main-return-values_1.cs)]  
  
 `int`를 반환할 수도 있습니다.  
  
 [!code-cs[csProgGuideMain#13](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/main-return-values_2.cs)]  
  
 `Main`의 반환 값을 사용하지 않는 경우 `void`를 반환하면 코드가 다소 단순해집니다. 그러나 정수를 반환하면 프로그램이 실행 파일을 호출하는 다른 프로그램 또는 스크립트에 상태 정보를 전달할 수 있습니다. 다음 예제에서는 `Main`의 반환 값을 어떻게 액세스할 수 있는지를 보여 줍니다.  
  
## <a name="example"></a>예제  
 이 예제에서는 배치 파일을 사용하여 프로그램을 실행하고 `Main` 함수의 반환 값을 테스트합니다. Windows에서 프로그램을 실행하는 경우 `Main` 함수에서 반환된 값은 `ERRORLEVEL`이라는 환경 변수에 저장됩니다. 배치 파일은 `ERRORLEVEL` 변수를 검사하여 실행 결과를 확인할 수 있습니다. 일반적으로 반환 값 0은 성공적인 실행을 나타냅니다. 다음 예제는 `Main` 함수에서 0을 반환하는 간단한 프로그램입니다. 0은 프로그램이 성공적으로 실행되었음을 나타냅니다. 프로그램을 MainReturnValTest.cs로 저장합니다.  
  
 [!code-cs[csProgGuideMain#14](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/main-return-values_3.cs)]  
  
## <a name="example"></a>예제  
 이 예제에서는 배치 파일을 사용하므로 명령 프롬프트에서 코드를 컴파일하는 것이 좋습니다. [방법: Visual Studio 명령줄에 필요한 환경 변수 설정](../../../csharp/language-reference/compiler-options/how-to-set-environment-variables-for-the-visual-studio-command-line.md)의 지침에 따라 명령줄 빌드를 사용하도록 설정하거나, **시작** 메뉴의 **Visual Studio Tools** 아래에 있는 Visual Studio 명령 프롬프트를 사용합니다. 명령 프롬프트에서 프로그램을 저장한 폴더로 이동합니다. 다음 명령은 MainReturnValTest.cs를 컴파일하고 실행 파일 MainReturnValTest.exe를 생성합니다.  
  
 `csc MainReturnValTest.cs`  
  
 다음으로 배치 파일을 만들어 MainReturnValTest.exe를 실행하고 결과를 표시합니다. 텍스트 파일에 다음 코드를 붙여넣고 MainReturnValTest.cs 및 MainReturnValTest.exe가 포함된 폴더에 `test.bat`로 저장합니다. 명령 프롬프트에서 `test`를 입력하여 배치 파일을 실행합니다.  
  
 코드에서 0을 반환하기 때문에 배치 파일이 성공했다고 보고합니다. 그러나 0이 아닌 값을 반환하도록 MainReturnValTest.cs를 변경한 다음 프로그램을 다시 컴파일하면 배치 파일의 후속 실행에서 실패했다고 보고합니다.  
  
```  
rem test.bat  
@echo off  
MainReturnValTest  
@if "%ERRORLEVEL%" == "0" goto good  
  
:fail  
    echo Execution Failed  
    echo return value = %ERRORLEVEL%  
    goto end  
  
:good  
    echo Execution succeeded  
    echo Return value = %ERRORLEVEL%  
    goto end  
  
:end  
```  
  
## <a name="sample-output"></a>샘플 출력  
 `Execution succeeded`  
  
 `Return value = 0`  
  
## <a name="see-also"></a>참고 항목  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C# 참조](../../../csharp/language-reference/index.md)   
 [Main()과 명령줄 인수](../../../csharp/programming-guide/main-and-command-args/index.md)   
 [방법: 명령줄 인수 표시](../../../csharp/programming-guide/main-and-command-args/how-to-display-command-line-arguments.md)   
 [방법: foreach를 사용하여 명령줄 인수 액세스](../../../csharp/programming-guide/main-and-command-args/how-to-access-command-line-arguments-using-foreach.md)

