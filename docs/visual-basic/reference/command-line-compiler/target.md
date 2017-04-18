---
title: "/target (Visual Basic) | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- target compiler options [Visual Basic]
- -target compiler options [Visual Basic]
- /target compiler options [Visual Basic]
ms.assetid: e0954147-548b-461f-9c4b-a8f88845616c
caps.latest.revision: 29
author: dotnet-bot
ms.author: dotnetcontent
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
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: ccdb87188b924303057d5867dccece937defe74d
ms.lasthandoff: 03/13/2017

---
# <a name="target-visual-basic"></a>/target(Visual Basic)
컴파일러 출력의 형식을 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
/target:{exe | library | module | winexe | appcontainerexe | winmdobj}  
```  
  
## <a name="remarks"></a>주의  
 다음 표에서 요약의 효과 `/target` 옵션입니다.  
  
|**옵션**|**동작**|  
|----------------|------------------|  
|`/target:exe`|컴파일러가 실행 가능한 콘솔 응용 프로그램을 만드는 합니다.<br /><br /> 하지 않으면 기본 옵션입니다 `/target` 옵션을 지정 합니다. 실행 파일 확장명이.exe 만들어집니다.<br /><br /> 지정 하지 않으면는 `/out` 옵션을 출력 파일 이름 포함 하는 입력된 파일의 이름으로 사용 된 `Sub Main` 절차.<br /><br /> 하나의 `Sub Main` 프로시저는.exe로 컴파일되는 소스 코드 파일에 필요 합니다. 사용 하 여는 `/main` 컴파일러 옵션을 포함 하는 클래스가 지정 된 `Sub Main` 프로시저입니다.|  
|`/target:library`|컴파일러가 동적 연결 라이브러리 (DLL)를 만들려고 합니다.<br /><br /> 동적 연결 라이브러리 파일은.dll 확장명으로 생성 됩니다.<br /><br /> 지정 하지 않으면는 `/out` 옵션을 출력 파일 이름으로 첫 번째 입력된 파일의 이름을 사용 합니다.<br /><br /> DLL을 빌드할 때는 `Sub Main` 절차가 필요 하지 않습니다.|  
|`/target:module`|컴파일러가 어셈블리에 추가할 수 있는 모듈을 만듭니다.<br /><br /> 출력 파일은.netmodule의 확장으로 생성 됩니다.<br /><br /> .NET 공용 언어 런타임 어셈블리 없는 파일을 로드할 수 없습니다. 그러나 통합할 수 있습니다 이러한 파일 어셈블리의 어셈블리 매니페스트를 사용 하 여 `/reference`합니다.<br /><br /> 모듈을 모두를 사용 하 여 어셈블리 매니페스트에 통합 해야 모듈 하나에 코드에서 다른 모듈의 내부 형식을 참조 하는 경우 `/reference`합니다.<br /><br /> [/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md) 옵션 모듈에서 메타 데이터를 가져옵니다.|  
|`/target:winexe`|컴파일러가 실행 가능한 Windows 기반 응용 프로그램을 만들려고 합니다.<br /><br /> 실행 파일 확장명이.exe 만들어집니다. Windows 기반 응용 프로그램을 제공 하는 것 중 하나에서 사용자 인터페이스는 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] 클래스 라이브러리 또는 Win32 Api와 함께 합니다.<br /><br /> 지정 하지 않으면는 `/out` 옵션을 출력 파일 이름 포함 하는 입력된 파일의 이름으로 사용 된 `Sub Main` 절차.<br /><br /> 하나의 `Sub Main` 프로시저는.exe로 컴파일되는 소스 코드 파일에 필요 합니다. 코드에 둘 이상의 클래스에 있는 경우에는 `Sub Main` 프로시저를 사용 하 여는 `/main` 컴파일러 옵션을 포함 하는 클래스가 지정 된 `Sub Main` 프로시저|  
|`/target:appcontainerexe`|응용 프로그램을 만드는 실행 가능한 Windows 기반 응용 프로그램 컨테이너에서 실행 해야 하는 컴파일러가 선택 합니다. 이 설정은 사용자에 사용할 [!INCLUDE[win8_appname_long](../../../csharp/includes/win8_appname_long_md.md)] 응용 프로그램입니다.<br /><br /> **appcontainerexe** 설정을 설정 하는 약간의 특성 필드에는 [이식 가능한 실행 파일](http://go.microsoft.com/fwlink/p/?LinkId=236960) 파일입니다. 이 비트가 나타냅니다. 응용 프로그램 컨테이너에서 응용 프로그램을 실행 해야 합니다. 이 비트가 설정 되어 오류가 발생 하는 경우는 `CreateProcess` 메서드를 응용 프로그램 컨테이너 외부에서 응용 프로그램을 시작 하려고 시도 합니다. 이 비트가 설정 외에도 **/target: appcontainerexe** 같습니다 **/target: winexe**합니다.<br /><br /> 실행 파일 확장명이.exe 만들어집니다.<br /><br /> 사용 하 여 별도로 지정 하지 않으면는 `/out` 옵션을 출력 파일 이름 포함 하는 입력된 파일의 이름으로 사용 된 `Sub Main` 프로시저.<br /><br /> 하나의 `Sub Main` 프로시저는.exe로 컴파일되는 소스 코드 파일에 필요 합니다. 코드에 있는 둘 이상의 클래스를 포함 하는 경우는 `Sub Main` 프로시저를 사용 하 여는 `/main` 컴파일러 옵션을 포함 하는 클래스가 지정 된 `Sub Main` 프로시저|  
|`/target:winmdobj`|컴파일러가 Windows 런타임 이진 (.winmd) 파일로 변환할 수 있는 중간 파일을 만들려고 합니다. .Winmd 파일은 관리 되는 언어 프로그램 뿐만 아니라 JavaScript 및 c + + 프로그램에서 사용할 수 있습니다.<br /><br /> 중간 파일.winmdobj 확장명으로 생성 됩니다.<br /><br /> 사용 하 여 별도로 지정 하지 않으면는 `/out` 옵션을 출력 파일 이름으로 첫 번째 입력된 파일의 이름을 사용 합니다. A `Sub Main` 프로시저는 필요 하지 않습니다.<br /><br /> .Winmdobj 파일에 대 한 입력으로 사용 하도록 설계 되는 <xref:Microsoft.Build.Tasks.WinMDExp>Windows 메타 데이터 (WinMD) 파일을 생성 하는 도구를 내보냅니다.</xref:Microsoft.Build.Tasks.WinMDExp> WinMD 파일 확장명이.winmd 및 해당 JavaScript, c + + 및 Windows 런타임 사용 WinMD 정 및 원본 라이브러리에서 코드를 포함 합니다.|  
  
 지정 하지 않으면 `/target:module`, `/target` 하면는 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] 어셈블리 매니페스트를 출력 파일에 추가할 수 있습니다.  
  
 Vbc.exe의 각 인스턴스를 생성, 최대 출력 파일은 하나입니다. 와 같은 컴파일러 옵션을 지정 하는 경우 `/out` 또는 `/target` 한 번 이상, 개가 처리 효과에 배치 됩니다. 컴파일에서 모든 파일에 대 한 정보는 매니페스트에 추가 됩니다. 모든 출력 파일을 사용 하 여 만든 것을 제외한 파일 `/target:module` 매니페스트에 어셈블리 메타 데이터를 포함 합니다. 사용 하 여 [Ildasm.exe (IL 디스어셈블러)](https://msdn.microsoft.com/library/f7dy01k1) 출력 파일에 메타 데이터를 볼 수 있습니다.  
  
 약식 `/target` 는 `/t`합니다.  
  
### <a name="to-set-target-in-the-visual-studio-ide"></a>Visual Studio IDE에서 /target을 설정 하려면  
  
1.  **솔루션 탐색기**에서 프로젝트를 선택합니다. 에 **프로젝트** 메뉴를 클릭 하 여 **속성**합니다. 자세한 내용은 [프로젝트 디자이너 소개](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7)를 참조하세요.  
  
2.  **응용 프로그램** 탭을 클릭합니다.  
  
3.  값을 수정 된 **응용 프로그램 종류** 상자입니다.  
  
## <a name="example"></a>예제  
 다음 코드에서는 `in.vb`만들기, `in.dll`:  
  
```  
vbc /target:library in.vb  
```  
  
## <a name="see-also"></a>참고 항목  
 [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md)   
 [주 /](../../../visual-basic/reference/command-line-compiler/main.md)   
 [/out (Visual Basic)](../../../visual-basic/reference/command-line-compiler/out.md)   
 [/reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)   
 [/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md)   
 [/moduleassemblyname](../../../visual-basic/reference/command-line-compiler/moduleassemblyname.md)   
 [어셈블리 및 전역 어셈블리 캐시](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)   
 [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
