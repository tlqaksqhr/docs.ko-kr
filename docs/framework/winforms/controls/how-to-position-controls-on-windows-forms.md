---
title: "방법: Windows Forms에 컨트롤 배치 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "Location"
  - "Location.Y"
  - "Location.X"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "컨트롤[Windows Forms]"
  - "컨트롤[Windows Forms], 이동"
  - "컨트롤[Windows Forms], 위치 지정"
  - "맞춤선"
ms.assetid: 4693977e-34a4-4f19-8221-68c3120c2b2b
caps.latest.revision: 18
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# 방법: Windows Forms에 컨트롤 배치
컨트롤의 위치를 지정하려면 Windows Forms 디자이너를 사용하거나 <xref:System.Windows.Forms.Control.Location%2A> 속성을 지정합니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.  설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기**를 선택합니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
### Windows Forms 디자이너의 디자인 화면에서 컨트롤의 위치를 지정하려면  
  
-   마우스를 사용하여 컨트롤을 적절한 위치로 끌어 옵니다.  
  
    > [!NOTE]
    >  화살표 키를 사용하여 컨트롤을 선택하고 이동하면 컨트롤의 위치를 더욱 정밀하게 지정할 수 있습니다.  또한 *맞춤선*을 사용하여 컨트롤을 폼에 정밀하게 배치할 수 있습니다.  자세한 내용은 [연습: 맞춤선을 사용하여 Windows Forms에서 컨트롤 정렬](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)을 참조하십시오.  
  
### 속성 창을 사용하여 컨트롤의 위치를 지정하려면  
  
1.  위치를 지정할 컨트롤을 클릭합니다.  
  
2.  **속성** 창에서 <xref:System.Windows.Forms.Control.Location%2A> 속성 값을 입력하여\(각 값은 쉼표로 구분\) 컨테이너 안에서 컨트롤의 위치를 지정합니다.  
  
     첫 번째 숫자\(X\)는 픽셀 단위로 측정된 컨테이너의 왼쪽 테두리부터의 거리이고 두 번째 숫자\(Y\)는 컨테이너 영역의 위쪽 테두리부터의 거리입니다.  
  
    > [!NOTE]
    >  <xref:System.Windows.Forms.Control.Location%2A> 속성을 확장하여 **X** 및 **Y** 값을 개별적으로 입력할 수 있습니다.  
  
### 프로그래밍 방식으로 컨트롤의 위치를 지정하려면  
  
1.  컨트롤의 <xref:System.Windows.Forms.Control.Location%2A> 속성을 <xref:System.Drawing.Point>로 설정합니다.  
  
    ```vb  
    Button1.Location = New Point(100, 100)  
    ```  
  
    ```csharp  
    button1.Location = new Point(100, 100);  
    ```  
  
    ```cpp  
    button1->Location = Point(100, 100);  
    ```  
  
2.  <xref:System.Windows.Forms.Control.Left%2A> 하위 속성을 사용하여 컨트롤의 X 좌표를 변경합니다.  
  
    ```vb  
    Button1.Left = 300  
    ```  
  
    ```csharp  
    button1.Left = 300;  
    ```  
  
    ```cpp  
    button1->Left = 300;  
    ```  
  
### 프로그래밍 방식으로 컨트롤의 위치를 늘리려면  
  
1.  <xref:System.Windows.Forms.Control.Left%2A> 하위 속성을 설정하여 컨트롤의 X 좌표를 늘립니다.  
  
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
    >  컨트롤의 X 및 Y 위치를 동시에 설정하려면 <xref:System.Windows.Forms.Control.Location%2A> 속성을 사용합니다.  위치를 개별적으로 설정하려면 컨트롤의 <xref:System.Windows.Forms.Control.Left%2A>\(**X**\) 또는 <xref:System.Windows.Forms.Control.Top%2A>\(**Y**\) 하위 속성을 사용합니다.  단추의 위치를 나타내는 <xref:System.Drawing.Point> 구조체는 단추의 좌표에 대한 복사본을 가지고 있으므로 이 구조체의 X 좌표와 Y 좌표를 암시적으로 설정하지 마십시오.  
  
## 참고 항목  
 [Windows Forms 컨트롤](../../../../docs/framework/winforms/controls/index.md)   
 [연습: 맞춤선을 사용하여 Windows Forms에서 컨트롤 정렬](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)   
 [연습: TableLayoutPanel을 사용하여 Windows Forms에서 컨트롤 정렬](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)   
 [연습: FlowLayoutPanel을 사용하여 Windows Forms에서 컨트롤 정렬](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)   
 [Windows Forms에서 컨트롤 정렬](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)   
 [개별 Windows Forms 컨트롤 레이블 지정 및 바로 가기 제공](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)   
 [Windows Forms에 사용할 수 있는 컨트롤](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)   
 [기능별 Windows Forms 컨트롤](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)   
 [How to: Set the Screen Location of Windows Forms](http://msdn.microsoft.com/ko-kr/cb023ab7-dea7-4284-9aa6-8c03c59b60c6)