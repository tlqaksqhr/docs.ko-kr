---
title: "방법: FontDialog 구성 요소를 사용하여 글꼴 목록 표시"
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
- fonts [Windows Forms], showing list
- FontDialog component [Windows Forms]
- fonts [Windows Forms], attributes
- Font property [Windows Forms], setting with FontDialog component
- Font dialog box [Windows Forms], displaying
- fonts [Windows Forms], selecting
ms.assetid: 35692c1b-0937-4b7a-9207-1ae6bdc244a0
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: dd04a44e6f6e3df26a643a8937e20e232e7471a4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-show-a-font-list-with-the-fontdialog-component"></a><span data-ttu-id="5b494-102">방법: FontDialog 구성 요소를 사용하여 글꼴 목록 표시</span><span class="sxs-lookup"><span data-stu-id="5b494-102">How to: Show a Font List with the FontDialog Component</span></span>
<span data-ttu-id="5b494-103">[FontDialog](../../../../docs/framework/winforms/controls/fontdialog-component-windows-forms.md) 구성 요소에 글꼴을 선택 하 고 가중치와 크기 같은 표시 요소를 변경할 사용자를 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b494-103">The [FontDialog](../../../../docs/framework/winforms/controls/fontdialog-component-windows-forms.md) component allows users to select a font, as well as change its display aspects, such as its weight and size.</span></span>  
  
 <span data-ttu-id="5b494-104">대화 상자에서 선택한 글꼴에 반환 되는 <xref:System.Windows.Forms.FontDialog.Font%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="5b494-104">The font selected in the dialog box is returned in the <xref:System.Windows.Forms.FontDialog.Font%2A> property.</span></span> <span data-ttu-id="5b494-105">따라서 사용자가 선택한 글꼴을 활용 하기 위해 속성 읽기를 하기만 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5b494-105">Thus, taking advantage of the font selected by the user is as easy as reading a property.</span></span>  
  
### <a name="to-select-font-properties-using-the-fontdialog-component"></a><span data-ttu-id="5b494-106">FontDialog 구성 요소를 사용 하 여 글꼴 속성을 선택 하려면</span><span class="sxs-lookup"><span data-stu-id="5b494-106">To select font properties using the FontDialog Component</span></span>  
  
1.  <span data-ttu-id="5b494-107">사용 하 여 대화 상자 표시는 <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="5b494-107">Display the dialog box using the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method.</span></span>  
  
2.  <span data-ttu-id="5b494-108">사용 하 여는 <xref:System.Windows.Forms.DialogResult> 대화 상자를 닫은 방법을 결정 하는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="5b494-108">Use the <xref:System.Windows.Forms.DialogResult> property to determine how the dialog box was closed.</span></span>  
  
3.  <span data-ttu-id="5b494-109">사용 하 여는 <xref:System.Windows.Forms.FontDialog.Font%2A> 속성을 원하는 글꼴을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b494-109">Use the <xref:System.Windows.Forms.FontDialog.Font%2A> property to set the desired font.</span></span>  
  
     <span data-ttu-id="5b494-110">다음 예제에는 <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기 열립니다는 <xref:System.Windows.Forms.FontDialog> 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="5b494-110">In the example below, the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event handler opens a <xref:System.Windows.Forms.FontDialog> component.</span></span> <span data-ttu-id="5b494-111">경우 글꼴 선택 하 고 사용자가 **확인**, <xref:System.Windows.Forms.FontDialog.Font%2A> 속성은 <xref:System.Windows.Forms.TextBox> 폼에 컨트롤에 선택 된 글꼴로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5b494-111">When a font is chosen and the user clicks **OK**, the <xref:System.Windows.Forms.FontDialog.Font%2A> property of a <xref:System.Windows.Forms.TextBox> control that is on the form is set to the chosen font.</span></span> <span data-ttu-id="5b494-112">이 예에서는 가정 폼에는 <xref:System.Windows.Forms.Button> 컨트롤은 <xref:System.Windows.Forms.TextBox> 컨트롤 및 <xref:System.Windows.Forms.FontDialog> 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="5b494-112">The example assumes your form has a <xref:System.Windows.Forms.Button> control, a  <xref:System.Windows.Forms.TextBox> control, and a <xref:System.Windows.Forms.FontDialog> component.</span></span>  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, _  
       ByVal e As System.EventArgs) Handles Button1.Click  
       If FontDialog1.ShowDialog() = DialogResult.OK Then  
          TextBox1.Font = FontDialog1.Font  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       if(fontDialog1.ShowDialog() == DialogResult.OK)  
       {  
          textBox1.Font = fontDialog1.Font;  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          if(fontDialog1->ShowDialog() == DialogResult::OK)  
          {  
             textBox1->Font = fontDialog1->Font;  
          }  
       }  
    ```  
  
     <span data-ttu-id="5b494-113">([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] 및 [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) 폼 생성자에 다음 코드를 추가하여 이벤트 처리기를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="5b494-113">([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] and [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    button1->Click += gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="5b494-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5b494-114">See Also</span></span>  
 <xref:System.Windows.Forms.FontDialog>  
 [<span data-ttu-id="5b494-115">FontDialog 구성 요소</span><span class="sxs-lookup"><span data-stu-id="5b494-115">FontDialog Component</span></span>](../../../../docs/framework/winforms/controls/fontdialog-component-windows-forms.md)
