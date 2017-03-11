---
title: "csc.exe를 사용한 명령줄 빌드 | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "빌드[C#]"
  - "명령줄[C#]"
ms.assetid: 66e70056-dd20-453c-a9b3-507e0478b015
caps.latest.revision: 28
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 28
---
# csc.exe를 사용한 명령줄 빌드
명령 프롬프트에서 실행 파일(csc.exe)의 이름을 입력하여 C# 컴파일러를 호출할 수 있습니다.  
  
 사용 하는 경우는 **Visual Studio 명령 프롬프트** 창에서 모든 필요한 환경 변수가 설정 됩니다. Windows 7에서는 해당 창에서 액세스할 수는 **시작** Microsoft Visual Studio를 열고 메뉴 *버전*\Visual Studio Tools 폴더입니다. Windows 8에서 Visual Studio 명령 프롬프트 라고는 **v s 2012 용 개발자 명령 프롬프트**, 시작 화면에서를 검색 하 여 찾을 수 있습니다.  
  
 표준 명령 프롬프트 창을 사용하는 경우 컴퓨터의 하위 디렉터리에서 csc.exe를 호출하려면 먼저 경로를 조정해야 합니다. 또한 vsvars32.bat를 실행하여 명령줄 빌드를 지원하도록 적절한 환경 변수를 설정해야 합니다. Vsvars32.bat 찾아서 실행 하는 방법에 대 한 지침을 포함 하 여에 대 한 자세한 내용은 참조 하십시오. [하는 방법: 환경 변수 설정에 대 한 Visual Studio 명령줄](../../../csharp/language-reference/compiler-options/how-to-set-environment-variables-for-the-visual-studio-command-line.md)합니다.  
  
 만 있는 컴퓨터에서 작업 하는 경우는 [!INCLUDE[winsdklong](../../../csharp/language-reference/compiler-options/includes/winsdklong-md.md)], C# 컴파일러를 사용할 수는 **SDK 명령 프롬프트**, 에서 여는 **Microsoft.NET Framework SDK** 메뉴 옵션입니다.  
  
 또한 MSBuild를 사용하여 프로그래밍 방식으로 C# 프로그램을 빌드할 수도 있습니다. 자세한 내용은 참조 [MSBuild](/visual-studio/msbuild/msbuild1)합니다.  
  
 일반적으로 csc.exe 실행 파일에는 microsoft.net \framework 위치는\\*버전* Windows 디렉터리 아래의 폴더입니다. 이 위치는 개별 컴퓨터의 구성에 따라 다를 수 있습니다. 컴퓨터에 .NET Framework 버전이 두 개 이상 설치된 경우 이 파일의 여러 버전을 찾을 수 있습니다. 이러한 설치에 대 한 자세한 내용은 참조 [결정 하는 버전의.NET Framework가 설치](http://msdn.microsoft.com/ko-kr/1a87cc6a-1c4b-4c38-b878-faa9b3beae3c)합니다.  
  
> [!TIP]
>  Visual Studio IDE를 사용 하 여 프로젝트를 빌드할 때 표시할 수 있습니다는 **csc** 명령과 관련된 컴파일러 옵션에는 **출력** 창입니다. 이 정보를 표시 하려면의 지침에 따라 [하는 방법: 보기를 저장 하 고 빌드 로그 파일 구성](../Topic/How%20to:%20View,%20Save,%20and%20Configure%20Build%20Log%20Files.md) 로그 데이터의 자세한 정도 수준을 변경 하려면 **보통** 또는 **자세히**합니다. 프로젝트를 다시 구성한 후 검색 된 **출력** 창에 대 한 **csc** 를 C# 컴파일러 호출을 찾습니다.  
  
 **이 항목의**  
  
-   [명령줄 구문에 대 한 규칙](#vcconcommand-linebuildinganchor1)  
  
-   [샘플 명령줄](#vcconcommand-linebuildinganchor2)  
  
-   [C# 컴파일러와 c + + 컴파일러 출력의 차이점](#vcconcommand-linebuildinganchor3)  
  
##  <a name="a-namevcconcommand-linebuildinganchor1a-rules-for-command-line-syntax-for-the-c-compiler"></a><a name="vcconcommand-linebuildinganchor1"></a> C# 컴파일러 명령줄 구문에 대 한 규칙  
 C# 컴파일러는 운영 체제 명령줄에 지정 된 인수를 해석할 때 다음 규칙을 사용 합니다.  
  
-   인수를 공백이나 탭으로 구분합니다.  
  
-   캐럿 (^) 문자는 이스케이프 문자나 구분 기호로 인식할 수 없습니다. 프로그램에서 argv 배열에 전달 하기 전에 운영 체제의 명령줄 파서에서 문자를 처리 합니다.  
  
-   큰따옴표 ("string")에 포함 하는 문자열 내에 포함 된 공백에 상관 없이 하나의 인수로 해석 됩니다. 따옴표로 묶은 문자열은 인수에 포함될 수 있습니다.  
  
-   백슬래시는 큰따옴표 (\\")는 리터럴 큰따옴표 문자 (")로 해석 됩니다.  
  
-   백슬래시는 큰따옴표 바로 앞에 있지 않으면 리터럴로 해석됩니다.  
  
-   짝수 개의 백슬래시는 큰따옴표 뒤, 하나 이상의 백슬래시 argv 배열, 백슬래시 쌍 마다에 놓이고 큰따옴표는 문자열 구분 기호로 해석 됩니다.  
  
-   오는 경우 홀수 개의 백슬래시는 큰따옴표, 하나 이상의 백슬래시 argv 배열, 백슬래시 쌍 마다에 놓이고 큰따옴표는 ""는 백슬래시로 이스케이프 나머지입니다. 이렇게 하면는 리터럴 큰따옴표 (")를 argv에 추가 됩니다.  
  
##  <a name="a-namevcconcommand-linebuildinganchor2a-sample-command-lines-for-the-c-compiler"></a><a name="vcconcommand-linebuildinganchor2"></a> C# 컴파일러에 대 한 샘플 명령줄  
  
-   File.exe 생성 File.cs 컴파일되지 않습니다.  
  
    ```  
    csc File.cs   
    ```  
  
-   File.dll 생성 File.cs 컴파일되지 않습니다.  
  
    ```  
    csc /target:library File.cs  
    ```  
  
-   File.cs 컴파일하여 My.exe를 만듭니다.  
  
    ```  
    csc /out:My.exe File.cs  
    ```  
  
-   모든 C# 파일에 최적화 된 현재 디렉터리에 컴파일하고 디버그 기호를 정의 합니다. 출력은 File2.exe.  
  
    ```  
    csc /define:DEBUG /optimize /out:File2.exe *.cs  
    ```  
  
-   모든 C# 파일을 File2.dll의 디버그 버전을 현재 디렉터리에 컴파일합니다. 사용 가능한 로고와 경고가 표시 됩니다.  
  
    ```  
    csc /target:library /out:File2.dll /warn:0 /nologo /debug *.cs  
    ```  
  
-   모든 C# 파일 (DLL) Something.xyz 현재 디렉터리에서 컴파일되지 않습니다.  
  
    ```  
    csc /target:library /out:Something.xyz *.cs  
    ```  
  
##  <a name="a-namevcconcommand-linebuildinganchor3a-differences-between-c-compiler-and-c-compiler-output"></a><a name="vcconcommand-linebuildinganchor3"></a> C# 컴파일러와 c + + 컴파일러 출력의 차이점  
 C# 컴파일러를 호출하면 개체 파일(.obj)은 만들어지지 않고 출력 파일이 직접 만들어집니다. 결과적으로 C# 컴파일러에는 링커가 필요 하지 않습니다.  
  
## <a name="see-also"></a>참고 항목  
 [C# 컴파일러 옵션](../../../csharp/language-reference/compiler-options/index.md)   
 [C# 컴파일러 옵션 사전순 목록](../../../csharp/language-reference/compiler-options/listed-alphabetically.md)   
 [C# 컴파일러 옵션 범주별 목록](../../../csharp/language-reference/compiler-options/listed-by-category.md)   
 [Main ()과 명령줄 인수](../../../csharp/programming-guide/main-and-command-args/main-and-command-line-arguments.md)   
 [명령줄 인수](../../../csharp/programming-guide/main-and-command-args/command-line-arguments.md)   
 [방법: 명령줄 인수 표시](../../../csharp/programming-guide/main-and-command-args/how-to-display-command-line-arguments.md)   
 [방법: foreach를 사용 하 여 액세스 명령줄 인수](../../../csharp/programming-guide/main-and-command-args/how-to-access-command-line-arguments-using-foreach.md)   
 [Main () 반환 값](../../../csharp/programming-guide/main-and-command-args/main-return-values.md)