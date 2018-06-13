---
title: '방법: MDI 자식 폼 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- MDI [Windows Forms], creating forms
- child forms
ms.assetid: 164b69bb-2eca-4339-ada3-0679eb2c6dda
ms.openlocfilehash: d4351e88de896f366ae2c4050f0e1c32aa0188a9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33527501"
---
# <a name="how-to-create-mdi-child-forms"></a>방법: MDI 자식 폼 만들기
MDI 자식 폼의 중요 한 요소는 [다중 문서 MDI (인터페이스) 응용 프로그램](../../../../docs/framework/winforms/advanced/multiple-document-interface-mdi-applications.md)사용자 상호 작용의 중심 이므로, 합니다.  
  
 다음 절차에서는 대부분의 워드프로세싱 응용 프로그램과 비슷하게 <xref:System.Windows.Forms.RichTextBox> 컨트롤을 표시하는 MDI 자식 폼을 만듭니다. <xref:System.Windows.Forms> 컨트롤을 <xref:System.Windows.Forms.DataGridView> 컨트롤과 같은 다른 컨트롤이나 컨트롤 혼합으로 대체하면 다양한 가능성을 가진 MDI 자식 창(및 확장을 통해 MDI 응용 프로그램)을 만들 수 있습니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.  
  
### <a name="to-create-mdi-child-forms"></a>MDI 자식 폼을 만들려면  
  
1.  새 Windows Forms 프로젝트를 만듭니다. **속성 창** 폼에 대 한 설정의 <xref:System.Windows.Forms.Form.IsMdiContainer%2A> 속성을 `true`, 및 해당 `WindowsState` 속성을 `Maximized`합니다.  
  
     그러면 폼이 자식 창의 MDI 컨테이너로 지정됩니다.  
  
2.  `Toolbox`에서 <xref:System.Windows.Forms.MenuStrip> 컨트롤을 폼으로 끌어서 놓습니다. 설정의 `Text` 속성을 **파일**합니다.  
  
3.  옆에 있는 줄임표 (...)는 **항목** 속성과 클릭 **추가** 두 자식 도구 스트립 메뉴 항목을 추가 합니다. 설정의 `Text` 속성에 이들이 항목에 대 한 **새로** 및 **창**합니다.  
  
4.  **솔루션 탐색기**프로젝트를 마우스 오른쪽 단추로 가리킨 **추가**를 선택한 후 **새 항목 추가**합니다.  
  
