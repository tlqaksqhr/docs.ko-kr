---
title: '방법: Windows Forms에 컨트롤 고정'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls, locking
- controls [Windows Forms], locking
ms.assetid: 94efe0d2-c14e-4d14-b903-63ea9b07e290
ms.openlocfilehash: f05da53f134f13bf5edbbe7ab8c5973f79bbca4f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33534747"
---
# <a name="how-to-lock-controls-to-windows-forms"></a>방법: Windows Forms에 컨트롤 고정
Windows 응용 프로그램의 사용자 인터페이스 (UI)를 디자인할 때 않습니다 잘못 이동 하거나 다른 속성을 설정 하는 경우 크기를 조정할 수 있도록 올바르게 배치 되 면 컨트롤을 잠글 수 있습니다.  
  
 또한 잠금 및 많은 컨트롤을 사용 하 여 양식을 하는 데 도움이 되는 폼을 한 번에에 있는 모든 컨트롤 또는 개별 컨트롤의 잠금을 해제할 수 있습니다. 모든 컨트롤 배치 했으면 양식에서 원하는 위치를 모두 잠그면 실수로 이동 하지 못하도록 차단할 수 있습니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.  
  
### <a name="to-lock-a-control"></a>컨트롤을 잠그려면  
  
1.  에 **속성** 창 클릭는 **잠금** 속성과 선택 `true`합니다. (이름을 두 번 속성 설정이 전환 됩니다.)  
  
     또는 컨트롤을 마우스 오른쪽 단추로 클릭 하 고 선택 **잠금 컨트롤**합니다.  
  
    > [!NOTE]
    >  컨트롤을 잠그면 디자인 화면에서 새 크기 또는 위치에 끌어 올 수 있습니다. 그러나 변경할 수 있습니다 크기 또는 방법으로 컨트롤의 위치는 **속성** 창 또는 코드입니다.  
  
### <a name="to-lock-all-the-controls-on-a-form"></a>폼에 있는 모든 컨트롤을 잠그려면  
  
1.  **형식** 메뉴 선택 **잠금 컨트롤**합니다.  
  
    > [!NOTE]
    >  이 명령은 폼 컨트롤은 때문에 해당 폼의 크기를 잠급니다.  
  
### <a name="to-unlock-all-locked-controls-on-a-form"></a>양식의 모든된 컨트롤의 잠금을 해제 하려면  
  
1.  **형식** 메뉴 선택 **잠금 컨트롤**합니다.  
  
     모든 이전에 잠긴된 컨트롤 형식에는 이제 잠금이 해제 합니다.  
  
### <a name="to-unlock-locked-controls-individually"></a>잠긴된 컨트롤을 개별적으로 잠금을 해제 하려면  
  
1.  에 **속성** 창 클릭는 **잠금** 속성과 선택 `false`합니다. (이름을 두 번 속성 설정이 전환 됩니다.)  
  
## <a name="see-also"></a>참고 항목  
 [Windows Forms 컨트롤](../../../../docs/framework/winforms/controls/index.md)  
 [Windows Forms에서 컨트롤 정렬](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)  
 [개별 Windows Forms 컨트롤 레이블 지정 및 바로 가기 제공](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)  
 [Windows Forms에 사용할 수 있는 컨트롤](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 [기능별 Windows Forms 컨트롤](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)
