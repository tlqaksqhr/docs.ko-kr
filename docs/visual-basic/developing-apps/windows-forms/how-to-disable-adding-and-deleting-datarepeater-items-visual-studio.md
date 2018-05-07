---
title: '방법: DataRepeater 항목 추가 및 삭제 사용 안 함(Visual Studio)'
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataRepeater, disabling delete
- DataRepeater, disabling add
ms.assetid: 298d8f60-ddfe-4361-ab66-cf76d0df5220
ms.openlocfilehash: e3d0d2a8d422054e269ee92df1fdfcb5acb96eac
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-disable-adding-and-deleting-datarepeater-items-visual-studio"></a>방법: DataRepeater 항목 추가 및 삭제 사용 안 함(Visual Studio)
기본적으로 사용자가 추가 하 고 수의 항목을 삭제 한 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 제어 합니다. 사용자가 CTRL + N을 눌러 새 항목을 추가할 수 있습니다 때는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItemEventArgs.DataRepeaterItem%2A> 포커스 했거나이 클릭 하 여는 **AddNewItem** 단추는 <xref:System.Windows.Forms.BindingNavigator> 제어 합니다. 사용자 키를 눌러 항목을 삭제할 수 있습니다 때 삭제 될는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItemEventArgs.DataRepeaterItem%2A> 포커스 했거나이 클릭 하 여는 **DeleteItem** 단추는 <xref:System.Windows.Forms.BindingNavigator> 제어 합니다.  
  
 추가 및/또는 디자인 타임 또는 런타임 시 삭제를 해제할 수 있습니다.  
  
### <a name="to-disable-adding-and-deleting-at-design-time"></a>디자인 타임에 추가 및 삭제를 사용 하지 않도록 설정 하려면  
  
1.  Windows Forms 디자이너에서 선택 된 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 제어 합니다.  
  
    > [!NOTE]
    >  컨트롤의 아래쪽 섹션을 선택 해야 합니다. 항목 템플릿 섹션을 선택 하면 다른 속성 집합이 표시 됩니다.  
  
2.  속성 창에서 설정 된 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.AllowUserToAddItems%2A> 속성을 **False**합니다.  
  
3.  설정의 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.AllowUserToDeleteItems%2A> 속성을 **False**합니다.  
  
4.  Windows Forms 디자이너에서 선택 된 <xref:System.Windows.Forms.BindingNavigator> 컨트롤을 클릭 한 다음는 **AddNewItem** 단추 (에 더하기 기호가 있는 단추).  
  
5.  속성 창에서 설정 된 <xref:System.Windows.Forms.ToolBarButton.Enabled%2A> 속성을 **False**합니다.  
  
6.  Windows Forms 디자이너에서 선택 된 <xref:System.Windows.Forms.BindingNavigator> 컨트롤을 클릭 한 다음는 **DeleteItem** 단추 (에 빨간색 X가 있는 단추).  
  
7.  속성 창에서 설정 된 <xref:System.Windows.Forms.ToolBarButton.Enabled%2A> 속성을 **False**합니다.  
  
8.  구성 요소 트레이에 선택는 <xref:System.Windows.Forms.BindingSource> 입니다는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 바인딩되어 있습니다.  
  
9. 속성 창에서 설정 된 <xref:System.Windows.Forms.BindingSource.AllowNew%2A> 속성을 **False**합니다.  
  
10. Windows Forms 디자이너에서 두 번 클릭은 **DeleteItem** 단추 코드 편집기를 엽니다.  
  
11. 이벤트 드롭 다운 목록에서 선택 된 `BindingNavigatorDeleteItem_EnabledChanged` 이벤트입니다.  
  
12. 다음 코드를 `BindingNavigatorDeleteItem_EnabledChanged` 이벤트 처리기에 추가합니다.  
  
     [!code-csharp[VbPowerPacksDataRepeaterDisableAddDelete#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio_1.cs)]
     [!code-vb[VbPowerPacksDataRepeaterDisableAddDelete#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio_1.vb)]  
  
    > [!NOTE]
    >  <xref:System.Windows.Forms.BindingSource> 로 인해 현재 레코드가 변경될 때마다 **DeleteItem** 단추가 활성화되므로 이 단계를 수행해야 합니다.  
  
### <a name="to-disable-adding-and-deleting-at-run-time"></a>실행된 시간에 추가 및 삭제를 사용 하지 않도록 설정 하려면  
  
1.  Windows Forms 디자이너에서 폼을 두 번 클릭하여 코드 편집기를 엽니다.  
  
2.  `Form_Load` 이벤트에 다음 코드를 추가합니다.  
  
     [!code-csharp[VbPowerPacksDataRepeaterDisableAddDelete#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio_2.cs)]
     [!code-vb[VbPowerPacksDataRepeaterDisableAddDelete#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio_2.vb)]  
  
3.  다음 코드를 `BindingNavigatorDeleteItem_EnabledChanged` 이벤트 처리기에 추가합니다.  
  
     [!code-csharp[VbPowerPacksDataRepeaterDisableAddDelete#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio_1.cs)]
     [!code-vb[VbPowerPacksDataRepeaterDisableAddDelete#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio_1.vb)]  
  
    > [!NOTE]
    >  <xref:System.Windows.Forms.BindingSource> 로 인해 현재 레코드가 변경될 때마다 **DeleteItem** 단추가 활성화되므로 이 단계를 수행해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
 [DataRepeater 컨트롤 소개](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)  
 [DataRepeater 컨트롤 문제 해결](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)
