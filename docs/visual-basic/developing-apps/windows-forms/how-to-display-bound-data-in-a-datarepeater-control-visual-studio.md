---
title: '방법: DataRepeater 컨트롤의 바인딩된 데이터 표시(Visual Studio)'
ms.date: 07/20/2015
helpviewer_keywords:
- DataRepeater, data-binding
- DataRepeater, displaying bound controls
ms.assetid: 56a15326-1334-4275-af4e-075cad79e6f7
ms.openlocfilehash: b96fb33a0dcf80a86d1fcb6e219e5f35b1f7351c
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2018
ms.locfileid: "42933408"
---
# <a name="how-to-display-bound-data-in-a-datarepeater-control-visual-studio"></a>방법: DataRepeater 컨트롤의 바인딩된 데이터 표시(Visual Studio)
가장 일반적인 용도 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 제어 데이터베이스 또는 다른 데이터 원본에서 바인딩된 데이터를 표시 하는 것입니다.  
  
 바인딩된 컨트롤 외에도 정적 레이블 또는 각 항목에 대해 반복 되는 이미지와 같은 다른 컨트롤을 추가 하려는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 제어 합니다. 자세한 내용은 [방법: DataRepeater 컨트롤의 바인딩되지 않은 컨트롤 표시](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md)합니다.  
  
 바인딩할 수도 있습니다 데이터 원본에 런타임 시 설정 하 여 합니다 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A> 속성을 `True` 데이터 소스를 할당 하 고는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DataSource%2A> 속성입니다. 이 경우 데이터 소스를 사용 하 여 모든 상호 작용을 관리 해야 합니다. 자세한 내용은 [DataRepeater 컨트롤의 가상 모드](../../../visual-basic/developing-apps/windows-forms/virtual-mode-in-the-datarepeater-control-visual-studio.md)합니다.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-data-bound-datarepeater"></a>데이터 바인딩된 DataRepeater를 만들려면  
  
1.  끌어서를 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 에서 제어 합니다 **Visual Basic PowerPacks** 탭에 **도구 상자** 폼 이나 컨테이너 컨트롤에.  
  
2.  핸들 크기 조정 및 위치를 끌어서 크기와 컨트롤을 배치 합니다.  
  
     컨트롤에는 두 개의 사각형 영역을 참고 합니다. 위쪽 영역은는 *항목 템플릿을*; 템플릿에 추가 된 컨트롤의 각 항목에 반복 됩니다는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 런타임 시 컨트롤입니다. 하위 지역은 합니다 *뷰포트*에 있는 항목 표시 됩니다.  
  
     또한 크기를 변경 하 여 컨트롤 또는 항목 템플릿 위치를 **크기** 하 고 **위치** 속성 창에서 속성입니다.  
  
3.  **데이터** 메뉴에서 **데이터 소스 표시**를 클릭합니다.  
  
    > [!NOTE]
    >  경우는 **데이터 원본** 창이 비어 있는 경우 데이터 소스를 추가 합니다. 자세한 내용은 [새 데이터 소스 추가](/visualstudio/data-tools/add-new-data-sources)를 참조하세요.  
  
4.  에 **데이터 원본** 창 바인딩하려는 데이터를 포함 하는 테이블에 대 한 최상위 노드를 선택 합니다.  
  
5.  테이블의 놓기 형식을 변경 `Details` 를 클릭 하 여 `Details` 테이블 노드의 드롭다운 목록에서.  
  
6.  항목 템플릿 영역으로 끌어와 테이블 노드를 선택 합니다 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 제어 합니다.  
  
     각 필드에 대 한 표시 되는 컨트롤 형식을 지정할 수 있습니다. 자세한 내용은 [데이터 소스 창에서 끌어올 때 만들 컨트롤 설정](/visualstudio/data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window)합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
 [DataRepeater 컨트롤 소개](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)  
 [방법: DataRepeater 컨트롤의 바인딩되지 않은 컨트롤 표시](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md)  
 [방법: 두 DataRepeater 컨트롤 (Visual Studio)를 사용 하 여 마스터/세부 폼 만들기](../../../visual-basic/developing-apps/windows-forms/how-to-create-a-master-detail-form-by-using-two-datarepeater-controls.md)  
 [방법: DataRepeater 컨트롤의 모양 변경](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)  
 [DataRepeater 컨트롤 문제 해결](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)
