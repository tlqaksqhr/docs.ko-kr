---
title: "How to: Invoke the Command-Line Compiler (Visual Basic) | Microsoft Docs"
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
  - "command-line arguments"
  - "vbc.exe"
  - "Visual Basic compiler, starting"
  - "command line, arguments"
ms.assetid: 0fd9a8f6-f34e-4c35-a49d-9b9bbd8da4a9
caps.latest.revision: 28
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 28
---
# How to: Invoke the Command-Line Compiler (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

MS\-DOS 프롬프트라고도 하는 명령줄에 실행 파일의 이름을 입력하면 명령줄 컴파일러를 호출할 수 있습니다.  기본 Windows 명령 프롬프트에서 컴파일하는 경우 실행 파일의 정규화된 경로를 입력해야 합니다.  이 기본 동작을 재정의하려면 [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs-md.md)] 명령 프롬프트를 사용하거나 PATH 환경 변수를 수정합니다.  두 경우 모두 컴파일러 이름을 입력하여 원하는 디렉터리에서 컴파일할 수 있습니다.  
  
 [!INCLUDE[note_settings_general](../../../csharp/language-reference/compiler-messages/includes/note-settings-general-md.md)]  
  
### Visual Studio 명령 프롬프트를 사용하여 컴파일러를 호출하려면  
  
1.  Microsoft Visual Studio 프로그램 그룹에서 Visual Studio Tools 프로그램 폴더를 엽니다.  
  
2.  사용할 수 있는 [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs-md.md)]Visual Studio설치 되어 있는 경우 사용자컴퓨터에 있는 디렉터리에서컴파일러에 액세스 하려면 명령 프롬프트.  
  
3.  [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs-md.md)] 명령 프롬프트를 호출합니다.  
  
4.  명령줄에 `vbc.exe` *sourceFileName*을 입력하고 Enter 키를 누릅니다.  
  
     예를 들어, 소스 코드를 `SourceFiles` 디렉터리에 저장한 경우 명령 프롬프트를 열고 `cd SourceFiles`를 입력하여 해당 디렉터리로 변경합니다.  디렉터리에 `Source.vb`라는 소스 파일이 포함되어 있는 경우 `vbc.exe Source.vb`를 입력하여 해당 파일을 컴파일할 수 있습니다.  
  
### PATH 환경 변수를 Windows 명령 프롬프트에 대한 컴파일러로 설정하려면  
  
1.  Windows 검색 기능을 사용하여 로컬 디스크에서 Vbc.exe를 찾습니다.  
  
     컴파일러가 있는 정확한 디렉터리 이름은 설치된 [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact-md.md)]의 버전과 Windows 디렉터리의 위치에 따라 다릅니다.  여러 개의 [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact-md.md)] 버전이 설치되어 있는 경우 사용할 버전\(일반적으로 최신 버전\)을 결정해야 합니다.  
  
2.  **시작** 메뉴에서 **내 컴퓨터**를 마우스 오른쪽 단추로 클릭한 다음 바로 가기 메뉴에서 **속성**을 클릭합니다.  
  
3.  **고급** 탭을 선택하고 **환경 변수**를 클릭합니다.  
  
4.  **시스템** 변수 창의 목록에서 **Path**를 선택하고 **편집**을 클릭합니다.  
  
5.  **시스템 변수 편집** 대화 상자에서 삽입 지점을 **변수 값** 필드의 문자열 끝으로 이동하고 세미콜론\(;\)을 입력한 다음 1단계에 있는 전체 디렉터리 이름을 입력합니다.  
  
6.  편집 내용을 확인했으면 **확인**을 클릭하여 대화 상자를 닫습니다.  
  
     PATH 환경 변수를 변경했으면 컴퓨터에 있는 임의 디렉터리의 Windows 명령 프롬프트에서 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] 컴파일러를 실행할 수 있습니다.  
  
### Windows 명령 프롬프트를 사용하여 컴파일러를 호출하려면  
  
1.  **시작** 메뉴에서 **보조프로그램** 폴더를 클릭한 다음 **Windows 명령 프롬프트**를 엽니다.  
  
2.  명령줄에 `vbc.exe` *sourceFileName*을 입력하고 Enter 키를 누릅니다.  
  
     예를 들어, 소스 코드를 `SourceFiles` 디렉터리에 저장한 경우 명령 프롬프트를 열고 `cd SourceFiles`를 입력하여 해당 디렉터리로 변경합니다.  디렉터리에 `Source.vb`라는 소스 파일이 포함되어 있는 경우 `vbc.exe Source.vb`를 입력하여 해당 파일을 컴파일할 수 있습니다.  
  
## 참고 항목  
 [Visual Basic Command\-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Conditional Compilation](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)