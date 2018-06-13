---
title: '방법: Windows Forms에 컨트롤 배치'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- Location
- Location.Y
- Location.X
helpviewer_keywords:
- controls [Windows Forms]
- controls [Windows Forms], moving
- snaplines
- controls [Windows Forms], positioning
ms.assetid: 4693977e-34a4-4f19-8221-68c3120c2b2b
ms.openlocfilehash: 6db021f2b1a29c3ef52a182c45bbc7878feebb97
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33538714"
---
# <a name="how-to-position-controls-on-windows-forms"></a>방법: Windows Forms에 컨트롤 배치
컨트롤의 위치, Windows Forms 디자이너를 사용 하거나 지정 된 <xref:System.Windows.Forms.Control.Location%2A> 속성입니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.  
  
### <a name="to-position-a-control-on-the-design-surface-of-the-windows-forms-designer"></a>Windows Forms 디자이너의 디자인 화면에 컨트롤을 배치 하려면  
  
-   컨트롤을 마우스로 적절 한 위치로 끕니다.  
  
    > [!NOTE]
    >  컨트롤을 선택 하 고 화살표가 포함 된 키 보다 정확 하 게 배치 하기 이동 합니다. 또한 *맞춤선* 정확 하 게 폼에 컨트롤을 배치 하는 데 도움이 됩니다. 자세한 내용은 참조 [연습: 맞춤선 Windows Forms에서 사용 하 여 컨트롤 정렬](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)합니다.  
  
### <a name="to-position-a-control-using-the-properties-window"></a>속성 창을 사용 하 여 컨트롤을 배치 하기  
  
1.  컨트롤의 위치를 클릭 합니다.  
  
2.  **속성** 창에 대 한 유형 값의 <xref:System.Windows.Forms.Control.Location%2A> 해당 컨테이너 내에서 컨트롤을 배치 하는 쉼표로 구분 된 속성입니다.  
  
     첫 번째 번호 (X)은; 컨테이너의 왼쪽된 테두리 거리 두 번째 숫자 (Y)는 거리 (픽셀) 컨테이너 영역의 위쪽 테두리 합니다.  
  
    > [!NOTE]
    >  확장할 수 있습니다는 <xref:System.Windows.Forms.Control.Location%2A> 속성 입력을 **X** 및 **Y** 값을 개별적으로 합니다.  
  
### <a name="to-position-a-control-programmatically"></a>컨트롤을 프로그래밍 방식으로 배치 하려면  
  
1.  설정의 <xref:System.Windows.Forms.Control.Location%2A> 컨트롤의 속성을 <xref:System.Drawing.Point>합니다.  
  
    ```vb  
    Button1.Location = New Point(100, 100)  
    ```  
  
    ```csharp  
    button1.Location = new Point(100, 100);  
    ```  
  
    ```cpp  
    button1->Location = Point(100, 100);  
    ```  
  
2.  X 좌표는 컨트롤의 위치를 변경 사용 하 여 <xref:System.Windows.Forms.Control.Left%2A> 하위 속성입니다.  
  
    ```vb  
    Button1.Left = 300  
    ```  
  
    ```csharp  
    button1.Left = 300;  
    ```  
  
    ```cpp  
    button1->Left = 300;  
    ```  
  
### <a name="to-increment-a-controls-location-programmatically"></a>컨트롤의 위치를 프로그래밍 방식으로 증가  
  
1.  설정의 <xref:System.Windows.Forms.Control.Left%2A> 하위 속성 컨트롤의 X 좌표를 늘립니다.  
  
    ```vb  
    Button1.Left += 200  
    ```  
  
    ```csharp  
    button1.Left += 200;  
    ```  
  
    ```cpp  
    button1->Left += 200;  
    ```  
  
    > [!NOTE]
    >  사용 하 여 <xref:System.Windows.Forms.Control.Location%2A> 속성을 설정 하는 컨트롤의 X 및 Y 위치를 동시에 합니다. 위치를 개별적으로 설정 하는 컨트롤을 사용 하 여 <xref:System.Windows.Forms.Control.Left%2A> (**X**) 또는 <xref:System.Windows.Forms.Control.Top%2A> (**Y**) 하위 속성입니다. 암시적으로의 X 및 Y 좌표를 설정 하지 마십시오는 <xref:System.Drawing.Point> 이 구조는 단추의 좌표의 복사본을 포함 하기 때문에 단추의 위치를 나타내는 구조입니다.  
  
## <a name="see-also"></a>참고 항목  
 [Windows Forms 컨트롤](../../../../docs/framework/winforms/controls/index.md)  
 [연습: Windows Forms에서 맞춤선을 사용하여 컨트롤 정렬](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)  
 [연습: TableLayoutPanel을 사용하여 Windows Forms에서 컨트롤 정렬](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)  
 [연습: FlowLayoutPanel을 사용하여 Windows Forms에서 컨트롤 정렬](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)  
 [Windows Forms에서 컨트롤 정렬](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)  
 [개별 Windows Forms 컨트롤 레이블 지정 및 바로 가기 제공](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)  
 [Windows Forms에 사용할 수 있는 컨트롤](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 [기능별 Windows Forms 컨트롤](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)  
 [방법: Windows Forms의 화면 위치 설정](http://msdn.microsoft.com/library/cb023ab7-dea7-4284-9aa6-8c03c59b60c6)
