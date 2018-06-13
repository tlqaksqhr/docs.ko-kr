---
title: '프로젝트 구성 (F #)'
description: 'Visual Studio에서 F # 프로젝트에서 작업할 때 프로젝트 디자이너를 사용 하는 방법에 알아봅니다.'
ms.date: 05/16/2016
ms.openlocfilehash: a6c9539945bbd32748ffca1434c984402bc3f17b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33565466"
---
# <a name="configuring-projects-in-visual-studio"></a>Visual Studio에서 프로젝트 구성

> [!NOTE]
이 문서는 최신 Visual Studio와 함께 최신 상태로 되지 않습니다.  업데이트 됩니다.

이 항목에서는 사용 하는 방법에 대 한 정보는 **프로젝트 디자이너** F # 프로젝트에서 작업할 때. F # 프로젝트를 사용한 작업 Visual Basic 또는 C# 프로젝트 작업와 크게 다르지 않습니다. 종종 F #을 사용 하는 경우 일반 Visual Studio 프로젝트 문서에서는 기본 참조로 사용할 수 있습니다. 이 항목 링크는 다른 Visual Studio 언어와 공유 되는 설정에 대 한 Visual Studio 설명서에서 관련 정보를 제공 하 고 F #에 설정도 설명 합니다.

## <a name="project-designer"></a>프로젝트 디자이너
**프로젝트 디자이너** 의 일반적인 용도 항목에 자세히 설명 되어 및 [프로젝트 디자이너 소개](https://msdn.microsoft.com/library/898dd854-c98d-430c-ba1b-a913ce3c73d7) Visual Studio 설명서에 있습니다. **프로젝트 디자이너** 관련 기능별로 그룹화 된 여러 페이지로 구성 됩니다. F # 프로젝트에 사용할 수 있는 페이지에는 대부분의 다른 언어에 사용할 수 있는 하위 집합입니다. F #에서 지원 되는 페이지는 다음 표에 설명 되어 있습니다. 사용할 수 없는 페이지는 명령줄 옵션을 변경한 경우에 사용할 수 또는 F #에서 사용할 수 없는 기능에 연결 합니다. F #에서 사용할 수 있는 페이지와 C# 페이지 가장 근접 하 게 관련 된 C#으로 제공 되는 링크 때문 **프로젝트 디자이너** 페이지.

|프로젝트 디자이너 페이지|관련된 링크|설명|
|---------------------|-------------|-----------|
|`Application`|[응용 프로그램 페이지, 프로젝트 디자이너 &#40;C&#35;&#41;](https://msdn.microsoft.com/library/ms247046.aspx)|응용 프로그램 수준 설정 및 작성 하는 경우 라이브러리 또는 실행 파일, 응용 프로그램의 대상.NET Framework의 버전, 및 리소스 파일을 하는 방법에 대 한 정보 등의 속성을 지정할 수 있도록 응용 프로그램 사용 하 여 저장 됩니다.|
|`Build`|[프로젝트 디자이너, 빌드 페이지 &#40;C&#35;&#41;](https://msdn.microsoft.com/library/kb4wyys2.aspx)|코드 컴파일 방식을 제어할 수 있습니다.|
|`Build Events`|[프로젝트 디자이너, 빌드 이벤트 페이지 &#40;C&#35;&#41;](https://msdn.microsoft.com/library/kb4wyys2.aspx)|이전 또는 이후에 컴파일 실행할 명령을 지정할 수 있습니다.|
|`Debug`|[프로젝트 디자이너, 디버그 페이지](https://msdn.microsoft.com/library/2wcdezs5.aspx)|디버깅 하는 동안 응용 프로그램을 실행 하는 방법을 제어할 수 있습니다. 이 포함 및 사용 하 여 응용 프로그램의 시작 디렉터리 무엇 인지 명령줄과 특수 디버깅 네이티브 코드 및 SQL과 같이 활성화 하 시겠습니까 모드입니다.|
|`Reference Paths`|[프로젝트의 참조 관리](/visualstudio/ide/managing-references-in-a-project)|코드에 종속 된 어셈블리를 검색할 위치를 지정할 수 있습니다.|

## <a name="f-specific-settings"></a>F #-특정 설정
다음 표에서 F #에 관련 된 설정을 요약 되어 있습니다.

|프로젝트 디자이너 페이지|설정|설명|
|---------------------|-------|-----------|
|`Build`|`Generate tail calls`|선택한 경우에 Microsoft MSIL (intermediate language) 명령의 비상 사용할 수 있습니다. 이렇게 하면 스택 프레임을 마무리 재귀 함수에 대 한 다시 사용할 수 있습니다. 에 해당 하는 `--tailcalls` 컴파일러 옵션입니다.|
|`Build`|`Other flags`|추가 컴파일러 명령줄 옵션을 지정할 수 있습니다.|

## <a name="see-also"></a>참고 항목
 [Visual Studio에서 F #으로 시작.](../get-started/get-started-visual-studio.md)  
 [컴파일러 옵션](../language-reference/compiler-options.md)  
 [프로젝트 디자이너 소개](https://msdn.microsoft.com/library/898dd854-c98d-430c-ba1b-a913ce3c73d7(v=vs.100))
