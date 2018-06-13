---
title: DataRepeater 컨트롤 문제 해결(Visual Studio)
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataRepeater, troubleshooting
ms.assetid: c0ab9469-eced-4f52-aa18-4bd8dd4f1a9a
ms.openlocfilehash: 092bbe89bb73a40dee7161f014d40a581b0ddc06
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33591900"
---
# <a name="troubleshooting-the-datarepeater-control-visual-studio"></a>DataRepeater 컨트롤 문제 해결(Visual Studio)
이 항목에서는 사용 하 여 작업할 때 발생할 수 있는 일반적인 문제는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 제어 합니다.  
  
## <a name="datarepeater-keyboard-and-mouse-events-are-not-raised"></a>DataRepeater 키보드 및 마우스 이벤트는 발생 하지 않습니다.  
 일부 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 키보드 및 마우스 이벤트와 같은 제어 이벤트가 발생 하지 않습니다. 이것은 의도적인 것입니다. <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 컨트롤 자체에 대 한 컨테이너는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> 개체 및 런타임 시 액세스할 수 없습니다. <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> 디자인 타임에 이벤트를 노출 하지 않습니다. 따라서 항목을 클릭 하거나 항목에 포커스가 있을 때 키를 누르면는 이벤트를 발생 하지 않습니다.  
  
 경우이 예외는 <xref:System.Windows.Forms.Control.Padding%2A> 속성이 큰 충분 한 값의 가장자리를 노출 하는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 제어 합니다. 이 경우에 노출 된 여백을 클릭 하면 마우스 이벤트를 발생 합니다.  
  
 이 문제를 해결 하려면 추가 <xref:System.Windows.Forms.Panel> 컨트롤을 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> 의 섹션은 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 컨트롤을 선택한 다음 컨트롤의 나머지 부분을 추가 <xref:System.Windows.Forms.Panel>합니다. 코드를 추가할 수 있습니다는 <xref:System.Windows.Forms.Panel> 키보드 및 마우스 이벤트에 대 한 컨트롤의 이벤트 처리기입니다.  
  
## <a name="the-datarepeater-is-partially-hidden-behind-the-binding-navigator"></a>DataRepeater는 바인딩 탐색기 뒤에 숨겨지지 부분적으로  
 처음 추가 하면 한 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 폼 컨트롤을 추가한 다음에서 데이터 바인딩된 컨트롤 추가 **데이터 원본** 창은 <xref:System.Windows.Forms.BindingNavigator> 컨트롤 위쪽에 표시 될 수 있습니다는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 제어 합니다. 이것은 알려진된 제한은 **데이터 원본** 창은와 같은 다른 컨트롤의 동작과 일치 하 고는 <xref:System.Windows.Forms.DataGridView> 제어 합니다.  
  
 이동 하거나 수는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 보다 낮은 <xref:System.Windows.Forms.BindingNavigator> 디자인 타임에 컨트롤 또는 코드에 다음과 같은 추가 `Load` 이벤트 처리기입니다.  
  
```vb  
DataRepeater1.Top = ProductsBindingNavigator.Height  
```  
  
```csharp  
dataRepeater1.Top = productsBindingNavigator.Height;  
```  
  
## <a name="controls-are-not-displayed-correctly-at-run-time"></a>런타임 시 컨트롤 올바르게 표시 되지 않습니다.  
 일부 컨트롤에는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 컨트롤이 실행 시 예상 대로 표시 되지 않을 수 있습니다. 컨트롤을 복제 하는 데 사용 하는 프로세스는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> 에 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> 항상 모든 컨트롤의 모든 속성을 확인할 수 없습니다. 예를 들어, 바인딩되지 않은 추가 하는 경우 <xref:System.Windows.Forms.ListBox> 컨트롤을 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 디자인 타임에 컨트롤을 채울 해당 <xref:System.Windows.Forms.ListBox.Items%2A> 목록으로 구성 된 컬렉션의 <xref:System.Windows.Forms.ListBox> 런타임 시 비어 있게 됩니다. 이 수 없기 때문에 복제 프로세스 계정에는 <xref:System.Windows.Forms.ListBox.Items%2A> 속성입니다.  
  
 누락 된 속성을 복원 하 여 이와 같은 문제를 해결할 수는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemCloned> 기본 복제가 완료 된 후에 발생 하는 이벤트입니다. 다음 예제에서는 복구 하는 <xref:System.Windows.Forms.ListBox.Items%2A> 의 컬렉션은 <xref:System.Windows.Forms.ListBox> 컨트롤에 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemCloned> 이벤트 처리기.  
  
 [!code-csharp[VbPowerPacksDataRepeaterItemCloned#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/troubleshooting-the-datarepeater-control-visual-studio_1.cs)]
 [!code-vb[VbPowerPacksDataRepeaterItemCloned#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/troubleshooting-the-datarepeater-control-visual-studio_1.vb)]  
  
## <a name="the-selection-symbol-on-the-item-header-is-missing"></a>항목 헤더에 선택 기호가 없거나  
 변경 될 때는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A> 속성에 있는 항목 헤더의는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 컨트롤을 선택할 수 있는 몇 가지 색 선택 기호가 표시 되지 않을 수 있습니다. 변경 된 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderSize%2A> 속성 선택 기호 사라질 때까지 발생할 수 있습니다.  
  
 선택 기호의 크기와 색을 변경할 수 없습니다.  
  
-   설정 하는 경우는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A> 를 <xref:System.Drawing.Color.White%2A>, 항목을 먼저 선택한 경우 선택 기호가 표시 되지 것입니다.  
  
-   설정 하는 경우는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A> 를 <xref:System.Drawing.Color.Black%2A>, 컨트롤을 선택 하 고 컨트롤이 편집 모드일 때 연필 기호가 표시 되지 것입니다 선택 기호가 표시 되지 것입니다.  
  
-   경우는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderSize%2A> 속성이 11 보다 작은 값으로 설정 되 면 표시기 기호 항목 머리글에서 표시 되지 것입니다.  
  
 헤더 및 선택 사용자 고유의 항목 기호로 사용 하 여 제공할 수 있습니다는 <xref:System.Windows.Forms.PictureBox> 제어 및 모니터링는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem.IsCurrent%2A> 속성은 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> 에 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> 의 이벤트는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 제어 합니다. 자세한 내용은 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem.IsCurrent%2A>을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [DataRepeater 컨트롤 소개](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)  
 [방법: DataRepeater 컨트롤의 바인딩된 데이터 표시](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md)  
 [방법: DataRepeater 컨트롤의 바인딩되지 않은 컨트롤 표시](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md)  
 [방법: DataRepeater 컨트롤의 레이아웃 변경](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-layout-of-a-datarepeater-control-visual-studio.md)  
 [방법: DataRepeater 컨트롤의 모양 변경](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)  
 [방법: DataRepeater 컨트롤의 항목 머리글 표시](../../../visual-basic/developing-apps/windows-forms/how-to-display-item-headers-in-a-datarepeater-control-visual-studio.md)  
 [방법: DataRepeater 항목 추가 및 삭제 사용 안 함](../../../visual-basic/developing-apps/windows-forms/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio.md)  
 [방법: DataRepeater 컨트롤의 데이터 검색](../../../visual-basic/developing-apps/windows-forms/how-to-search-data-in-a-datarepeater-control-visual-studio.md)  
 [방법: 두 DataRepeater 컨트롤 (Visual Studio)를 사용 하 여 마스터/세부 폼 만들기](../../../visual-basic/developing-apps/windows-forms/how-to-create-a-master-detail-form-by-using-two-datarepeater-controls.md)
