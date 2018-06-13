---
title: '방법: ColorDialog 구성 요소를 사용하여 색상표 표시'
ms.date: 03/30/2017
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
ms.openlocfilehash: ea12fe19b6c8c7464f0820267face8a1d66de784
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33536929"
---
# <a name="how-to-show-a-color-palette-with-the-colordialog-component"></a><span data-ttu-id="09a0f-102">방법: ColorDialog 구성 요소를 사용하여 색상표 표시</span><span class="sxs-lookup"><span data-stu-id="09a0f-102">How to: Show a Color Palette with the ColorDialog Component</span></span>
<span data-ttu-id="09a0f-103">[ColorDialog](../../../../docs/framework/winforms/controls/colordialog-component-windows-forms.md) 구성 요소는 색의 팔레트를 표시 하 고 사용자가 선택한 색을 포함 하는 속성을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="09a0f-103">The [ColorDialog](../../../../docs/framework/winforms/controls/colordialog-component-windows-forms.md) component displays a palette of colors and returns a property containing the color the user has selected.</span></span>  
  
### <a name="to-choose-a-color-using-the-colordialog-component"></a><span data-ttu-id="09a0f-104">ColorDialog 구성 요소를 사용 하 여 색을 선택 하려면</span><span class="sxs-lookup"><span data-stu-id="09a0f-104">To choose a color using the ColorDialog component</span></span>  
  
1.  <span data-ttu-id="09a0f-105">사용 하 여 대화 상자 표시는 <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="09a0f-105">Display the dialog box using the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method.</span></span>  
  
2.  <span data-ttu-id="09a0f-106">사용 하 여는 <xref:System.Windows.Forms.DialogResult> 대화 상자를 닫은 방법을 결정 하는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="09a0f-106">Use the <xref:System.Windows.Forms.DialogResult> property to determine how the dialog box was closed.</span></span>  
  
3.  <span data-ttu-id="09a0f-107">사용 하 여는 <xref:System.Windows.Forms.ColorDialog.Color%2A> 의 속성은 <xref:System.Windows.Forms.ColorDialog> 선택된 된 색을 설정 하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="09a0f-107">Use the <xref:System.Windows.Forms.ColorDialog.Color%2A> property of the <xref:System.Windows.Forms.ColorDialog> component to set the chosen color.</span></span>  
  
     <span data-ttu-id="09a0f-108">다음 예제에는 <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기 열립니다는 <xref:System.Windows.Forms.ColorDialog> 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="09a0f-108">In the example below, the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event handler opens a <xref:System.Windows.Forms.ColorDialog> component.</span></span> <span data-ttu-id="09a0f-109">때 색을 선택 하 고 사용자가 **확인**, <xref:System.Windows.Forms.Button> 컨트롤의 배경 색은 선택된 된 색으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="09a0f-109">When a color is chosen and the user clicks **OK**, the <xref:System.Windows.Forms.Button> control's background color is set to the chosen color.</span></span> <span data-ttu-id="09a0f-110">이 예에서는 가정 폼에는 <xref:System.Windows.Forms.Button> 제어 및 <xref:System.Windows.Forms.ColorDialog> 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="09a0f-110">The example assumes your form has a <xref:System.Windows.Forms.Button> control and a <xref:System.Windows.Forms.ColorDialog> component.</span></span>  
  
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
  
     <span data-ttu-id="09a0f-111">(Visual C# [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) 이벤트 처리기를 등록 하려면 폼의 생성자에 다음 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="09a0f-111">(Visual C#, [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click +=   
       gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="09a0f-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="09a0f-112">See Also</span></span>  
 <xref:System.Windows.Forms.ColorDialog>  
 [<span data-ttu-id="09a0f-113">ColorDialog 구성 요소</span><span class="sxs-lookup"><span data-stu-id="09a0f-113">ColorDialog Component</span></span>](../../../../docs/framework/winforms/controls/colordialog-component-windows-forms.md)
