---
title: "샘플 컴파일 명령줄 (Visual Basic) | Microsoft 문서"
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
- command line, compilers
- compilation, command-line
- command-line compilers
- compiling source code, from command line
- Visual Basic compiler, sample command lines
ms.assetid: 5bfbb487-5f47-4267-969a-39dfb917beeb
caps.latest.revision: 14
author: stevehoag
ms.author: shoag
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 918787b3377f2e5a636a6b098046ac2f455efcdd
ms.lasthandoff: 03/13/2017

---
# <a name="sample-compilation-command-lines-visual-basic"></a>샘플 컴파일 명령줄(Visual Basic)
컴파일하는 대신 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 내에서 프로그램 [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)], 실행 파일 (.exe) 파일 또는 동적 연결 라이브러리 (.dll) 파일을 생성 하는 명령줄에서 컴파일할 수 있습니다.  
  
 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 명령줄 컴파일러는 입력 및 출력 파일, 어셈블리 및 디버그를 제어 하는 옵션 및 전처리기 옵션의 전체 집합을 지원 합니다. 각 옵션은 동일 하 게 사용 하는 두 가지 형태로 사용할 수 있는: `-``option` 및 `/``option`합니다. 이 설명서 표시는 `/``option` 폼입니다.  
  
 다음 표에서 용도 맞게 수정할 수 있는 일부 예제 명령줄을 나열 합니다.  
  
|후|기능|  
|--------|---------|  
|File.vb 컴파일하고 File.exe 만들기|`vbc /reference:Microsoft.VisualBasic.dll File.vb`|  
|File.vb 컴파일하고 File.dll 만들기|`vbc /target:library File.vb`|  
|File.vb 컴파일하고 My.exe 만들기|`vbc /out:My.exe File.vb`|  
|모든 컴파일 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 에 최적화 된 현재 디렉터리에 파일 및 `DEBUG` 기호를 정의 File2.exe를 생성 합니다.|`vbc /define:DEBUG=1 /optimize /out:File2.exe *.vb`|  
|모든 컴파일 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 로고 또는 경고를 표시 하지 않고 File2.dll의 디버그 버전을 생성 하는 현재 디렉터리의 파일|`vbc /target:library /out:File2.dll /nowarn /nologo /debug *.vb`|  
|모든 컴파일 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Something.dll 현재 디렉터리의 파일|`vbc /target:library /out:Something.dll *.vb`|  
  
 Microsoft를 명령줄에서 컴파일하는 경우 명시적으로 참조 해야 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 를 통해 런타임 라이브러리는 `/reference` 컴파일러 옵션입니다.  
  
> [!TIP]
>  Visual Studio IDE를 사용 하 여 프로젝트를 빌드할 때 연결 된 작업에 대 한 정보를 표시할 수 있습니다 **vbc** 명령을 출력 창에 해당 컴파일러 옵션을 사용 합니다. 이 정보를 표시 하려면 열에서 [옵션 대화 상자, 프로젝트 및 솔루션, 빌드 및 실행](https://docs.microsoft.com/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run)로 설정한는 **MSBuild 프로젝트 빌드 출력의 자세한 정도** 를 **보통** 또는 더 높은 수준의 자세한 정도입니다. 자세한 내용은 [방법: 빌드 로그 파일 보기, 저장 및 구성](http://msdn.microsoft.com/library/75d38b76-26d6-4f43-bbe7-cbacd7cc81e7)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md)   
 [조건부 컴파일](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
