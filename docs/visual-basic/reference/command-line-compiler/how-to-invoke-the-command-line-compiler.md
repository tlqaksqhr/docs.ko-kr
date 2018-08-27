---
title: '방법: 명령줄 컴파일러 호출(Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- command-line arguments
- vbc.exe
- Visual Basic compiler, starting
- command line [Visual Basic], arguments
ms.assetid: 0fd9a8f6-f34e-4c35-a49d-9b9bbd8da4a9
ms.openlocfilehash: 0b835bb5654574a5aa6f32eede1e942b11e7dcb0
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2018
ms.locfileid: "42932156"
---
# <a name="how-to-invoke-the-command-line-compiler-visual-basic"></a>방법: 명령줄 컴파일러 호출(Visual Basic)
MS-DOS 프롬프트 라고도 하는 명령줄에 실행 파일의 이름을 입력 하 여 명령줄 컴파일러를 호출할 수 있습니다. 기본 Windows 명령 프롬프트에서에서 컴파일하는 경우에 실행 파일에 정규화 된 경로 입력 해야 합니다. 이 기본 동작을 재정의 하려면 Visual Studio 명령 프롬프트를 사용 하거나 경로 환경 변수를 수정 합니다. 둘 다 컴파일러 이름을 입력 하 여 모든 디렉터리에서 컴파일할 수 있습니다.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-invoke-the-compiler-using-the-visual-studio-command-prompt"></a>Visual Studio 명령 프롬프트를 사용 하 여 컴파일러를 호출 하려면  
  
1.  Microsoft Visual Studio 프로그램 그룹 내에서 Visual Studio Tools 프로그램 폴더를 엽니다.  
  
2.  Visual Studio를 설치한 경우 컴퓨터에 모든 디렉터리에서 컴파일러에 액세스할 Visual Studio 명령 프롬프트를 사용할 수 있습니다.  
  
3.  Visual Studio 명령 프롬프트를 호출 합니다.  
  
4.  명령줄에서 입력 `vbc.exe` *sourceFileName* 한 다음 ENTER를 누릅니다.  
  
     예를 들어 라는 디렉터리에 소스 코드를 저장 하는 경우 `SourceFiles`, 하는 명령 프롬프트를 열고 입력 `cd SourceFiles` 해당 디렉터리로 변경 합니다. 디렉터리 라는 원본 파일을 포함 하는 경우 `Source.vb`를 입력 하 여 컴파일할 수 있습니다 `vbc.exe Source.vb`합니다.  
  
### <a name="to-set-the-path-environment-variable-to-the-compiler-for-the-windows-command-prompt"></a>Windows 명령 프롬프트에 대 한 컴파일러를 PATH 환경 변수를 설정 하려면  
  
1.  로컬 디스크에 Vbc.exe를 찾으려면 Windows Search 기능을 사용 합니다.  
  
     컴파일러 위치한 디렉터리의 정확한 이름을 Windows 디렉터리의 위치는 "" 설치 된.NET Framework의 버전에 따라 달라 집니다. ".NET Framework" 설치의 둘 이상의 버전이 있는 경우 (일반적으로 최신 버전)를 사용 하는 버전을 결정 해야 합니다.  
  
2.  사용자 **시작** 메뉴를 마우스 오른쪽 단추로 클릭 **내 컴퓨터**를 클릭 하 고 **속성** 바로 가기 메뉴에서.  
  
3.  클릭 합니다 **고급** 탭을 클릭 한 다음 **환경 변수**합니다.  
  
4.  에 **시스템** 변수 창 **경로** 클릭 하 고 목록에서 **편집**합니다.  
  
5.  에 **시스템 편집** 변수 대화 상자에서 문자열의 끝에 삽입 포인터를 이동는 **변수 값** 필드 및 세미콜론 (;) 뒤에 1 단계에서에서 찾을 수 있는 전체 디렉터리 이름을 합니다.  
  
6.  클릭 **확인** 편집 내용을 확인 하 여 대화 상자를 닫습니다.  
  
     PATH 환경 변수를 변경한 후 실행할 수 있습니다 Visual Basic 컴파일러는 Windows 명령 프롬프트에서 디렉터리에서 컴퓨터에.  
  
### <a name="to-invoke-the-compiler-using-the-windows-command-prompt"></a>Windows 명령 프롬프트를 사용 하 여 컴파일러를 호출  
  
1.  **시작** 메뉴를 클릭 합니다 **Accessories** 폴더를 연 다음 합니다 **Windows 명령 프롬프트**합니다.  
  
2.  명령줄에서 입력 `vbc.exe` *sourceFileName* 한 다음 ENTER를 누릅니다.  
  
     예를 들어 라는 디렉터리에 소스 코드를 저장 하는 경우 `SourceFiles`, 하는 명령 프롬프트를 열고 입력 `cd SourceFiles` 해당 디렉터리로 변경 합니다. 디렉터리 라는 원본 파일을 포함 하는 경우 `Source.vb`를 입력 하 여 컴파일할 수 있습니다 `vbc.exe Source.vb`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md)  
 [조건부 컴파일](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
