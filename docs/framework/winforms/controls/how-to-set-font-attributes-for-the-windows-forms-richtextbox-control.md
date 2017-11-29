---
title: "방법: Windows Forms RichTextBox 컨트롤의 글꼴 특성 설정"
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
- .rtf files [Windows Forms], formatting in RichTextBox control
- fonts [Windows Forms], changing attributes in RichTextBox control
- RTF files [Windows Forms], formatting in RichTextBox control
- RichTextBox control [Windows Forms], setting font attributes
- text [Windows Forms]
- text boxes [Windows Forms], formatting text
- formatting [Windows Forms]
ms.assetid: 2bc23ddb-0529-4489-a1a2-ad253cb43f9a
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0fe122f509890715c398bef728a98ff874b61817
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-set-font-attributes-for-the-windows-forms-richtextbox-control"></a><span data-ttu-id="6d384-102">방법: Windows Forms RichTextBox 컨트롤의 글꼴 특성 설정</span><span class="sxs-lookup"><span data-stu-id="6d384-102">How to: Set Font Attributes for the Windows Forms RichTextBox Control</span></span>
<span data-ttu-id="6d384-103">Windows Forms <xref:System.Windows.Forms.RichTextBox> 컨트롤에 표시 되는 텍스트 서식을 지정 하기 위한 다양 한 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d384-103">The Windows Forms <xref:System.Windows.Forms.RichTextBox> control has numerous options for formatting the text it displays.</span></span> <span data-ttu-id="6d384-104">정확해 선택한 문자 굵게, 밑줄, 또는 기울임꼴를 사용 하 여 <xref:System.Windows.Forms.RichTextBox.SelectionFont%2A> 속성.</span><span class="sxs-lookup"><span data-stu-id="6d384-104">You can make the selected characters bold, underlined, or italic, using the <xref:System.Windows.Forms.RichTextBox.SelectionFont%2A> property.</span></span> <span data-ttu-id="6d384-105">또한 이 속성을 사용하여 선택한 문자의 크기와 서체를 변경할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d384-105">You can also use this property to change the size and typeface of the selected characters.</span></span> <span data-ttu-id="6d384-106"><xref:System.Windows.Forms.RichTextBox.SelectionColor%2A> 속성을 사용 하면 선택한 문자 색을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d384-106">The <xref:System.Windows.Forms.RichTextBox.SelectionColor%2A> property enables you to change the selected characters' color.</span></span>  
  
### <a name="to-change-the-appearance-of-characters"></a><span data-ttu-id="6d384-107">문자의 모양을 변경하려면</span><span class="sxs-lookup"><span data-stu-id="6d384-107">To change the appearance of characters</span></span>  
  
1.  <span data-ttu-id="6d384-108">설정의 <xref:System.Windows.Forms.RichTextBox.SelectionFont%2A> 속성을 적절 한 글꼴입니다.</span><span class="sxs-lookup"><span data-stu-id="6d384-108">Set the <xref:System.Windows.Forms.RichTextBox.SelectionFont%2A> property to an appropriate font.</span></span>  
  
     <span data-ttu-id="6d384-109">사용자가 응용 프로그램에서 글꼴 패밀리, 크기 및 서체를 설정할 수 있도록 일반적으로 사용 된 <xref:System.Windows.Forms.FontDialog> 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="6d384-109">To enable users to set the font family, size, and typeface in an application, you would typically use the <xref:System.Windows.Forms.FontDialog> component.</span></span> <span data-ttu-id="6d384-110">개요는 [FontDialog 구성 요소 개요](../../../../docs/framework/winforms/controls/fontdialog-component-overview-windows-forms.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6d384-110">For an overview, see [FontDialog Component Overview](../../../../docs/framework/winforms/controls/fontdialog-component-overview-windows-forms.md).</span></span>  
  
2.  <span data-ttu-id="6d384-111">설정의 <xref:System.Windows.Forms.RichTextBox.SelectionColor%2A> 속성을 적절 한 색을 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d384-111">Set the <xref:System.Windows.Forms.RichTextBox.SelectionColor%2A> property to an appropriate color.</span></span>  
  
     <span data-ttu-id="6d384-112">응용 프로그램에서 색을 설정 하려면 사용자가 사용 하려면 일반적으로 사용 된 <xref:System.Windows.Forms.ColorDialog> 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="6d384-112">To enable users to set the color in an application, you would typically use the <xref:System.Windows.Forms.ColorDialog> component.</span></span> <span data-ttu-id="6d384-113">개요는 [ColorDialog 구성 요소 개요](../../../../docs/framework/winforms/controls/colordialog-component-overview-windows-forms.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6d384-113">For an overview, see [ColorDialog Component Overview](../../../../docs/framework/winforms/controls/colordialog-component-overview-windows-forms.md).</span></span>  
  
    ```vb  
    RichTextBox1.SelectionFont = New Font("Tahoma", 12, FontStyle.Bold)  
    RichTextBox1.SelectionColor = System.Drawing.Color.Red  
    ```  
  
    ```csharp  
    richTextBox1.SelectionFont = new Font("Tahoma", 12, FontStyle.Bold);  
    richTextBox1.SelectionColor = System.Drawing.Color.Red;  
    ```  
  
    ```cpp  
    richTextBox1->SelectionFont =  
       gcnew System::Drawing::Font("Tahoma", 12, FontStyle::Bold);  
    richTextBox1->SelectionColor = System::Drawing::Color::Red;  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="6d384-114">이러한 속성은 선택한 텍스트에만 적용되며, 선택한 텍스트가 없으면 삽입 지점의 현재 위치에서 입력한 텍스트에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d384-114">These properties only affect selected text, or, if no text is selected, the text that is typed at the current location of the insertion point.</span></span> <span data-ttu-id="6d384-115">프로그래밍 방식으로 텍스트를 선택 하는 내용은 <xref:System.Windows.Forms.TextBoxBase.Select%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="6d384-115">For information on selecting text programmatically, see <xref:System.Windows.Forms.TextBoxBase.Select%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d384-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6d384-116">See Also</span></span>  
 <xref:System.Windows.Forms.RichTextBox>  
 [<span data-ttu-id="6d384-117">RichTextBox 컨트롤</span><span class="sxs-lookup"><span data-stu-id="6d384-117">RichTextBox Control</span></span>](../../../../docs/framework/winforms/controls/richtextbox-control-windows-forms.md)  
 [<span data-ttu-id="6d384-118">Windows Forms에 사용할 수 있는 컨트롤</span><span class="sxs-lookup"><span data-stu-id="6d384-118">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
