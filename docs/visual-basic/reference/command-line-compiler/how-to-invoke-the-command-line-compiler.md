---
title: "방법: 명령줄 컴파일러 (Visual Basic)를 호출 합니다. | Microsoft 문서"
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
- command-line arguments
- vbc.exe
- Visual Basic compiler, starting
- command line, arguments
ms.assetid: 0fd9a8f6-f34e-4c35-a49d-9b9bbd8da4a9
caps.latest.revision: 28
author: stevehoag
ms.author: shoag
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
ms.openlocfilehash: 69c95289f91f712bd3fda03a7f582d879141591a
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-invoke-the-command-line-compiler-visual-basic"></a>방법: 명령줄 컴파일러 호출(Visual Basic)
MS-DOS 프롬프트 라고도 하는 명령줄에 실행 파일의 이름을 입력 하 여 명령줄 컴파일러를 호출할 수 있습니다. 기본 Windows 명령 프롬프트에서에서 컴파일하는 경우에 실행 파일의 정규화 된 경로 입력 해야 합니다. 이 기본 동작을 재정의 하는 방법은 사용 하 여는 [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] 명령 프롬프트를 하거나 PATH 환경 변수를 수정 합니다. 둘 다 컴파일러 이름을 입력 하 여 원하는 디렉터리에서 컴파일할 수 있습니다.  
  
[!INCLUDE[note_settings_general](../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
### <a name="to-invoke-the-compiler-using-the-visual-studio-command-prompt"></a>Visual Studio 명령 프롬프트를 사용 하 여 컴파일러를 호출 하려면  
  
1.  Microsoft Visual Studio 프로그램 그룹 내에서 Visual Studio Tools 프로그램 폴더를 엽니다.  
  
2.  사용할 수는 [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] Visual Studio가 설치 된 경우 컴퓨터에 모든 디렉터리에서 컴파일러에 액세스 하려면 명령 프롬프트입니다.  
  
3.  호출 된 [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] 명령 프롬프트입니다.  
  
4.  명령줄에서 입력 `vbc.exe` *sourceFileName* 한 다음 ENTER를 누릅니다.  
  
     예를 들어 라는 디렉터리에 소스 코드를 저장 하는 경우 `SourceFiles`를 입력 하 고 명령 프롬프트를 열 때 `cd SourceFiles` 해당 디렉터리로 변경 합니다. 디렉터리 라는 소스 파일을 포함 하는 경우 `Source.vb`를 입력 하 여 컴파일할 수 `vbc.exe Source.vb`합니다.  
  
### <a name="to-set-the-path-environment-variable-to-the-compiler-for-the-windows-command-prompt"></a>Windows 명령 프롬프트에 대 한 컴파일러에 PATH 환경 변수를 설정 하려면  
  
1.  로컬 디스크에 Vbc.exe를 찾으려고 Windows 검색 기능을 사용 합니다.  
  
     컴파일러가 있는 디렉터리의 정확한 이름을 Windows 디렉터리의 위치와의 버전에 따라 달라 집니다는 [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)] 설치 합니다. 버전이 여러 개 있는 경우는 [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)] 설치 (일반적으로 최신 버전)를 사용 하 여 버전을를 결정 해야 합니다.  
  
2.  사용자 **시작** 메뉴를 마우스 오른쪽 단추로 클릭 **내 컴퓨터**, 클릭 하 고 **속성** 바로 가기 메뉴에서.  
  
3.  클릭 하 고 **고급** 탭을 클릭 한 후 **환경 변수**합니다.  
  
4.  에 **시스템** 변수 창의 **경로** 의 목록에서 클릭 **편집**합니다.  
  
5.  에 **편집 시스템** 변수 대화 상자에서 문자열의 끝에 삽입 지점을 이동는 **변수 값** 필드를 세미콜론 (;)을 입력 1 단계에서에서 찾은 전체 디렉터리 이름이 차례로 나옵니다.  
  
6.  클릭 **확인** 편집 내용을 확인 하 여 대화 상자를 닫습니다.  
  
     PATH 환경 변수를 변경한 후 실행할 수 있습니다는 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 컴퓨터에 모든 디렉터리에서 Windows 명령 프롬프트에서 컴파일러입니다.  
  
### <a name="to-invoke-the-compiler-using-the-windows-command-prompt"></a>Windows 명령 프롬프트를 사용 하 여 컴파일러를 호출 하려면  
  
1.  **시작** 메뉴를 클릭은 **액세서리** 폴더를 연 후의 **Windows 명령 프롬프트**합니다.  
  
2.  명령줄에서 입력 `vbc.exe` *sourceFileName* 한 다음 ENTER를 누릅니다.  
  
     예를 들어 라는 디렉터리에 소스 코드를 저장 하는 경우 `SourceFiles`를 입력 하 고 명령 프롬프트를 열 때 `cd SourceFiles` 해당 디렉터리로 변경 합니다. 디렉터리 라는 소스 파일을 포함 하는 경우 `Source.vb`를 입력 하 여 컴파일할 수 `vbc.exe Source.vb`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md)   
 [조건부 컴파일](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
