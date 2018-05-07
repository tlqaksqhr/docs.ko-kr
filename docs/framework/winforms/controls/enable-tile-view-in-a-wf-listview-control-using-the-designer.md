---
title: '방법: 디자이너를 사용하여 Windows Forms ListView 컨트롤에서 Tile 보기 사용'
ms.date: 03/30/2017
helpviewer_keywords:
- tile view feature
- ListView control [Windows Forms], tile view
- tiling [Windows Forms], Windows Forms, controls
ms.assetid: 12f0816a-52b8-41ee-a6d9-ded3a8a5817a
ms.openlocfilehash: 836d82930c7ff41e7a4ae64a577baa5f1ba780c2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-enable-tile-view-in-a-windows-forms-listview-control-using-the-designer"></a>방법: 디자이너를 사용하여 Windows Forms ListView 컨트롤에서 Tile 보기 사용
바둑판식 뷰 기능은 <xref:System.Windows.Forms.ListView> 제어를 통해 그래픽 정보와 텍스트 정보 간의 시각적 균형을 제공할 수 있습니다. 바둑판식 뷰에서 항목에 대해 표시되는 텍스트 정보는 세부 정보 뷰에 대해 정의된 열 정보와 같습니다. 다음 함수를 함께 그룹화 또는 삽입 타일 보기에 기능을 표시할는 <xref:System.Windows.Forms.ListView> 제어 합니다.  
  
 바둑판식 뷰는 다음 그림에 나와 있는 것 처럼 32 x 32 아이콘과 여러 줄의 텍스트를 사용 합니다.  
  
 ![ListView 컨트롤의 tile 보기](../../../../docs/framework/winforms/controls/media/listviewtile.gif "ListViewTile")  
  
 Tile 보기 속성 및 메서드 사용 전체적으로 크기와 tile 보기 창 내에서 모든 항목의 모양을 제어 하려면 각 항목에 대해 표시할 열 필드를 지정할 수 있습니다. 명확성을 위해 첫 번째 텍스트 줄을 타일에는 항상 해당 항목의 이름입니다. 변경할 수 없습니다.  
  
 다음 절차를 수행 하려면는 **Windows 응용 프로그램** 포함 된 폼을 사용 하 여 프로젝트는 <xref:System.Windows.Forms.ListView> 제어 합니다. 이러한 프로젝트 설정에 대 한 정보를 참조 하십시오. [하는 방법: Windows 응용 프로그램 프로젝트 만들기](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) 및 [하는 방법: Windows Forms에 컨트롤 추가](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)합니다.  
  
> [!NOTE]
>  바둑판식 뷰는 응용 프로그램이 <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> 메서드를 호출할 때 [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)]에서만 사용할 수 있습니다. 이전 운영 체제에서는 바둑판식 뷰와 관련된 코드가 아무 효과도 없으며, <xref:System.Windows.Forms.ListView> 컨트롤이 큰 아이콘 보기에 표시됩니다. 자세한 내용은 <xref:System.Windows.Forms.ListView.View%2A?displayProperty=nameWithType>을 참조하세요.  
>   
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.  
  
### <a name="to-set-tile-view-in-the-designer"></a>디자이너에서 tile 보기를 설정 하려면  
  
1.  선택 된 <xref:System.Windows.Forms.ListView> 폼의 컨트롤로 합니다.  
  
2.  에 **속성** 창에서는 <xref:System.Windows.Forms.ListView.View%2A> 속성 선택 **타일**합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.ListView.TileSize%2A>  
 [Windows XP 기능 및 Windows Forms 컨트롤](http://msdn.microsoft.com/library/bc7fab94-fce9-4bf1-a8ad-a5837c91c3c0)  
 [ListView 컨트롤 개요](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)
