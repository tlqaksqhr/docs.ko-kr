---
title: "Main() 반환 값(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Main 메서드[C#], 반환 값"
ms.assetid: c2f5a1d8-1676-4bea-bc7e-44a97e72d5bc
caps.latest.revision: 20
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 20
---
# Main() 반환 값(C# 프로그래밍 가이드)
`Main` 메서드는 `void`를 반환할 수 있습니다.  
  
 [!code-cs[csProgGuideMain#12](../../../csharp/programming-guide/inside-a-program/codesnippet/csharp/main-return-values_1.cs)]  
  
 또는 `int`를 반환할 수 있습니다.  
  
 [!code-cs[csProgGuideMain#13](../../../csharp/programming-guide/inside-a-program/codesnippet/csharp/main-return-values_2.cs)]  
  
 `Main`의 반환 값이 사용되지 않는 경우 `void`를 반환하면 코드가 좀더 단순해집니다.  그러나 정수를 반환하면 프로그램에서 실행 파일을 호출하는 스크립트나 기타 프로그램으로 상태 정보를 전달할 수 있습니다.  다음 예제에서는 `Main`의 반환 값에 액세스하는 방법을 보여 줍니다.  
  
## 예제  
 이 예제에서는 배치 파일을 사용하여 프로그램을 실행하고 `Main` 함수의 반환 값을 테스트합니다.  프로그램이 Windows에서 실행되면 `Main` 함수의 모든 반환 값은 `ERRORLEVEL`이라는 환경 변수에 저장됩니다.  배치 파일에서는 `ERRORLEVEL` 변수를 검사하여 실행 결과를 확인할 수 있습니다.  일반적으로 반환 값이 0이면 실행이 성공적임을 나타냅니다.  다음 예제는 `Main` 함수에서 0을 반환하는 간단한 프로그램입니다.  0은 프로그램이 성공적으로 실행되었음을 나타냅니다.  프로그램을 MainReturnValTest.cs로 저장합니다.  
  
 [!code-cs[csProgGuideMain#14](../../../csharp/programming-guide/inside-a-program/codesnippet/csharp/main-return-values_3.cs)]  
  
## 예제  
 이 예제에서는 배치 파일을 사용하기 때문에 명령 프롬프트에서 코드를 컴파일하는 것이 가장 좋습니다.  [How to: Set Environment Variables for the Visual Studio Command Line](../../../csharp/language-reference/compiler-options/how-to-set-environment-variables-for-the-visual-studio-command-line.md)의 지침에 따라 명령줄 빌드를 사용하도록 설정하거나, **시작** 메뉴의 **Visual Studio Tools**에서 사용 가능한 Visual Studio 명령 프롬프트를 사용합니다.  명령 프롬프트에서 프로그램을 저장한 폴더로 이동합니다.  다음 명령은 MainReturnValTest.cs를 컴파일하고 실행 파일 MainReturnValTest.exe를 생성합니다.  
  
 `csc MainReturnValTest.cs`  
  
 그런 다음 MainReturnValTest.exe를 실행하고 결과를 표시하는 배치 파일을 만듭니다.  텍스트 파일에 다음 코드를 붙여 넣고, MainReturnValTest.cs 및 MainReturnValTest.exe가 포함된 폴더에 해당 파일을 `test.bat`로 저장합니다.  명령 프롬프트에 `test`를 입력하여 배치 파일을 실행합니다.  
  
 코드가 0을 반환하므로 배치 파일에서 성공을 보고합니다.  그러나 0이 아닌 값을 반환하도록 MainReturnValTest.cs를 변경한 후 프로그램을 다시 컴파일하면 이후에 배치 파일을 실행할 때 실패가 보고됩니다.  
  
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
  
## 샘플 출력  
 `Execution succeeded`  
  
 `Return value = 0`  
  
## 참고 항목  
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [Main\(\)과 명령줄 인수](../../../csharp/programming-guide/main-and-command-args/main-and-command-line-arguments.md)   
 [방법: 명령줄 인수 표시](../../../csharp/programming-guide/main-and-command-args/how-to-display-command-line-arguments.md)   
 [방법: foreach를 사용하여 명령줄 인수 액세스](../../../csharp/programming-guide/main-and-command-args/how-to-access-command-line-arguments-using-foreach.md)