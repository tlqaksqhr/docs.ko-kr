---
title: "방법: 명령줄 컴파일러 호출(Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- command-line arguments
- vbc.exe
- Visual Basic compiler, starting
- command line [Visual Basic], arguments
ms.assetid: 0fd9a8f6-f34e-4c35-a49d-9b9bbd8da4a9
caps.latest.revision: "28"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5c69860ede5620272e67bde435e6e6fa08cc81bc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-invoke-the-command-line-compiler-visual-basic"></a>방법: 명령줄 컴파일러 호출(Visual Basic)
MS-DOS 프롬프트 라고도 하는 명령줄에 실행 파일의 이름을 입력 하 여 명령줄 컴파일러를 호출할 수 있습니다. 기본 Windows 명령 프롬프트에서에서 컴파일하는 경우에 실행 파일의 정규화 된 경로 입력 해야 합니다. 이 기본 동작을 재정의 하려면 사용할 수 있습니다는 [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] 명령 프롬프트 또는 PATH 환경 변수를 수정 합니다. 둘 다 컴파일러 이름을 입력 하 여 원하는 디렉터리에서 컴파일할 수 있습니다.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-invoke-the-compiler-using-the-visual-studio-command-prompt"></a>Visual Studio 명령 프롬프트를 사용 하 여 컴파일러를 호출 하려면  
  
1.  Microsoft Visual Studio 프로그램 그룹 내에서 Visual Studio Tools 프로그램 폴더를 엽니다.  
  
2.  사용할 수는 [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] Visual Studio가 설치 되어 컴퓨터에 모든 디렉터리에서 컴파일러에 액세스 하려면 명령 프롬프트입니다.  
  
3.  호출 된 [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] 명령 프롬프트입니다.  
  
4.  명령줄에서 입력 `vbc.exe` *sourceFileName* 한 다음 ENTER 키를 누릅니다.  
  
     예를 들어 라는 디렉터리에 소스 코드를 저장 하는 경우 `SourceFiles`, 종류와 명령 프롬프트를 열 때 `cd SourceFiles` 해당 디렉터리로 변경 합니다. 디렉터리 라는 소스 파일을 포함 하는 경우 `Source.vb`를 입력 하 여 컴파일할 수 `vbc.exe Source.vb`합니다.  
  
### <a name="to-set-the-path-environment-variable-to-the-compiler-for-the-windows-command-prompt"></a>Windows 명령 프롬프트에 대 한 컴파일러를 PATH 환경 변수를 설정 하려면  
  
1.  로컬 디스크에 Vbc.exe를 찾으려고 Windows 검색 기능을 사용 합니다.  
  
     컴파일러 있는 디렉터리의 정확한 이름을 Windows 디렉터리의 위치는 "" 설치 된.NET Framework의 버전에 따라 다릅니다. ".NET Framework" 설치 된 버전이 둘 이상 있는 경우 (일반적으로 최신 버전)를 사용 하는 버전을 확인 해야 합니다.  
  
2.  사용자 **시작** 메뉴를 마우스 오른쪽 단추로 클릭 **내 컴퓨터**, 클릭 하 고 **속성** 바로 가기 메뉴에서 합니다.  
  
3.  클릭는 **고급** 탭을 클릭 한 다음 **환경 변수**합니다.  
  
4.  에 **시스템** 변수 창 **경로** 클릭 확인 하 고 목록에서 **편집**합니다.  
  
5.  에 **편집 시스템** 변수 대화 상자에서 문자열의 끝에 삽입 포인터를 이동는 **변수 값** 필드 세미콜론 (;)을 입력 하 고 1 단계에는 전체 디렉터리 이름이 차례로 나옵니다.  
  
6.  클릭 **확인** 편집 내용을 확인 하는 대화 상자를 닫습니다.  
  
     PATH 환경 변수를 변경한 후 실행할 수 있습니다는 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 컴파일러는 컴퓨터의 모든 디렉터리에서 Windows 명령 프롬프트에서 합니다.  
  
### <a name="to-invoke-the-compiler-using-the-windows-command-prompt"></a>Windows 명령 프롬프트를 사용 하 여 컴파일러를 호출 하려면  
  
1.  **시작** 메뉴를 클릭 하 고 **Accessories** 폴더를 연 후는 **Windows 명령 프롬프트**합니다.  
  
2.  명령줄에서 입력 `vbc.exe` *sourceFileName* 한 다음 ENTER 키를 누릅니다.  
  
     예를 들어 라는 디렉터리에 소스 코드를 저장 하는 경우 `SourceFiles`, 종류와 명령 프롬프트를 열 때 `cd SourceFiles` 해당 디렉터리로 변경 합니다. 디렉터리 라는 소스 파일을 포함 하는 경우 `Source.vb`를 입력 하 여 컴파일할 수 `vbc.exe Source.vb`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md)  
 [조건부 컴파일](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
