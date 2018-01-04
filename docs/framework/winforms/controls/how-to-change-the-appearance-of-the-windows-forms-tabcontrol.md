---
title: "방법: Windows Forms TabControl의 모양 변경"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- icons [Windows Forms], displaying on tabs
- TabControl control [Windows Forms], changing page appearance
- tabs [Windows Forms], controlling appearance
- buttons [Windows Forms], displaying tabs as
ms.assetid: 7c6cc443-ed62-4d26-b94d-b8913b44f773
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 61fb11b79459da14384af974dbc403024faa377f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-change-the-appearance-of-the-windows-forms-tabcontrol"></a>방법: Windows Forms TabControl의 모양 변경
속성을 사용 하 여 Windows Forms에서 탭의 모양을 변경할 수는 <xref:System.Windows.Forms.TabControl> 및 <xref:System.Windows.Forms.TabPage> 컨트롤의 개별 탭을 구성 하는 개체입니다. 이러한 속성을 설정 하 여 탭에 이미지를 표시, 표시 하거나 수 있습니다 가로 대신 세로로 탭, 여러 행의 탭이 표시 하 고 사용 하도록 설정 탭을 프로그래밍 방식으로 사용 하지 않도록 설정 합니다.  
  
### <a name="to-display-an-icon-on-the-label-part-of-a-tab"></a>탭의 레이블 부분에 아이콘을 표시 하려면  
  
1.  추가 <xref:System.Windows.Forms.ImageList> 컨트롤을 폼입니다.  
  
2.  이미지 목록에 이미지를 추가 합니다.  
  
     이미지 목록에 대 한 자세한 내용은 참조 [ImageList 구성 요소](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md) 및 [하는 방법: Windows Forms ImageList 구성 요소와 이미지 추가 또는 제거](../../../../docs/framework/winforms/controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md)합니다.  
  
3.  설정의 <xref:System.Windows.Forms.TabControl.ImageList%2A> 속성의는 <xref:System.Windows.Forms.TabControl> 에 <xref:System.Windows.Forms.ImageList> 제어 합니다.  
  
4.  설정의 <xref:System.Windows.Forms.TabPage.ImageIndex%2A> 속성의는 <xref:System.Windows.Forms.TabPage> 목록에서 적절 한 이미지의 인덱스입니다.  
  
### <a name="to-create-multiple-rows-of-tabs"></a>여러 행의 탭을 만들려면  
  
1.  탭 페이지 수를 추가 합니다.  
  
2.  설정의 <xref:System.Windows.Forms.TabControl.Multiline%2A> 의 속성은 <xref:System.Windows.Forms.TabControl> 를 `true`합니다.  
  
3.  설정 탭 여러 행에 표시 되지 않습니다는 <xref:System.Windows.Forms.Control.Width%2A> 의 속성에서 <xref:System.Windows.Forms.TabControl> 모든 탭 보다 좁은 되도록 합니다.  
  
### <a name="to-arrange-tabs-on-the-side-of-the-control"></a>탭 컨트롤의 측면을 정렬 하려면  
  
-   설정의 <xref:System.Windows.Forms.TabControl.Alignment%2A> 의 속성은 <xref:System.Windows.Forms.TabControl> 를 <xref:System.Windows.Forms.TabAlignment.Left> 또는 <xref:System.Windows.Forms.TabAlignment.Right>합니다.  
  
### <a name="to-programmatically-enable-or-disable-all-controls-on-a-tab"></a>탭에 있는 모든 컨트롤을 사용 하지 않도록 설정 하거나 프로그래밍 방식으로 설정 하려면  
  
1.  설정의 <xref:System.Windows.Forms.TabPage.Enabled%2A> 의 속성은 <xref:System.Windows.Forms.TabPage> 를 `true` 또는 `false`합니다.  
  
    ```vb  
    TabPage1.Enabled = False  
    ```  
  
    ```csharp  
    tabPage1.Enabled = false;  
    ```  
  
    ```cpp  
    tabPage1->Enabled = false;  
    ```  
  
### <a name="to-display-tabs-as-buttons"></a>탭을 단추로 표시 하려면  
  
-   설정의 <xref:System.Windows.Forms.TabControl.Appearance%2A> 의 속성은 <xref:System.Windows.Forms.TabControl> 를 <xref:System.Windows.Forms.TabAppearance.Buttons> 또는 <xref:System.Windows.Forms.TabAppearance.FlatButtons>합니다.  
  
## <a name="see-also"></a>참고 항목  
 [TabControl 컨트롤](../../../../docs/framework/winforms/controls/tabcontrol-control-windows-forms.md)  
 [TabControl 컨트롤 개요](../../../../docs/framework/winforms/controls/tabcontrol-control-overview-windows-forms.md)  
 [방법: 탭 페이지에 컨트롤 추가](../../../../docs/framework/winforms/controls/how-to-add-a-control-to-a-tab-page.md)  
 [방법: 탭 페이지 사용 안 함](../../../../docs/framework/winforms/controls/how-to-disable-tab-pages.md)  
 [방법: Windows Forms TabControl을 사용하여 탭 추가 및 제거](../../../../docs/framework/winforms/controls/how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)
