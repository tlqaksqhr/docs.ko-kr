---
title: '방법: 디자이너를 사용하여 Windows Forms ListView 컨트롤에 열 추가'
ms.date: 03/30/2017
helpviewer_keywords:
- ListView control [Windows Forms], adding column headers
- columns [Windows Forms], adding to ListView controls
ms.assetid: 5b1a8b4d-587e-479a-95c1-f9b90884f13a
ms.openlocfilehash: 83ea97b0961d158a1f3ab7a77ad2aa93732c17b9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33528397"
---
# <a name="how-to-add-columns-to-the-windows-forms-listview-control-using-the-designer"></a>방법: 디자이너를 사용하여 Windows Forms ListView 컨트롤에 열 추가
Windows Forms <xref:System.Windows.Forms.ListView> 컨트롤 각 목록에 대 한 여러 열을 표시할 수 있습니다에 때 항목는 **세부 정보** 보기. 여러 유형의 각 목록 항목에 대 한 정보를 표시 하는 열을 사용할 수 있습니다. 예를 들어 파일 이름, 파일 형식, 크기 및 파일을 마지막으로 수정한 날짜 파일의 목록을 표시할 수 있습니다. 작성 된 후 열을 채우는 방법에 대 한 정보를 참조 하십시오. [하는 방법: Windows Forms ListView 컨트롤에서 열에 하위 항목 표시](../../../../docs/framework/winforms/controls/how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)합니다.  
  
 다음 절차를 수행 하려면는 **Windows 응용 프로그램** 포함 된 폼을 사용 하 여 프로젝트는 <xref:System.Windows.Forms.ListView> 제어 합니다. 이러한 프로젝트 설정에 대 한 정보를 참조 하십시오. [하는 방법: Windows 응용 프로그램 프로젝트 만들기](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) 및 [하는 방법: Windows Forms에 컨트롤 추가](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)합니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.  
  
### <a name="to-add-columns-in-the-designer"></a>디자이너에서 열을 추가 하려면  
  
1.  에 **속성** 창의 컨트롤의 설정 <xref:System.Windows.Forms.ListView.View%2A> 속성을 <xref:System.Windows.Forms.View.Details>합니다.  
  
2.  에 **속성** 창 클릭는 **줄임표** 단추 (![VisualStudioEllipsesButton 스크린 샷](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) 옆에 <xref:System.Windows.Forms.ListView.Columns%2A> 속성입니다.  
  
     **ColumnHeader 컬렉션 편집기** 나타납니다.  
  
3.  사용 하 여는 **추가** 단추 새 열을 추가 합니다. 다음 열 머리글을 선택 하 고 해당 텍스트 (열 캡션), 텍스트 맞춤 및 두께 설정할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [ListView 컨트롤 개요](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)  
 [방법: Windows Forms ListView 컨트롤을 사용하여 항목 추가 및 제거](../../../../docs/framework/winforms/controls/how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)  
 [방법: Windows Forms ListView 컨트롤을 사용하여 열에 하위 항목 표시](../../../../docs/framework/winforms/controls/how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)  
 [방법: Windows Forms ListView 컨트롤의 아이콘 표시](../../../../docs/framework/winforms/controls/how-to-display-icons-for-the-windows-forms-listview-control.md)  
 [방법: TreeView 또는 ListView 컨트롤에 사용자 지정 정보 추가(Windows Forms)](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)
