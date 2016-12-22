---
title: "How to: Disable Adding and Deleting DataRepeater Items (Visual Studio) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "DataRepeater, disabling delete"
  - "DataRepeater, disabling add"
ms.assetid: 298d8f60-ddfe-4361-ab66-cf76d0df5220
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# How to: Disable Adding and Deleting DataRepeater Items (Visual Studio)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

기본적으로 사용자는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 컨트롤에서 항목을 추가하고 삭제할 수 있습니다.  <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItemEventArgs.DataRepeaterItem%2A>에 포커스가 있을 때 Ctrl\+N을 누르거나 <xref:System.Windows.Forms.BindingNavigator> 컨트롤에서 **AddNewItem** 단추를 클릭하여 새 항목을 추가할 수 있습니다.  <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItemEventArgs.DataRepeaterItem%2A>에 포커스가 있을 때 Delete 키를 누르거나 <xref:System.Windows.Forms.BindingNavigator> 컨트롤에서 **DeleteItem** 단추를 클릭하여 항목을 삭제할 수 있습니다.  
  
 디자인 타임 또는 런타임에 추가 및\/또는 삭제 기능을 비활성화할 수 있습니다.  
  
### 디자인 타임에 추가 및 삭제 기능을 비활성화하려면  
  
1.  Windows Forms 디자이너에서 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 컨트롤을 선택합니다.  
  
    > [!NOTE]
    >  컨트롤의 아래 섹션을 선택해야 합니다.  항목 템플릿 섹션을 선택하면 다른 속성 집합이 표시됩니다.  
  
2.  속성 창에서 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.AllowUserToAddItems%2A> 속성을 **False**로 설정합니다.  
  
3.  <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.AllowUserToDeleteItems%2A> 속성을 **False**로 설정합니다.  
  
4.  Windows Forms 디자이너에서 <xref:System.Windows.Forms.BindingNavigator> 컨트롤을 선택한 다음 **AddNewItem** 단추\(더하기 기호가 있는 단추\)를 클릭합니다.  
  
5.  속성 창에서 <xref:System.Windows.Forms.ToolBarButton.Enabled%2A> 속성을 **False**로 설정합니다.  
  
6.  Windows Forms 디자이너에서 <xref:System.Windows.Forms.BindingNavigator> 컨트롤을 선택한 다음 **DeleteItem** 단추\(빨강 X 표시가 있는 단추\)를 클릭합니다.  
  
7.  속성 창에서 <xref:System.Windows.Forms.ToolBarButton.Enabled%2A> 속성을 **False**로 설정합니다.  
  
8.  구성 요소 트레이에서 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>가 바인딩되는 <xref:System.Windows.Forms.BindingSource>를 선택합니다.  
  
9. 속성 창에서 <xref:System.Windows.Forms.BindingSource.AllowNew%2A> 속성을 **False**로 설정합니다.  
  
10. Windows Forms 디자이너에서 **DeleteItem** 단추를 두 번 클릭하여 코드 편집기를 엽니다.  
  
11. 오른쪽 드롭다운 목록에서 `BindingNavigatorDeleteItem_EnabledChanged` 이벤트를 선택합니다.  
  
12. `BindingNavigatorDeleteItem_EnabledChanged` 이벤트 처리기에 다음 코드를 추가합니다.  
  
     [!code-cs[VbPowerPacksDataRepeaterDisableAddDelete#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio_1.cs)]
     [!code-vb[VbPowerPacksDataRepeaterDisableAddDelete#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio_1.vb)]  
  
    > [!NOTE]
    >  <xref:System.Windows.Forms.BindingSource>로 인해 현재 레코드가 변경될 때마다 **DeleteItem** 단추가 활성화되므로 이 단계를 수행해야 합니다.  
  
### 런타임 타임에 추가 및 삭제 기능을 비활성화하려면  
  
1.  Windows Forms 디자이너에서 폼을 두 번 클릭하여 코드 편집기를 엽니다.  
  
2.  `Form_Load` 이벤트에 다음 코드를 추가합니다.  
  
     [!code-cs[VbPowerPacksDataRepeaterDisableAddDelete#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio_2.cs)]
     [!code-vb[VbPowerPacksDataRepeaterDisableAddDelete#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio_2.vb)]  
  
3.  `BindingNavigatorDeleteItem_EnabledChanged` 이벤트 처리기에 다음 코드를 추가합니다.  
  
     [!code-cs[VbPowerPacksDataRepeaterDisableAddDelete#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio_1.cs)]
     [!code-vb[VbPowerPacksDataRepeaterDisableAddDelete#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio_1.vb)]  
  
    > [!NOTE]
    >  <xref:System.Windows.Forms.BindingSource>로 인해 현재 레코드가 변경될 때마다 **DeleteItem** 단추가 활성화되므로 이 단계를 수행해야 합니다.  
  
## 참고 항목  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>   
 [Introduction to the DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)   
 [Troubleshooting the DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)