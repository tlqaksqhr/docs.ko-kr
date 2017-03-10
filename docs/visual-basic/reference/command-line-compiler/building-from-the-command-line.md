---
title: "명령줄에서 빌드(Visual Basic) | Microsoft Docs"
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
  - "빌드[Visual Basic], 명령줄"
  - "Visual Basic 컴파일러, Visual Basic 컴파일러 정보"
  - "명령줄[Visual Basic], 컴파일러"
  - "명령줄에서(Visual Basic), 빌드"
  - "명령줄[Visual Basic], 빌드"
  - "컴파일러, 명령줄에서 호출"
  - "명령줄 빌드"
  - "소스 코드 컴파일"
  - "명령줄 컴파일러, Visual Basic"
  - "명령줄[Visual Basic], Visual Basic"
ms.assetid: e61947e9-a42e-4717-a699-5f70a98cdd03
caps.latest.revision: 13
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 13
---
# 명령줄에서 빌드(Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] 프로젝트는 하나 이상의 개별 소스 파일로 구성됩니다.  컴파일 과정을 거치면서 이러한 소스 파일들은 단일 패키지, 즉 응용 프로그램으로 실행될 수 있는 하나의 실행 파일로 결합됩니다.  
  
 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에는 [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs-md.md)] IDE\(통합 개발 환경\)에서 프로그램을 컴파일할 수 있는 또 다른 방법인 명령줄 컴파일러가 제공됩니다.  명령줄 컴파일러는 시스템 메모리나 저장 공간이 한정되어 있는 컴퓨터를 사용하거나 이러한 컴퓨터에서 사용할 코드를 작성하는 경우처럼 IDE의 모든 기능을 사용할 필요가 없는 상황에 적합하도록 만들어졌습니다.  
  
 명령줄에서 컴파일할 때 사용자는 `/reference` 컴파일러 옵션을 통해 Microsoft [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] 런타임 라이브러리를 명시적으로 참조해야 합니다.  
  
 [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs-md.md)] IDE에서 소스 파일을 컴파일하려면 **빌드** 메뉴에서 **빌드** 명령을 선택합니다.  
  
> [!TIP]
>  프로젝트 파일을 Visual Studio IDE를 사용 하 여 빌드할 때 연결 된 항목에 대 한 정보를 표시할 수 있습니다 **vbc** 명령 및 출력 창에는 스위치.  이 정보를 표시 하려면 열은 [옵션 대화 상자, 프로젝트 및 솔루션, 빌드 및 실행](/visual-studio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run), 다음 설정의  **MSBuild 프로젝트 빌드 출력의 자세한 정도** 에  **보통** 또는 높은 수준의 자세한 정도.  자세한 내용은 [방법: 빌드 로그 파일 보기, 저장 및 구성](../Topic/How%20to:%20View,%20Save,%20and%20Configure%20Build%20Log%20Files.md)을 참조하십시오.  
  
 프로젝트 \(.vbproj\) 파일은 명령 프롬프트에서 Msbuild를 사용 하 여 컴파일할 수 있습니다.  자세한 내용은 [Command\-Line Reference](/visual-studio/msbuild/msbuild-command-line-reference) 및 [연습: MSBuild 사용](../Topic/Walkthrough:%20Using%20MSBuild.md)을 참조하십시오.  
  
## 단원 내용  
 [How to: Invoke the Command\-Line Compiler](../../../visual-basic/reference/command-line-compiler/how-to-invoke-the-command-line-compiler.md)  
 MS\-DOS 프롬프트 또는 특정 하위 디렉터리에서 명령줄 컴파일러를 호출하는 방법에 대해 설명합니다.  
  
 [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 사용자가 용도에 맞게 직접 수정할 수 있는 샘플 명령줄 목록을 제공합니다.  
  
## 관련 단원  
 [Visual Basic Command\-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md)  
 사전순 또는 용도별로 정렬된 컴파일러 옵션 목록을 제공합니다.  
  
 [Conditional Compilation](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)  
 코드의 특정 섹션만 컴파일하는 방법에 대해 설명합니다.  
  
 [Visual Studio에서 프로젝트 및 솔루션 빌드 및 정리](/visual-studio/ide/building-and-cleaning-projects-and-solutions-in-visual-studio)  
 각 빌드에 포함할 내용을 구성하는 방법, 프로젝트 속성을 선택하는 방법 및 프로젝트를 올바른 순서로 빌드하는 방법에 대해 설명합니다.