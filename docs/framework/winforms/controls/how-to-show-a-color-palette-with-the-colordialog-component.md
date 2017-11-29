---
title: "방법: ColorDialog 구성 요소를 사용하여 색상표 표시"
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
- palettes [Windows Forms], showing color
- color dialog box [Windows Forms], showing color palettes
- colors [Windows Forms], allowing users to select
- color palettes [Windows Forms], dialog box
- ColorDialog component [Windows Forms], showing color palettes
- color palettes [Windows Forms], showing in ColorDialog component
- colors [Windows Forms], showing palettes
ms.assetid: ee050f61-dbc8-4436-ba22-51360981ab48
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: af773141039d049e010742f339ec4f9363d73cc3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-show-a-color-palette-with-the-colordialog-component"></a>방법: ColorDialog 구성 요소를 사용하여 색상표 표시
[ColorDialog](../../../../docs/framework/winforms/controls/colordialog-component-windows-forms.md) 구성 요소는 색의 팔레트를 표시 하 고 사용자가 선택한 색을 포함 하는 속성을 반환 합니다.  
  
### <a name="to-choose-a-color-using-the-colordialog-component"></a>ColorDialog 구성 요소를 사용 하 여 색을 선택 하려면  
  
1.  사용 하 여 대화 상자 표시는 <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> 메서드.  
  
2.  사용 하 여는 <xref:System.Windows.Forms.DialogResult> 대화 상자를 닫은 방법을 결정 하는 속성입니다.  
  
3.  사용 하 여는 <xref:System.Windows.Forms.ColorDialog.Color%2A> 의 속성은 <xref:System.Windows.Forms.ColorDialog> 선택된 된 색을 설정 하는 구성 요소입니다.  
  
     다음 예제에는 <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기 열립니다는 <xref:System.Windows.Forms.ColorDialog> 구성 요소입니다. 때 색을 선택 하 고 사용자가 **확인**, <xref:System.Windows.Forms.Button> 컨트롤의 배경 색은 선택된 된 색으로 설정 합니다. 이 예에서는 가정 폼에는 <xref:System.Windows.Forms.Button> 제어 및 <xref:System.Windows.Forms.ColorDialog> 구성 요소입니다.  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, _  
    ByVal e As System.EventArgs) Handles Button1.Click  
       If ColorDialog1.ShowDialog() = DialogResult.OK Then  
          Button1.BackColor = ColorDialog1.Color  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       if(colorDialog1.ShowDialog() == DialogResult.OK)  
       {  
          button1.BackColor = colorDialog1.Color;  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,   
          System::EventArgs ^ e)  
       {  
          if(colorDialog1->ShowDialog() == DialogResult::OK)  
          {  
             button1->BackColor = colorDialog1->Color;  
          }  
       }  
    ```  
  
     ([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) 폼 생성자에 다음 코드를 추가하여 이벤트 처리기를 등록합니다.  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click +=   
       gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.ColorDialog>  
 [ColorDialog 구성 요소](../../../../docs/framework/winforms/controls/colordialog-component-windows-forms.md)
