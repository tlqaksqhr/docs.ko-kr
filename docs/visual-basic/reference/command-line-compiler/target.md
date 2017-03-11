---
title: "/target (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "target compiler options [Visual Basic]"
  - "-target compiler options [Visual Basic]"
  - "/target compiler options [Visual Basic]"
ms.assetid: e0954147-548b-461f-9c4b-a8f88845616c
caps.latest.revision: 29
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 29
---
# /target (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

컴파일러 출력 형식을 지정합니다.  
  
## 구문  
  
```  
/target:{exe | library | module | winexe | appcontainerexe | winmdobj}  
```  
  
## 설명  
 다음 표에서는 `/target` 옵션의 효과를 요약합니다.  
  
|**옵션**|**동작**|  
|------------|------------|  
|`/target:exe`|컴파일러가 실행 가능한 콘솔 응용 프로그램을 만들도록 합니다.<br /><br /> 이 옵션은 `/target` 옵션을 지정하지 않을 경우 기본 옵션으로 사용됩니다.  확장명이 .exe인 실행 파일이 만들어집니다.<br /><br /> `/out` 옵션을 사용하여 별도로 지정하지 않으면 `Sub Main` 프로시저를 포함하는 입력 파일의 이름이 출력 파일 이름으로 사용됩니다.<br /><br /> .exe로 컴파일되는 소스 코드 파일에는 `Sub Main` 프로시저가 하나만 필요합니다.  `Sub Main` 프로시저를 포함하는 클래스를 지정하려면 `/main` 컴파일러 옵션을 사용합니다.|  
|`/target:library`|컴파일러에서 DLL\(동적 연결 라이브러리\)을 만들도록 합니다.<br /><br /> 생성되는 동적 연결 라이브러리 파일에는 확장명 .dll이 사용됩니다.<br /><br /> `/out` 옵션을 사용하여 별도로 지정하지 않으면 첫 번째 입력 파일의 이름이 출력 파일 이름으로 사용됩니다.<br /><br /> DLL을 빌드할 때 `Sub Main` 프로시저는 필요하지 않습니다.|  
|`/target:module`|컴파일러는 어셈블리에 추가할 수 있는 모듈을 만듭니다.<br /><br /> 출력 파일에는 확장명 이 사용됩니다.  netmodule입니다.<br /><br /> .NET 공용 언어 런타임은 어셈블리가 없는 파일을 로드할 수 없습니다.  그러나 `/reference`를 사용하여 그러한 파일을 어셈블리의 어셈블리 매니페스트에 통합할 수 있습니다.<br /><br /> 한 모듈의 코드가 다른 모듈의 내부 형식을 참조하는 경우 `/reference`를 사용하여 두 모듈을 어셈블리 매니페스트로 통합해야 합니다.<br /><br /> [\/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md) 옵션은 모듈에서 메타데이터를 가져옵니다.|  
|`/target:winexe`|컴파일러가 실행 가능한 Windows 기반 응용 프로그램을 만들도록 지정합니다.<br /><br /> 확장명이 .exe인 실행 파일이 만들어집니다.  Windows 기반 프로그램은 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)] 클래스 라이브러리나 Win32 API를 사용하여 사용자 인터페이스를 제공합니다.<br /><br /> `/out` 옵션을 사용하여 별도로 지정하지 않으면 `Sub Main` 프로시저를 포함하는 입력 파일의 이름이 출력 파일 이름으로 사용됩니다.<br /><br /> .exe로 컴파일되는 소스 코드 파일에는 `Sub Main` 프로시저가 하나만 필요합니다.  코드에 `Sub Main` 프로시저가 포함된 클래스가 두 개 이상 있으면 `/main` 컴파일러 옵션을 사용하여 `Sub Main` 프로시저를 포함하는 클래스를 지정합니다.|  
|`/target:appcontainerexe`|컴파일러가 컨테이너 응용 프로그램을 실행 하는 실행 Windows 기반 응용 프로그램을 만들 수 있습니다.  이 설정을 사용 하도록 [!INCLUDE[win8_appname_long](../../../csharp/includes/win8-appname-long-md.md)] 응용 프로그램.<br /><br /> **appcontainerexe** 설정 비트 특성 필드에는 [Pe](http://go.microsoft.com/fwlink/p/?LinkId=236960) 파일.  응용 프로그램에는 응용 프로그램 컨테이너 실행 해야 하는이 비트를 나타냅니다.  이 비트가 설정 되어 있으면 경우 오류를 발생의 `CreateProcess` 메서드는 응용 프로그램 컨테이너 외부에서 응용 프로그램을 시작 하려고 합니다.  비트는이 설정을 외 **\/target:appcontainerexe** 같습니다 **\/target:winexe**.<br /><br /> 확장명이 .exe인 실행 파일이 만들어집니다.<br /><br /> 사용 하 여 별도로 지정 하지 않으면 있는 `/out` 옵션, 출력 파일 이름을 포함 하는 입력된 파일의 이름을 사용은 `Sub Main` 프로시저.<br /><br /> .exe로 컴파일되는 소스 코드 파일에는 `Sub Main` 프로시저가 하나만 필요합니다.  코드를 가진 클래스가 둘 이상 포함 되어 있는지는 `Sub Main` 절차를 사용의 `/main` 컴파일러 옵션을 포함 하는 클래스가 지정 하는 `Sub Main` 절차|  
|`/target:winmdobj`|컴파일러가 Windows 런타임 이진 \(.winmd\) 파일로 변환할 수 있는 중간 파일을 만들 수 있습니다.  관리 되는 언어 프로그램 뿐만 아니라 JavaScript 및 C\+\+ 프로그램에서.winmd 파일을 사용할 수 있습니다.<br /><br /> 중간 파일에.winmdobj 확장명으로 만들어집니다.<br /><br /> 사용 하 여 별도로 지정 하지 않으면 있는 `/out` 옵션을 사용 첫 번째 입력된 파일의 이름이 출력 파일 이름입니다.  A `Sub Main` 절차 필요 없습니다.<br /><br /> .Winmdobj 파일에 대 한 입력으로 사용할 수 있는 <xref:Microsoft.Build.Tasks.WinMDExp> 내보내기 도구에서 Windows 메타 데이터 \(WinMD\) 파일을.  WinMD 파일의 확장자는.winmd입니다 및 Windows 런타임 사용, C\+\+ 및 해당 Javascript에서 원래 라이브러리 및 WinMD 정의 코드 포함.|  
  
 `/target:module`을 지정하지 않으면 `/target`이 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)] 어셈블리 매니페스트를 출력 파일에 추가합니다.  
  
 Vbc.exe의 인스턴스마다 생성되는 출력 파일은 하나뿐입니다.  `/out` 또는 `/target`과 같은 컴파일러 옵션을 두 번 이상 지정하면 컴파일러에서 마지막으로 처리한 옵션이 적용됩니다.  컴파일할 때 모든 파일에 대한 정보가 매니페스트에 추가됩니다.  `/target:module`을 사용하여 만든 출력 파일을 제외한 모든 출력 파일의 매니페스트에 어셈블리 메타데이터가 포함됩니다.  출력 파일에 메타데이터를 표시하려면 [Ildasm.exe\(IL 디스어셈블러\)](../Topic/Ildasm.exe%20\(IL%20Disassembler\).md)를 사용하십시오.  
  
 `/target`의 약식 표현은 `/t`입니다.  
  