5.  에 **새 항목 추가** 대화 상자에서 **Windows Form** (Visual basic에서 또는 Visual C#) 또는 **Windows Forms 응용 프로그램 (.NET)** (에서 [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)])는 에서 **템플릿** 창. 에 **이름** 상자, 폼의 이름을 **Form2**합니다. 클릭는 **열려** 단추를 프로젝트에 폼을 추가 합니다.  
  
    > [!NOTE]
    >  이 단계에서 만든 MDI 자식 폼은 표준 Windows Form입니다. 따라서 폼의 투명도를 제어할 수 있는 <xref:System.Windows.Forms.Form.Opacity%2A> 속성이 있습니다. 그러나 <xref:System.Windows.Forms.Form.Opacity%2A> 속성은 최상위 창에 사용하도록 설계되었습니다. 그리기 문제가 발생할 수 있으므로 MDI 자식 폼에는 사용하지 마세요.  
  
     이 폼은 MDI 자식 폼에 대한 템플릿이 됩니다.  
  
     **Windows Forms 디자이너** 열리는지 **Form2**합니다.  
  
6.  **도구 상자**를 끌어 한 **RichTextBox** 컨트롤을 폼입니다.  
  
7.  에 **속성** 창에서 설정 된 `Anchor` 속성을 **위쪽, 왼쪽** 및 `Dock` 속성을 **채우기**합니다.  
  
     이렇게 하면 폼의 크기를 조정하는 경우에도 <xref:System.Windows.Forms.RichTextBox> 컨트롤이 MDI 자식 폼의 영역을 완전히 채웁니다.  
  
8.  두 번 클릭는 **새로** 만들려는 메뉴 항목은 <xref:System.Windows.Forms.Control.Click> 것에 대 한 이벤트 처리기입니다.  
  
9. 클릭할 때 새 MDI 자식 폼을 만들려면 다음과 비슷한 코드를 삽입는 **새로** 메뉴 항목입니다.  
  
    > [!NOTE]
    >  다음 예제에서는 이벤트 처리기가 `MenuItem2`에 대한 <xref:System.Windows.Forms.Control.Click> 이벤트를 처리합니다. 주의 응용 프로그램 아키텍처의 세부 사항에 따라 프로그램 **새로** 메뉴 항목이 하지 않을 `MenuItem2`합니다.  
  
    ```vb  
    Protected Sub MDIChildNew_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles MenuItem2.Click  
       Dim NewMDIChild As New Form2()  
       'Set the Parent Form of the Child window.  
       NewMDIChild.MdiParent = Me  
       'Display the new form.  
       NewMDIChild.Show()  
    End Sub  
    ```  
  
    ```csharp  
    protected void MDIChildNew_Click(object sender, System.EventArgs e){  
       Form2 newMDIChild = new Form2();  
       // Set the Parent Form of the Child window.  
       newMDIChild.MdiParent = this;  
       // Display the new form.  
       newMDIChild.Show();  
    }  
    ```  
  
    ```cpp  
    private:  
       void menuItem2_Click(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          Form2^ newMDIChild = gcnew Form2();  
          // Set the Parent Form of the Child window.  
          newMDIChild->MdiParent = this;  
          // Display the new form.  
          newMDIChild->Show();  
       }  
    ```  
  
     [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]에서 Form1.h의 맨 위에 다음 `#include` 지시문을 추가합니다.  
  
    ```cpp  
    #include "Form2.h"  
    ```  
  
10. 맨 위에 있는 드롭다운 목록에는 **속성** 창에 해당 하는 메뉴 스트립을 선택는 **파일** 메뉴 스트립 집합과 <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> 속성을 Window <xref:System.Windows.Forms.ToolStripMenuItem>합니다.  
  
     이렇게 하면는 **창** 메뉴 활성 자식 창 옆에 확인 표시가 있는 열린 MDI 자식 창의 목록을 유지 합니다.  
  
11. F5 키를 눌러 응용 프로그램을 실행합니다. 선택 하 여 **새로** 에서 **파일** 메뉴에는 추적 유지 되는 새 MDI 자식 폼을 만들 수 있습니다는 **창** 메뉴 항목입니다.  
  
    > [!NOTE]
    >  MDI 자식 폼이 <xref:System.Windows.Forms.MainMenu> 구성 요소(일반적으로 메뉴 항목의 메뉴 구조 사용)를 포함하고 <xref:System.Windows.Forms.MainMenu> 구성 요소(일반적으로 메뉴 항목의 메뉴 구조 사용)가 있는 MDI 부모 폼 내에서 열린 경우 <xref:System.Windows.Forms.MenuItem.MergeType%2A> 속성(및 필요에 따라 <xref:System.Windows.Forms.MenuItem.MergeOrder%2A> 속성)을 설정했으면 메뉴 항목이 자동으로 병합됩니다. 두 <xref:System.Windows.Forms.MainMenu> 구성 요소와 자식 폼의 모든 메뉴 항목에 대한 <xref:System.Windows.Forms.MenuItem.MergeType%2A> 속성을 <xref:System.Windows.Forms.MenuMerge.MergeItems>로 설정합니다. 또한 두 메뉴의 메뉴 항목이 원하는 순서대로 표시되도록 <xref:System.Windows.Forms.MenuItem.MergeOrder%2A> 속성을 설정합니다. MDI 부모 폼을 닫을 경우 MDI 부모에 대한 <xref:System.Windows.Forms.Form.Closing> 이벤트가 발생하기 전에 각 MDI 자식 폼에서 <xref:System.Windows.Forms.Form.Closing> 이벤트가 발생합니다. MDI 자식의 <xref:System.Windows.Forms.Form.Closing> 이벤트를 취소해도 MDI 부모의 <xref:System.Windows.Forms.Form.Closing> 이벤트가 발생하지 않도록 방지되지는 않습니다. 그러나 MDI 부모의 <xref:System.Windows.Forms.Form.Closing> 이벤트에 대한 <xref:System.ComponentModel.CancelEventArgs> 인수가 이제 `true`로 설정됩니다. <xref:System.ComponentModel.CancelEventArgs> 인수를 `false`로 설정하여 MDI 부모 및 모든 MDI 자식 폼을 강제로 닫을 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [MDI(다중 문서 인터페이스) 응용 프로그램](../../../../docs/framework/winforms/advanced/multiple-document-interface-mdi-applications.md)  
 [방법: MDI 상위 폼 만들기](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md)  
 [방법: 활성 MDI 자식 확인](../../../../docs/framework/winforms/advanced/how-to-determine-the-active-mdi-child.md)  
 [방법: 활성 MDI 자식으로 데이터 전송](../../../../docs/framework/winforms/advanced/how-to-send-data-to-the-active-mdi-child.md)  
 [방법: MDI 자식 양식 정렬](../../../../docs/framework/winforms/advanced/how-to-arrange-mdi-child-forms.md)
