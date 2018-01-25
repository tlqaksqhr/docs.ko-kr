---
title: "C# 컴파일러 옵션 범주별 목록"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- Visual C# compiler, options listed by category
- compiler options [C#], listed by category
- Visual C#, compiler options listed by category
ms.assetid: 96437ecc-6502-4cd3-b070-e9386a298e83
caps.latest.revision: "17"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 410cad333b023e59d8c093d70d0e248504625dd6
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="c-compiler-options-listed-by-category"></a>C# 컴파일러 옵션 범주별 목록
여기에서는 컴파일러 옵션을 범주별로 정렬합니다. 사전순 목록은 [C# 컴파일러 옵션 사전순 목록](../../../csharp/language-reference/compiler-options/listed-alphabetically.md)을 참조하세요.  
  
### <a name="optimization"></a>최적화  
  
|옵션|용도|  
|------------|-------------|  
|[-filealign](../../../csharp/language-reference/compiler-options/filealign-compiler-option.md)|출력 파일에 있는 섹션의 크기를 지정합니다.|  
|[-optimize](../../../csharp/language-reference/compiler-options/optimize-compiler-option.md)|최적화를 사용하거나 사용하지 않도록 설정합니다.|  
  
### <a name="output-files"></a>출력 파일  
  
|옵션|용도|  
|------------|-------------|  
|[-doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md)|처리된 문서 주석을 작성할 XML 파일을 지정합니다.|  
|[-out](../../../csharp/language-reference/compiler-options/out-compiler-option.md)|출력 파일을 지정합니다.|  
|[/pdb](../../../csharp/language-reference/compiler-options/pdb-compiler-option.md)|.pdb 파일의 이름과 위치를 지정합니다.|  
|[-platform](../../../csharp/language-reference/compiler-options/platform-compiler-option.md)|출력 플랫폼을 지정합니다.|  
|[/preferreduilang](../../../csharp/language-reference/compiler-options/preferreduilang-compiler-option.md)|컴파일러 출력 언어를 지정합니다.|  
|[/refout](refout-compiler-option.md)|주 어셈블리 외에도 참조 어셈블리를 생성합니다.|  
|[/refonly](refonly-compiler-option.md)|주 어셈블리를 대신 참조 어셈블리를 생성합니다.|  
|[-target](../../../csharp/language-reference/compiler-options/target-compiler-option.md)|다섯 가지 옵션([-target:appcontainerexe](../../../csharp/language-reference/compiler-options/target-appcontainerexe-compiler-option.md), [-target:exe](../../../csharp/language-reference/compiler-options/target-exe-compiler-option.md), [-target:library](../../../csharp/language-reference/compiler-options/target-library-compiler-option.md), [-target:module](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md), [-target:winexe](../../../csharp/language-reference/compiler-options/target-winexe-compiler-option.md) 또는 [-target:winmdobj](../../../csharp/language-reference/compiler-options/target-winmdobj-compiler-option.md)) 중 하나를 사용하여 출력 파일 형식을 지정합니다.|  
|-modulename:\<string>|소스 모듈의 이름을 지정합니다.|  
  
### <a name="net-framework-assemblies"></a>.NET Framework 어셈블리  
  
|옵션|용도|  
|------------|-------------|  
|[-addmodule](../../../csharp/language-reference/compiler-options/addmodule-compiler-option.md)|이 어셈블리의 일부가 될 모듈을 하나 이상 지정합니다.|  
|[-delaysign](../../../csharp/language-reference/compiler-options/delaysign-compiler-option.md)|공개 키를 추가하고 어셈블리는 서명되지 않은 채 두도록 컴파일러에 지시합니다.|  
|[-keycontainer](../../../csharp/language-reference/compiler-options/keycontainer-compiler-option.md)|암호화 키 컨테이너의 이름을 지정합니다.|  
|[-keyfile](../../../csharp/language-reference/compiler-options/keyfile-compiler-option.md)|암호화 키를 포함하는 파일 이름을 지정합니다.|  
|[/lib](../../../csharp/language-reference/compiler-options/lib-compiler-option.md)|[-reference](../../../csharp/language-reference/compiler-options/reference-compiler-option.md)를 통해 참조되는 어셈블리의 위치를 지정합니다.|  
|[-nostdlib](../../../csharp/language-reference/compiler-options/nostdlib-compiler-option.md)|표준 라이브러리(mscorlib.dll)를 가져오지 않도록 컴파일러에 지시합니다.|  
|[-reference](../../../csharp/language-reference/compiler-options/reference-compiler-option.md)|어셈블리를 포함하는 파일에서 메타데이터를 가져옵니다.|  
|-analyzer|이 어셈블리에서 분석기를 실행합니다(약식: /a).|  
|-additionalfile|코드 생성에 직접 영향을 주지 않지만 오류 또는 경고를 생성하기 위해 분석기에서 사용할 수 있는 추가 파일에 이름을 지정합니다.|  
  
### <a name="debuggingerror-checking"></a>디버깅/오류 검사  
  
|옵션|용도|  
|------------|-------------|  
|[-bugreport](../../../csharp/language-reference/compiler-options/bugreport-compiler-option.md)|쉽게 버그를 보고할 수 있도록 정보가 포함된 파일을 만듭니다.|  
|[/checked](../../../csharp/language-reference/compiler-options/checked-compiler-option.md)|데이터 형식 범위를 오버플로하는 정수 연산이 있는 경우 런타임에 예외가 발생되는지 여부를 지정합니다.|  
|[-debug](../../../csharp/language-reference/compiler-options/debug-compiler-option.md)|디버깅 정보를 내보내도록 컴파일러에 지시합니다.|  
|[-errorreport](../../../csharp/language-reference/compiler-options/errorreport-compiler-option.md)|오류 보고 동작을 설정합니다.|  
|[/fullpaths](../../../csharp/language-reference/compiler-options/fullpaths-compiler-option.md)|컴파일러 출력에서 파일의 절대 경로를 지정합니다.|  
|[-nowarn](../../../csharp/language-reference/compiler-options/nowarn-compiler-option.md)|지정한 경고가 컴파일러에서 생성되지 않도록 합니다.|  
|[/warn](../../../csharp/language-reference/compiler-options/warn-compiler-option.md)|경고 수준을 설정합니다.|  
|[-warnaserror](../../../csharp/language-reference/compiler-options/warnaserror-compiler-option.md)|경고를 오류로 승격합니다.|  
|-ruleset:\<file>|특정 진단을 사용하지 않는 규칙 집합 파일을 지정합니다.|  
  
### <a name="preprocessor"></a>전처리기  
  
|옵션|용도|  
|------------|-------------|  
|[-define](../../../csharp/language-reference/compiler-options/define-compiler-option.md)|전처리기 기호를 정의합니다.|  
  
### <a name="resources"></a>리소스  
  
|옵션|용도|  
|------------|-------------|  
|[-link](../../../csharp/language-reference/compiler-options/link-compiler-option.md)|지정된 어셈블리의 COM 형식 정보를 프로젝트에 사용할 수 있도록 합니다.|  
|[-linkresource](../../../csharp/language-reference/compiler-options/linkresource-compiler-option.md)|관리되는 리소스에 대한 링크를 만듭니다.|  
|[-resource](../../../csharp/language-reference/compiler-options/resource-compiler-option.md)|.NET Framework 리소스를 출력 파일에 포함합니다.|  
|[-win32icon](../../../csharp/language-reference/compiler-options/win32icon-compiler-option.md)|출력 파일에 삽입할 .ico 파일을 지정합니다.|  
|[/win32res:](../../../csharp/language-reference/compiler-options/win32res-compiler-option.md)|출력 파일에 삽입할 Win32 리소스를 지정합니다.|  
  
### <a name="miscellaneous"></a>기타  
  
|옵션|용도|  
|------------|-------------|  
|[@](../../../csharp/language-reference/compiler-options/response-file-compiler-option.md)|지시 파일을 지정합니다.|  
|[-?](../../../csharp/language-reference/compiler-options/help-compiler-option.md)|stdout에 컴파일러 옵션을 나열합니다.|  
|[-baseaddress](../../../csharp/language-reference/compiler-options/baseaddress-compiler-option.md)|DLL을 로드할 기본 설정 기준 주소를 지정합니다.|  
|[-codepage](../../../csharp/language-reference/compiler-options/codepage-compiler-option.md)|컴파일할 때 모든 소스 코드 파일에 사용할 코드 페이지를 지정합니다.|  
|[-help](../../../csharp/language-reference/compiler-options/help-compiler-option.md)|stdout에 컴파일러 옵션을 나열합니다.|  
|[-highentropyva](../../../csharp/language-reference/compiler-options/highentropyva-compiler-option.md)|실행 파일이 ASLR(주소 공간 레이아웃 불규칙화)을 지원하도록 지정합니다.|  
|[-langversion](../../../csharp/language-reference/compiler-options/langversion-compiler-option.md)|언어 버전 모드(Default, ISO-1, ISO-2, 3, 4, 5, 6, 7, 7.1 또는 최신)를 지정합니다. |  
|[-main](../../../csharp/language-reference/compiler-options/main-compiler-option.md)|**Main** 메서드의 위치를 지정합니다.|  
|[-noconfig](../../../csharp/language-reference/compiler-options/noconfig-compiler-option.md)|csc.rsp를 사용하여 컴파일하지 않도록 컴파일러에 지시합니다.|  
|[-nologo](../../../csharp/language-reference/compiler-options/nologo-compiler-option.md)|컴파일러 배너 정보를 표시하지 않습니다.|  
|[-recurse](../../../csharp/language-reference/compiler-options/recurse-compiler-option.md)|하위 디렉터리에서 컴파일할 소스 파일을 검색합니다.|  
|[-subsystemversion](../../../csharp/language-reference/compiler-options/subsystemversion-compiler-option.md)|실행 파일이 사용할 수 있는 하위 시스템의 최소 버전을 지정합니다.|  
|[/unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md)|[unsafe](../../../csharp/language-reference/keywords/unsafe.md) 키워드를 사용하는 코드를 컴파일할 수 있도록 설정합니다.|  
|[-utf8output](../../../csharp/language-reference/compiler-options/utf8output-compiler-option.md)|UTF-8 인코딩을 사용하여 컴파일러 출력을 표시합니다.|  
|-parallel[+&#124;-]|동시 빌드(+)를 사용할지 여부를 지정합니다.|  
|-checksumalgorithm:\<alg>|PDB에 저장된 소스 파일 체크섬을 계산하기 위한 알고리즘을 지정합니다.  지원되는 값은 SHA1(기본값) 또는 SHA256입니다.|  
  
## <a name="obsolete-options"></a>사용되지 않는 옵션  
  
|옵션|용도|  
|---|---|  
|-incremental|증분 컴파일을 사용하도록 설정합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [C# 컴파일러 옵션](../../../csharp/language-reference/compiler-options/index.md)  
 [사전순 C# 컴파일러 옵션 목록](../../../csharp/language-reference/compiler-options/listed-alphabetically.md)  
 [방법: Visual Studio 명령줄에 필요한 환경 변수 설정](../../../csharp/language-reference/compiler-options/how-to-set-environment-variables-for-the-visual-studio-command-line.md)
