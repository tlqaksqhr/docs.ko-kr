---
title: '방법: 탭 페이지에 컨트롤 추가'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- TabPage control
- tab controls [Windows Forms], tab order
- tab pages [Windows Forms], adding controls
ms.assetid: b092532e-7346-469f-b9a1-897f9bea4fb7
ms.openlocfilehash: 1bb2233cf9e288ae89ebb8cab3df4f6451dc8eed
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-add-a-control-to-a-tab-page"></a>방법: 탭 페이지에 컨트롤 추가
Windows Forms를 사용 하 여 <xref:System.Windows.Forms.TabControl> 조직화 방식으로 다른 컨트롤을 표시 합니다. 다음 절차에는 첫 번째 탭에 단추를 추가 하는 방법을 보여 줍니다. 탭 페이지의 레이블이 부분에 아이콘을 추가 하는 방법에 대 한 정보를 참조 하십시오. [하는 방법: Windows Forms TabControl의 모양 변경](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)합니다.  
  
### <a name="to-add-a-control-programmatically"></a>프로그래밍 방식으로 컨트롤을 추가 하려면  
  
1.  사용 하 여는 <xref:System.Windows.Forms.Control.ControlCollection.Add%2A> 에서 반환 된 컬렉션의 메서드는 <xref:System.Windows.Forms.Control.Controls%2A> 속성 <xref:System.Windows.Forms.TabPage>:  
  
     [!code-cpp[TabPageControlCollectionHowToAdd#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/tabpagecontrolcollectionhowtoadd/cpp/add.cpp#1)]
     [!code-csharp[TabPageControlCollectionHowToAdd#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/tabpagecontrolcollectionhowtoadd/cs/add.cs#1)]
     [!code-vb[TabPageControlCollectionHowToAdd#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/tabpagecontrolcollectionhowtoadd/vb/add.vb#1)]  
  
## <a name="see-also"></a>참고 항목  
 [TabControl 컨트롤](../../../../docs/framework/winforms/controls/tabcontrol-control-windows-forms.md)  
 [TabControl 컨트롤 개요](../../../../docs/framework/winforms/controls/tabcontrol-control-overview-windows-forms.md)  
 [방법: Windows Forms TabControl의 모양 변경](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)  
 [방법: 탭 페이지 사용 안 함](../../../../docs/framework/winforms/controls/how-to-disable-tab-pages.md)  
 [방법: Windows Forms TabControl을 사용하여 탭 추가 및 제거](../../../../docs/framework/winforms/controls/how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)
