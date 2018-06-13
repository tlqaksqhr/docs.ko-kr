---
title: '방법: 끌어 온 GridView 열 머리글의 스타일 만들기'
ms.date: 03/30/2017
helpviewer_keywords:
- ListView controls [WPF], styling
ms.assetid: 0b999645-0313-4b33-80b9-19ece08b5459
ms.openlocfilehash: 2e57b4cb1b8ddb90e8e6e0abc6db3e7f0b864cfa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33554575"
---
# <a name="how-to-create-a-style-for-a-dragged-gridview-column-header"></a>방법: 끌어 온 GridView 열 머리글의 스타일 만들기
끌어 온의 모양을 변경 하는 방법을 보여 주는이 예제 <xref:System.Windows.Controls.GridViewColumnHeader> 사용자 열 위치를 변경 하는 경우.  
  
## <a name="example"></a>예제  
 열 머리글의 다른 위치로 끌어 올 때는 <xref:System.Windows.Controls.ListView> 사용 하 여 <xref:System.Windows.Controls.GridView> 보기 모드에 대 한 열을 새 위치로 이동 합니다. 열 머리글을 끄는 동안 부동 머리글의 복사본이 원래 머리글 외에도 나타납니다. 열 머리글에는 <xref:System.Windows.Controls.GridView> 로 표시 됩니다는 <xref:System.Windows.Controls.GridViewColumnHeader> 개체입니다.  
  
 부동 및 원래 머리글의 모양을 사용자 지정 하려면 설정할 수 있습니다 <xref:System.Windows.Controls.ControlTemplate.Triggers%2A> 수정 하는 <xref:System.Windows.Controls.GridViewColumnHeader> <xref:System.Windows.Style>합니다. 이러한 <xref:System.Windows.Controls.ControlTemplate.Triggers%2A> 때 적용 되는 <xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A> 속성 값은 `true` 및 <xref:System.Windows.Controls.GridViewColumnHeader.Role%2A> 속성 값은 <xref:System.Windows.Controls.GridViewColumnHeaderRole.Floating>합니다.  
  
 사용자가 마우스 단추를 누를 한 누르고 위에 마우스를 일시 중지할 경우는 <xref:System.Windows.Controls.GridViewColumnHeader>, <xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A> 속성 값이 변경 `true`합니다. 마찬가지로, 사용자 끌기 작업 시작는 <xref:System.Windows.Controls.GridViewColumnHeader.Role%2A> 속성 변경 <xref:System.Windows.Controls.GridViewColumnHeaderRole.Floating>합니다.  
  
 다음 예제에서는 설정 하는 방법을 보여 줍니다. <xref:System.Windows.Controls.ControlTemplate.Triggers%2A> 변경 하는 <xref:System.Windows.Controls.Control.Foreground%2A> 및 <xref:System.Windows.Controls.Control.Background%2A> 사용자가을 새 위치로 열을 끌 때 원래와 부동 머리글의 색입니다.  
  
 [!code-xaml[ListViewHeaderRoleStyle#GVCHControlTemplateStart](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#gvchcontroltemplatestart)]  
[!code-xaml[ListViewHeaderRoleStyle#ControlTemplateTriggersStart](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#controltemplatetriggersstart)]  
[!code-xaml[ListViewHeaderRoleStyle#IsPressed](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#ispressed)]  
[!code-xaml[ListViewHeaderRoleStyle#Floating](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#floating)]  
[!code-xaml[ListViewHeaderRoleStyle#ControlTemplateTriggersEnd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#controltemplatetriggersend)]  
[!code-xaml[ListViewHeaderRoleStyle#GVCHControlTemplateEnd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#gvchcontroltemplateend)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Controls.GridViewColumnHeader>  
 <xref:System.Windows.Controls.GridViewColumnHeaderRole>  
 <xref:System.Windows.Controls.ListView>  
 <xref:System.Windows.Controls.GridView>  
 [방법 항목](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)  
 [ListView 개요](../../../../docs/framework/wpf/controls/listview-overview.md)  
 [GridView 개요](../../../../docs/framework/wpf/controls/gridview-overview.md)
