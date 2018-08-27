---
title: Visual Studio에서 인식 되는 DPI를 사용 하지 않도록 설정
description: HDPI 모니터에 Windows Forms 디자이너 및 DPI를 인식 하지 못하는 프로세스로 Visual Studio를 실행 하는 방법의 제한 사항에 설명 합니다.
ms.date: 08/14/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-designers
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: 65c997e12aa033b3b08d32c8ab76372e3c52a803
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2018
ms.locfileid: "42936552"
---
# <a name="disable-dpi-awareness-in-visual-studio"></a>Visual Studio에서 인식 되는 DPI를 사용 하지 않도록 설정

Visual Studio는 dpi 인식 응용 프로그램에 자동으로 표시 배율을 즉 인치당입니다. 응용 프로그램에서 DPI에서 인식 되지 않으면 알 경우 운영 체제에 비트맵으로 응용 프로그램을 확장 합니다. 이 동작은 DPI 가상화를 라고도 합니다. 응용 프로그램이 여전히 100% 배율 조정 또는 96dpi에서 실행 되 고 있는지 것으로 생각 합니다.

## <a name="windows-forms-designer-on-hdpi-monitors"></a>HDPI 모니터에 Windows Forms 디자이너

합니다 **Windows Forms 디자이너** Visual Studio에 없는 확장 지원 합니다. 이 인해 표시 문제에서 몇 가지 형태를 열면 합니다 **Windows Forms 디자이너** hdpi 모니터 인치당 높은에서. 예를 들어 다음 그림에 나와 있는 것 처럼 중복 컨트롤 나타날 수 있습니다.

![HDPI 모니터에서 Windows Forms 디자이너](media/disable-dpi-awareness-visual-studio/win-forms-designer-hdpi.png)

Visual Studio 2017 버전 15.8 및 나중에 폼을 여는 경우에 **Windows Forms 디자이너** HDPI 모니터를에서 Visual Studio 디자이너의 맨 위에 있는 노란색 표시줄 정보를 표시 합니다.

![DPI를 인식 하지 못하는 모드에서 다시 시작 하려면 Visual Studio의 정보 표시줄](media/disable-dpi-awareness-visual-studio/scaling-gold-bar.png)

메시지 읽고 **기본 디스플레이에 크기 조정 (192dpi) 200%로 설정 됩니다. 디자이너 창에서 렌더링 문제를 발생할 수 있습니다이 있습니다.**

디자이너에서 작동 하지 않는 경우 폼의 레이아웃을 조정할 필요가 없습니다 정보 표시줄을 무시 하 고 다른 형식의 디자이너 또는 코드 편집기에서 작업을 계속할 수 있습니다. 만 **Windows Forms 디자이너** 영향을 받습니다. 작업할 필요가 없는 경우는 **Windows Forms 디자이너**, 다음 섹션에서는 도움이 [문제를 해결](#to-resolve-the-problem)합니다.

## <a name="to-resolve-the-problem"></a>문제를 해결 하려면

표시 문제를 해결 하는 방법은 세 가지가 있습니다.

### <a name="restart-visual-studio-as-a-dpi-unaware-process"></a>DPI를 인식 하지 못하는 프로세스로 Visual Studio를 다시 시작

DPI를 인식 하지 못하는 프로세스로 노란색 정보 모음에서 옵션을 선택 하면 Visual Studio를 다시 시작할 수 있습니다. 이 기본 방법은 문제를 해결 합니다.

Visual Studio DPI를 인식 하지 못하는 프로세스로 실행 되 면 디자이너 레이아웃 문제가 해결 되 면 있지만 글꼴 희미하게 보일 수 있습니다. Visual Studio는 DPI를 인식 하지 못하는 프로세스로 실행 될 때 다른 노란색 정보 메시지를 표시 **Visual Studio DPI를 인식 하지 못하는 프로세스로 실행 됩니다. WPF 및 XAML 디자이너를 제대로 표시 되지 않을 수 있습니다.** 정보 표시줄 하는 옵션도 제공 **DPI 인식 프로세스로 Visual Studio를 다시 시작**합니다.

> [!NOTE]
> - DPI를 인식 하지 못하는 프로세스로 다시 시작 하는 옵션을 선택 하면 Visual Studio 도구 창 도킹 되지 않았는지 있었습니다, 해당 도구 창의 위치 변경 될 수 있습니다.
> - 있는 경우 또는 Visual Basic 기본 프로필을 사용 하는 경우는 **만들어질 때 새 프로젝트 저장** 옵션의 선택을 취소 **도구** > **옵션**  >  **프로젝트 및 솔루션**, DPI를 인식 하지 못하는 프로세스로 다시 시작 될 때 Visual Studio 프로젝트를 다시 열 수 없습니다. 아래에서 선택 하 여 프로젝트를 열 수는 있지만 **파일** > **최근 프로젝트 및 솔루션**합니다.

작업 완료 되 면 DPI 인식 프로세스로 Visual Studio를 다시 시작 해야 합니다 **Windows Forms 디자이너**합니다. DPI를 인식 하지 못하는 프로세스로 실행 중인 경우 글꼴 흐리게 수 및와 같은 문제를 다른 디자이너에 표시 될 수 있습니다 합니다 **XAML 디자이너**합니다. 닫고 DPI를 인식 하지 못하는 모드에서 실행 되는 경우에 Visual Studio를 다시 열 경우 됩니다 DPI 인식 다시 합니다. 클릭할 수도 있습니다는 **DPI 인식 프로세스로 Visual Studio를 다시 시작** 정보 표시줄에 대 한 옵션입니다.

### <a name="add-a-registry-entry"></a>레지스트리 항목을 추가 합니다.

레지스트리를 수정 하 여 DPI를 인식 하지 못하는으로 Visual Studio를 표시할 수 있습니다. 열기 **레지스트리 편집기** 항목을 추가 합니다 **실행 NT\CurrentVersion\AppCompatFlags\Layers** 하위 키:

**항목**: %ProgramFiles (x86) %\Microsoft Visual Studio\2017\your-edition\Common7\IDE\devenv.exe

**형식**: REG_SZ

**값**: DPIUNAWARE

> [!NOTE]
> Visual Studio는 레지스트리 항목을 제거할 때까지 DPI를 인식 하지 못하는 모드로 유지 됩니다.

### <a name="set-your-display-scaling-setting-to-100"></a>디스플레이 설정을 100%로 크기 조정 설정

Windows 10에서 100%로 설정 크기 조정 하 여 표시를 설정 하려면 다음을 입력 **설정 표시** 작업 표시줄을 선택 하 고 검색 상자에에서 **표시 설정 변경**합니다. 에 **설정을** 창에서 **텍스트, 앱 및 기타 항목의 크기를 변경** 에 **100%** 합니다.

100%로 크기 조정 디스플레이 설정 적절 하지 않을, 있으므로 사용자 인터페이스를 사용할 수 있으려면 너무 작습니다.

## <a name="see-also"></a>참고자료

- [Windows Forms의 자동 크기 조정](automatic-scaling-in-windows-forms.md)