---
title: "C# 컴파일러 옵션 사전순 목록"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- compiler options [C#], listed alpabetically
- C# language, compiler options listed alphabitically
- Visual C# compiler, options listed alphabetically
- Visual C#, compiler options listed alphabetically
ms.assetid: 43535ea0-ca47-4a15-b528-615087a86092
caps.latest.revision: 25
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
ms.sourcegitcommit: 8e8d01587ccde967b8484b3b61916f8cf437f6c0
ms.openlocfilehash: 8a32dcab0a64fdb715871806088825e227f08abb
ms.contentlocale: ko-kr
ms.lasthandoff: 09/19/2017

---
# <a name="c-compiler-options-listed-alphabetically"></a>C# 컴파일러 옵션 사전순 목록
여기에서는 컴파일러 옵션을 사전순으로 정렬합니다. 범주별 목록을 보려면 [C# 컴파일러 옵션 범주별 목록](../../../csharp/language-reference/compiler-options/listed-by-category.md)을 참조하세요.  
  
|옵션|용도|  
|------------|-------------|  
|[@](../../../csharp/language-reference/compiler-options/response-file-compiler-option.md)|추가 옵션에 대한 지시 파일을 읽습니다.|  
|[/?](../../../csharp/language-reference/compiler-options/help-compiler-option.md)|stdout에 사용법 메시지를 표시합니다.|  
|/additionalfile|코드 생성에 직접 영향을 주지 않지만 오류 또는 경고를 생성하기 위해 분석기에서 사용할 수 있는 추가 파일에 이름을 지정합니다.|  
|[/addmodule](../../../csharp/language-reference/compiler-options/addmodule-compiler-option.md)|지정한 모듈을 이 어셈블리에 링크합니다.|  
|/analyzer|이 어셈블리에서 분석기를 실행합니다(약식: /a).|  
|[/appconfig](../../../csharp/language-reference/compiler-options/appconfig-compiler-option.md)|어셈블리 바인딩 시간에 app.config의 위치를 지정합니다.|  
|[/baseaddress](../../../csharp/language-reference/compiler-options/baseaddress-compiler-option.md)|빌드할 라이브러리의 기준 주소를 지정합니다.|  
|[/bugreport](../../../csharp/language-reference/compiler-options/bugreport-compiler-option.md)|'버그 보고서' 파일을 만듭니다. /errorreport:prompt 또는 /errorreport:send와 함께 사용하면 이 파일이 충돌 정보와 함께 전송됩니다.|  
|[/checked](../../../csharp/language-reference/compiler-options/checked-compiler-option.md)|컴파일러에서 오버플로 검사를 생성하도록 합니다.|  
|/checksumalgorithm:\<alg>|PDB에 저장된 소스 파일 체크섬을 계산하기 위한 알고리즘을 지정합니다.  지원되는 값은 SHA1(기본값) 또는 SHA256입니다.|  
|[/codepage](../../../csharp/language-reference/compiler-options/codepage-compiler-option.md)|소스 파일을 열 때 사용할 코드 페이지를 지정합니다.|  
|[/debug](../../../csharp/language-reference/compiler-options/debug-compiler-option.md)|디버깅 정보를 내보냅니다.|  
|[/define](../../../csharp/language-reference/compiler-options/define-compiler-option.md)|조건부 컴파일 기호를 정의합니다.|  
|[/delaysign](../../../csharp/language-reference/compiler-options/delaysign-compiler-option.md)|강력한 이름 키의 공용 부분만 사용하여 어셈블리 서명을 연기합니다.|  
|[/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md)|생성할 XML 문서 파일을 지정합니다.|  
|[/errorreport](../../../csharp/language-reference/compiler-options/errorreport-compiler-option.md)|내부 컴파일러 오류를 처리하는 방법을 지정합니다. prompt, send 또는 none 중에서 선택할 수 있으며 기본값은 none입니다.|  
|[/filealign](../../../csharp/language-reference/compiler-options/filealign-compiler-option.md)|출력 파일 섹션에 사용되는 맞춤을 지정합니다.|  
|[/fullpaths](../../../csharp/language-reference/compiler-options/fullpaths-compiler-option.md)|컴파일러에서 정규화된 경로를 생성하도록 합니다.|  
|[/help](../../../csharp/language-reference/compiler-options/help-compiler-option.md)|stdout에 사용법 메시지를 표시합니다.|  
|[/highentropyva](../../../csharp/language-reference/compiler-options/highentropyva-compiler-option.md)|높은 엔트로피 ASLR을 지원하도록 지정합니다.|  
|/incremental|증분 컴파일을 사용하도록 설정합니다(사용되지 않음).|  
|[/keycontainer](../../../csharp/language-reference/compiler-options/keycontainer-compiler-option.md)|강력한 이름의 키 컨테이너를 지정합니다.|  
|[/keyfile](../../../csharp/language-reference/compiler-options/keyfile-compiler-option.md)|강력한 이름의 키 파일을 지정합니다.|  
|[/langversion:\<string>](../../../csharp/language-reference/compiler-options/langversion-compiler-option.md)|언어 버전 모드(Default, ISO-1, ISO-2, 3, 4, 5, 6, 7, 7.1 또는 최신)를 지정합니다. |  
|[/lib](../../../csharp/language-reference/compiler-options/lib-compiler-option.md)|참조를 검색할 추가 디렉터리를 지정합니다.|  
|[/link](../../../csharp/language-reference/compiler-options/link-compiler-option.md)|지정된 어셈블리의 COM 형식 정보를 프로젝트에 사용할 수 있도록 합니다.|  
|[/linkresource](../../../csharp/language-reference/compiler-options/linkresource-compiler-option.md)|지정한 리소스를 이 어셈블리에 링크합니다.|  
|[/main](../../../csharp/language-reference/compiler-options/main-compiler-option.md)|진입점을 포함하는 형식을 지정합니다. 다른 모든 가능한 진입점은 무시합니다.|  
|[/moduleassemblyname](../../../csharp/language-reference/compiler-options/moduleassemblyname-compiler-option.md)|.netmodule에서 public이 아닌 형식에 액세스할 수 있는 어셈블리를 지정합니다.|  
|/modulename:\<string>|소스 모듈의 이름을 지정합니다.|  
|[/noconfig](../../../csharp/language-reference/compiler-options/noconfig-compiler-option.md)|컴파일러에서 CSC.RSP 파일을 자동으로 포함하지 않도록 합니다.|  
|[/nologo](../../../csharp/language-reference/compiler-options/nologo-compiler-option.md)|컴파일러 저작권 메시지를 표시하지 않습니다.|  
|[/nostdlib](../../../csharp/language-reference/compiler-options/nostdlib-compiler-option.md)|컴파일러에서 표준 라이브러리(mscorlib.dll)를 참조하지 않도록 합니다.|  
|[/nowarn](../../../csharp/language-reference/compiler-options/nowarn-compiler-option.md)|특정 경고 메시지를 사용하지 않도록 설정합니다.|  
|[/nowin32manifest](../../../csharp/language-reference/compiler-options/nowin32manifest-compiler-option.md)|응용 프로그램 매니페스트를 실행 파일에 포함하지 않도록 컴파일러에 지시합니다.|  
|[/optimize](../../../csharp/language-reference/compiler-options/optimize-compiler-option.md)|최적화를 사용하거나 사용하지 않도록 설정합니다.|  
|[/out](../../../csharp/language-reference/compiler-options/out-compiler-option.md)|출력 파일 이름을 지정합니다(기본값: 주 클래스가 있는 파일의 기본 이름 또는 첫째 파일).|  
|/parallel[+&#124;-]|동시 빌드(+)를 사용할지 여부를 지정합니다.|  
|[/pdb](../../../csharp/language-reference/compiler-options/pdb-compiler-option.md)|.pdb 파일의 이름과 위치를 지정합니다.|  
|[/platform](../../../csharp/language-reference/compiler-options/platform-compiler-option.md)|이 코드를 실행할 수 있는 플랫폼을 x86, Itanium, x64, anycpu 또는 anycpu32bitpreferred로 제한합니다. 기본값은 anycpu입니다.|  
|[/preferreduilang](../../../csharp/language-reference/compiler-options/preferreduilang-compiler-option.md)|컴파일러 출력에 사용할 언어를 지정합니다.|  
|[/recurse](../../../csharp/language-reference/compiler-options/recurse-compiler-option.md)|와일드카드 지정에 따라 현재 디렉터리와 하위 디렉터리에 있는 모든 파일을 포함합니다.|  
|[/reference](../../../csharp/language-reference/compiler-options/reference-compiler-option.md)|지정한 어셈블리 파일에서 메타데이터를 참조합니다.|  
|[/refout](refout-compiler-option.md)|주 어셈블리 외에도 참조 어셈블리를 생성합니다.|  
|[/refonly](refonly-compiler-option.md)|주 어셈블리를 대신 참조 어셈블리를 생성합니다.|  
|[/resource](../../../csharp/language-reference/compiler-options/resource-compiler-option.md)|지정한 리소스를 포함합니다.|  
|/ruleset:\<file>|특정 진단을 사용하지 않는 규칙 집합 파일을 지정합니다.|  
|[/subsystemversion](../../../csharp/language-reference/compiler-options/subsystemversion-compiler-option.md)|실행 파일이 사용할 수 있는 하위 시스템의 최소 버전을 지정합니다.|  
|[/target](../../../csharp/language-reference/compiler-options/target-compiler-option.md)|네 가지 옵션([/target:appcontainerexe](../../../csharp/language-reference/compiler-options/target-appcontainerexe-compiler-option.md), [/target:exe](../../../csharp/language-reference/compiler-options/target-exe-compiler-option.md), [/target:library](../../../csharp/language-reference/compiler-options/target-library-compiler-option.md), [/target:module](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md), [/target:winexe](../../../csharp/language-reference/compiler-options/target-winexe-compiler-option.md), [/target:winmdobj](../../../csharp/language-reference/compiler-options/target-winmdobj-compiler-option.md)) 중 하나를 사용하여 출력 파일의 형식을 지정합니다.|  
|[/unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md)|[안전하지 않은](../../../csharp/language-reference/keywords/unsafe.md) 코드를 허용합니다.|  
|[/utf8output](../../../csharp/language-reference/compiler-options/utf8output-compiler-option.md)|컴파일러 메시지를 UTF-8 인코딩으로 출력합니다.|  
|[/warn](../../../csharp/language-reference/compiler-options/warn-compiler-option.md)|경고 수준(0-4)을 설정합니다.|  
|[/warnaserror](../../../csharp/language-reference/compiler-options/warnaserror-compiler-option.md)|특정 경고를 오류로 보고합니다.|  
|[/win32icon](../../../csharp/language-reference/compiler-options/win32icon-compiler-option.md)|이 아이콘을 사용하여 출력합니다.|  
|[/win32manifest](../../../csharp/language-reference/compiler-options/win32manifest-compiler-option.md)|사용자 지정 win32 매니페스트 파일을 지정합니다.|  
|[/win32res](../../../csharp/language-reference/compiler-options/win32res-compiler-option.md)|win32 리소스 파일(.res)을 지정합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [C# 컴파일러 옵션](../../../csharp/language-reference/compiler-options/index.md)   
 [범주별 C# 컴파일러 옵션 목록](../../../csharp/language-reference/compiler-options/listed-by-category.md)   
 [방법: Visual Studio 명령줄에 필요한 환경 변수 설정](../../../csharp/language-reference/compiler-options/how-to-set-environment-variables-for-the-visual-studio-command-line.md)   
 [\<compiler> 요소](../../../framework/configure-apps/file-schema/compiler/compiler-element.md)