### Visual Studio IDE에서 \/target을 설정하려면  
  
1.  **솔루션 탐색기**에서 프로젝트를 선택합니다.  **프로젝트** 메뉴에서 **속성**을 선택합니다.  자세한 내용은 [Introduction to the Project Designer](http://msdn.microsoft.com/ko-kr/898dd854-c98d-430c-ba1b-a913ce3c73d7)을 참조하십시오.  
  
2.  **응용 프로그램** 탭을 클릭합니다.  
  
3.  **응용 프로그램 종류** 상자의 값을 수정합니다.  
  
## 예제  
 다음 코드는 `in.vb`를 컴파일하여 `in.dll`을 만듭니다.  
  
```  
vbc /target:library in.vb  
```  
  
## 참고 항목  
 [Visual Basic Command\-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [\/main](../../../visual-basic/reference/command-line-compiler/main.md)   
 [\/out](../../../visual-basic/reference/command-line-compiler/out.md)   
 [\/reference](../../../visual-basic/reference/command-line-compiler/reference.md)   
 [\/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md)   
 [\/moduleassemblyname](../../../visual-basic/reference/command-line-compiler/moduleassemblyname.md)   
 [어셈블리 및 전역 어셈블리 캐시](../Topic/Assemblies%20and%20the%20Global%20Assembly%20Cache%20\(C%23%20and%20Visual%20Basic\).md)   
 [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)