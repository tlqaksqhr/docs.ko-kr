---
title: "방법: 도구 모음 단추의 아이콘 정의 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "단추[Windows Forms], 아이콘"
  - "예제[Windows Forms], 도구 모음"
  - "아이콘[Windows Forms], 도구 모음 단추"
  - "이미지[Windows Forms], 도구 모음 단추"
  - "ToolBar 컨트롤[Windows Forms], 단추에 아이콘 추가"
  - "도구 모음[Windows Forms], 단추에 아이콘 추가"
ms.assetid: 84db98b4-8566-49ce-b2c8-1fd66a5eb3a0
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# 방법: 도구 모음 단추의 아이콘 정의
> [!NOTE]
>  <xref:System.Windows.Forms.ToolStrip> 컨트롤은 <xref:System.Windows.Forms.ToolBar> 컨트롤을 대체하고 여기에 다른 기능을 추가하여 새로 도입된 컨트롤이지만 이전 버전과의 호환성 및 이후 사용 가능성을 고려하여 <xref:System.Windows.Forms.ToolBar> 컨트롤을 계속 유지하도록 선택할 수 있습니다.  
  
 사용자가 쉽게 식별할 수 있도록 <xref:System.Windows.Forms.ToolBar> 단추에 아이콘을 표시할 수 있습니다.  이렇게 하려면 [ImageList 구성 요소](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md) 구성 요소에 이미지를 추가한 다음 <xref:System.Windows.Forms.ImageList> 구성 요소를 <xref:System.Windows.Forms.ToolBar> 컨트롤에 연결합니다.  
  
### 프로그래밍 방식으로 도구 모음 단추의 아이콘을 설정하려면  
  
1.  프로시저에서 <xref:System.Windows.Forms.ImageList> 구성 요소와 <xref:System.Windows.Forms.ToolBar> 컨트롤을 인스턴스화합니다.  
  
2.  동일한 프로시저에서 <xref:System.Windows.Forms.ImageList> 구성 요소에 이미지를 할당합니다.  
  
3.  동일한 프로시저에서 <xref:System.Windows.Forms.ImageList> 컨트롤을 <xref:System.Windows.Forms.ToolBar> 컨트롤에 할당하고 개별 도구 모음 단추의 <xref:System.Windows.Forms.ToolBarButton.ImageIndex%2A> 속성을 할당합니다.  
  
     다음 코드 예제에서 이미지의 위치로 설정된 경로는 **내 문서** 폴더입니다.  Windows 운영 체제가 실행되는 대부분의 컴퓨터에는 내 문서 폴더가 포함되어 있으므로 이 위치를 사용합니다.  또한 이 위치를 선택하면 사용자는 최소한의 시스템 액세스 수준으로 응용 프로그램을 안전하게 실행할 수 있습니다.  아래 예제에서는 <xref:System.Windows.Forms.PictureBox> 컨트롤이 포함된 폼을 이미 추가한 것으로 가정합니다.  
  
     위 단계를 수행하고 나면 아래와 유사한 코드가 작성됩니다.  
  
    ```vb  
    Public Sub InitializeMyToolBar()  
    ' Instantiate an ImageList component and a ToolBar control.  
       Dim ToolBar1 as New ToolBar  
       Dim ImageList1 as New ImageList  
    ' Assign an image to the ImageList component.  
    ' You should replace the bold image  
    ' in the sample below with an icon of your own choosing.  
       Dim myImage As System.Drawing.Image = _   
          Image.FromFile Image.FromFile _  
          (System.Environment.GetFolderPath _  
          (System.Environment.SpecialFolder.Personal) _  
          & "\Image.gif")  
       ImageList1.Images.Add(myImage)  
    ' Create a ToolBarButton.  
       Dim ToolBarButton1 As New ToolBarButton()  
    ' Add the ToolBarButton to the ToolBar.  
       ToolBar1.Buttons.Add(toolBarButton1)  
    ' Assign an ImageList to the ToolBar.  
       ToolBar1.ImageList = ImageList1  
    ' Assign the ImageIndex property of the ToolBarButton.  
       ToolBarButton1.ImageIndex = 0  
    End Sub  
  
    ```  
  
    ```csharp  
    public void InitializeMyToolBar()  
    {  
       // Instantiate an ImageList component and a ToolBar control.  
       ToolBar toolBar1 = new  ToolBar();   
       ImageList imageList1 = new ImageList();  
       // Assign an image to the ImageList component.  
       // You should replace the bold image   
       // in the sample below with an icon of your own choosing.  
       // Note the escape character used (@) when specifying the path.  
       Image myImage = Image.FromFile  
       (System.Environment.GetFolderPath  
       (System.Environment.SpecialFolder.Personal)  
       + @"\Image.gif");  
       imageList1.Images.Add(myImage);  
       // Create a ToolBarButton.  
       ToolBarButton toolBarButton1 = new ToolBarButton();  
       // Add the ToolBarButton to the ToolBar.  
       toolBar1.Buttons.Add(toolBarButton1);  
       // Assign an ImageList to the ToolBar.  
       toolBar1.ImageList = imageList1;  
       // Assign ImageIndex property of the ToolBarButton.  
       toolBarButton1.ImageIndex = 0;  
    }  
  
    ```  
  
    ```cpp  
    public:  
       void InitializeMyToolBar()  
       {  
          // Instantiate an ImageList component and a ToolBar control.  
          ToolBar ^ toolBar1 = gcnew  ToolBar();   
          ImageList ^ imageList1 = gcnew ImageList();  
          // Assign an image to the ImageList component.  
          // You should replace the bold image   
          // in the sample below with an icon of your own choosing.  
          Image ^ myImage = Image::FromFile(String::Concat  
             (System::Environment::GetFolderPath  
             (System::Environment::SpecialFolder::Personal),  
             "\\Image.gif"));  
          imageList1->Images->Add(myImage);  
          // Create a ToolBarButton.  
          ToolBarButton ^ toolBarButton1 = gcnew ToolBarButton();  
          // Add the ToolBarButton to the ToolBar.  
          toolBar1->Buttons->Add(toolBarButton1);  
          // Assign an ImageList to the ToolBar.  
          toolBar1->ImageList = imageList1;  
          // Assign ImageIndex property of the ToolBarButton.  
          toolBarButton1->ImageIndex = 0;  
       }  
    ```  
  
## 참고 항목  
 <xref:System.Windows.Forms.ToolBar>   
 [방법: 도구 모음 단추에 대한 메뉴 이벤트 발생](../../../../docs/framework/winforms/controls/how-to-trigger-menu-events-for-toolbar-buttons.md)   
 [ToolBar 컨트롤](../../../../docs/framework/winforms/controls/toolbar-control-windows-forms.md)   
 [ImageList 구성 요소](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md)