---
title: "샘플 컴파일 명령줄(Visual Basic) | Microsoft Docs"
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
  - "명령줄, 컴파일러"
  - "컴파일, 명령줄"
  - "명령줄 컴파일러"
  - "소스 코드 컴파일, 명령줄"
  - "Visual Basic 컴파일러, 샘플 명령줄"
ms.assetid: 5bfbb487-5f47-4267-969a-39dfb917beeb
caps.latest.revision: 14
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 14
---
# 샘플 컴파일 명령줄(Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

[!INCLUDE[vsprvs](../../../csharp/includes/vsprvs-md.md)] 내에서 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] 프로그램을 컴파일하는 대신 명령줄에서 컴파일하여 실행 파일\(.exe\)이나 동적 연결 라이브러리 파일\(.dll\)을 만들 수 있습니다.  
  
 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] 명령줄 컴파일러는 입출력 파일, 어셈블리, 디버그 및 전처리기 옵션을 제어하는 모든 옵션 집합을 지원합니다.  각 옵션은 `-``option`과 `/``option`의 두 가지 형태로 사용할 수 있습니다.  이 문서에서는 `/``option` 형태만 보여 줍니다.  
  
 다음 표에서는 용도에 맞게 수정할 수 있는 샘플 명령줄 중 일부를 보여 줍니다.  
  
|To|기능|  
|--------|--------|  
|File.vb를 컴파일하여 File.exe 만들기|`vbc /reference:Microsoft.VisualBasic.dll File.vb`|  
|File.vb를 컴파일하여 File.dll 만들기|`vbc /target:library File.vb`|  
|File.vb를 컴파일하여 My.exe 만들기|`vbc /out:My.exe File.vb`|  
|최적화 기능을 사용하고 `DEBUG` 기호를 정의한 상태에서 현재 디렉터리의 모든 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] 파일을 컴파일하여 File2.exe 만들기|`vbc /define:DEBUG=1 /optimize /out:File2.exe *.vb`|  
|현재 디렉터리의 모든 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] 파일을 컴파일하여 로고 또는 경고를 표시하지 않는 File2.dll의 디버그 버전 만들기|`vbc /target:library /out:File2.dll /nowarn /nologo /debug *.vb`|  
|현재 디렉터리의 모든 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] 파일을 Something.dll로 컴파일|`vbc /target:library /out:Something.dll *.vb`|  
  
 명령줄에서 컴파일할 때 사용자는 `/reference` 컴파일러 옵션을 통해 Microsoft [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] 런타임 라이브러리를 명시적으로 참조해야 합니다.  
  
> [!TIP]
>  Visual Studio IDE를 사용 하 여 프로젝트를 빌드할 때 연결 된 항목에 대 한 정보를 표시할 수 있습니다 **vbc** 명령 출력 창에 해당 컴파일러 옵션을 사용 합니다.  이 정보를 표시 하려면 열은 [옵션 대화 상자, 프로젝트 및 솔루션, 빌드 및 실행](/visual-studio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run), 다음 설정의  **MSBuild 프로젝트 빌드 출력의 자세한 정도** 에  **보통** 또는 높은 수준의 자세한 정도.  자세한 내용은 [방법: 빌드 로그 파일 보기, 저장 및 구성](../Topic/How%20to:%20View,%20Save,%20and%20Configure%20Build%20Log%20Files.md)을 참조하십시오.  
  
## 참고 항목  
 [Visual Basic Command\-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Conditional Compilation](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)