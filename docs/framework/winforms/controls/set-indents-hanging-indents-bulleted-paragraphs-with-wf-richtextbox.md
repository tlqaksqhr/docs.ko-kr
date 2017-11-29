---
title: "방법: Windows Forms RichTextBox 컨트롤을 사용하여 들여쓰기, 내어쓰기 및 글머리 기호 단락 설정"
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
- text boxes [Windows Forms], setting indents
- .rtf files [Windows Forms], formatting in RichTextBox control
- examples [Windows Forms], text boxes
- RTF files [Windows Forms], formatting in RichTextBox control
- RichTextBox control [Windows Forms], setting indents and bullets
- text boxes [Windows Forms], bullets
ms.assetid: abfb40e6-5642-4691-8ec1-9d9ae91688dc
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b9b1398c0438f9ebe528e9394014f5f6529ea8f2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-set-indents-hanging-indents-and-bulleted-paragraphs-with-the-windows-forms-richtextbox-control"></a><span data-ttu-id="c5a5a-102">방법: Windows Forms RichTextBox 컨트롤을 사용하여 들여쓰기, 내어쓰기 및 글머리 기호 단락 설정</span><span class="sxs-lookup"><span data-stu-id="c5a5a-102">How to: Set Indents, Hanging Indents, and Bulleted Paragraphs with the Windows Forms RichTextBox Control</span></span>
<span data-ttu-id="c5a5a-103">Windows Forms <xref:System.Windows.Forms.RichTextBox> 컨트롤에 표시 되는 텍스트 서식을 지정 하기 위한 다양 한 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5a5a-103">The Windows Forms <xref:System.Windows.Forms.RichTextBox> control has numerous options for formatting the text it displays.</span></span> <span data-ttu-id="c5a5a-104">설정 하 여 선택한 단락이 글머리 기호 목록으로 서식을 지정할 수 있습니다는 <xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="c5a5a-104">You can format selected paragraphs as bulleted lists by setting the <xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A> property.</span></span> <span data-ttu-id="c5a5a-105">사용할 수도 있습니다는 <xref:System.Windows.Forms.RichTextBox.SelectionIndent%2A>, <xref:System.Windows.Forms.RichTextBox.SelectionRightIndent%2A>, 및 <xref:System.Windows.Forms.RichTextBox.SelectionHangingIndent%2A> 왼쪽 및 컨트롤의 오른쪽 가장자리와 다른 텍스트 줄의 왼쪽된 가장자리를 기준으로 단락 들여쓰기를 설정 하는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="c5a5a-105">You can also use the <xref:System.Windows.Forms.RichTextBox.SelectionIndent%2A>, <xref:System.Windows.Forms.RichTextBox.SelectionRightIndent%2A>, and <xref:System.Windows.Forms.RichTextBox.SelectionHangingIndent%2A> properties to set the indentation of paragraphs relative to the left and right edges of the control, and the left edge of other lines of text.</span></span>  
  
### <a name="to-format-a-paragraph-as-a-bulleted-list"></a><span data-ttu-id="c5a5a-106">단락의 서식을 글머리 기호 목록으로 지정하려면</span><span class="sxs-lookup"><span data-stu-id="c5a5a-106">To format a paragraph as a bulleted list</span></span>  
  
1.  <span data-ttu-id="c5a5a-107"><xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A> 속성을 `true`으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c5a5a-107">Set the <xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A> property to `true`.</span></span>  
  
    ```vb  
    RichTextBox1.SelectionBullet = True  
    ```  
  
    ```csharp  
    richTextBox1.SelectionBullet = true;  
    ```  
  
    ```cpp  
    richTextBox1->SelectionBullet = true;  
    ```  
  
### <a name="to-indent-a-paragraph"></a><span data-ttu-id="c5a5a-108">단락을 들여쓰려면</span><span class="sxs-lookup"><span data-stu-id="c5a5a-108">To indent a paragraph</span></span>  
  
1.  <span data-ttu-id="c5a5a-109">설정의 <xref:System.Windows.Forms.RichTextBox.SelectionIndent%2A> 속성을 텍스트의 왼쪽된 가장자리와 컨트롤의 왼쪽된 가장자리 사이의 픽셀 거리를 나타내는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="c5a5a-109">Set the <xref:System.Windows.Forms.RichTextBox.SelectionIndent%2A> property to an integer representing the distance in pixels between the left edge of the control and the left edge of the text.</span></span>  
  
2.  <span data-ttu-id="c5a5a-110">설정의 <xref:System.Windows.Forms.RichTextBox.SelectionHangingIndent%2A> 속성을 첫 번째 단락에 텍스트 줄의 왼쪽된 가장자리와 같은 단락에 다음 줄의 왼쪽된 가장자리 사이의 픽셀 거리를 나타내는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="c5a5a-110">Set the <xref:System.Windows.Forms.RichTextBox.SelectionHangingIndent%2A> property to an integer representing the distance in pixels between the left edge of the first line of text in the paragraph and the left edge of subsequent lines in the same paragraph.</span></span> <span data-ttu-id="c5a5a-111">값은 <xref:System.Windows.Forms.RichTextBox.SelectionHangingIndent%2A> 속성이 첫 번째 줄은 줄 바꿈된 단락의 줄에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5a5a-111">The value of the <xref:System.Windows.Forms.RichTextBox.SelectionHangingIndent%2A> property only applies to lines in a paragraph that have wrapped below the first line.</span></span>  
  
3.  <span data-ttu-id="c5a5a-112">설정의 <xref:System.Windows.Forms.RichTextBox.SelectionRightIndent%2A> 속성을 픽셀 텍스트의 오른쪽 가장자리와 컨트롤의 오른쪽 가장자리 사이의 거리를 나타내는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="c5a5a-112">Set the <xref:System.Windows.Forms.RichTextBox.SelectionRightIndent%2A> property to an integer representing the distance in pixels between the right edge of the control and the right edge of the text.</span></span>  
  
    ```vb  
    RichTextBox1.SelectionIndent = 8  
    RichTextBox1.SelectionHangingIndent = 3  
    RichTextBox1.SelectionRightIndent = 12  
    ```  
  
    ```csharp  
    richTextBox1.SelectionIndent = 8;  
    richTextBox1.SelectionHangingIndent = 3;  
    richTextBox1.SelectionRightIndent = 12;  
    ```  
  
    ```cpp  
    richTextBox1->SelectionIndent = 8;  
    richTextBox1->SelectionHangingIndent = 3;  
    richTextBox1->SelectionRightIndent = 12;  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="c5a5a-113">이러한 모든 속성은 선택한 텍스트가 포함된 단락에 적용되며, 현재 삽입 지점 이후로 입력된 텍스트에도 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5a5a-113">All these properties affect any paragraphs that contain selected text, and also the text that is typed after the current insertion point.</span></span> <span data-ttu-id="c5a5a-114">예를 들어 사용자가 단락 내의 단어를 선택한 다음 들여쓰기를 조정하면, 이 단어가 포함된 전체 단락뿐만 아니라 선택한 단락 이후에 입력되는 모든 단락에도 새 설정이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5a5a-114">For example, when a user selects a word within a paragraph and then adjusts the indentation, the new settings will apply to the entire paragraph that contains that word, and also to any paragraphs subsequently entered after the selected paragraph.</span></span> <span data-ttu-id="c5a5a-115">프로그래밍 방식으로 텍스트를 선택 하는 방법에 대 한 정보를 참조 하십시오. <xref:System.Windows.Forms.TextBoxBase.Select%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="c5a5a-115">For information about selecting text programmatically, see <xref:System.Windows.Forms.TextBoxBase.Select%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5a5a-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c5a5a-116">See Also</span></span>  
 <xref:System.Windows.Forms.RichTextBox>  
 [<span data-ttu-id="c5a5a-117">RichTextBox 컨트롤</span><span class="sxs-lookup"><span data-stu-id="c5a5a-117">RichTextBox Control</span></span>](../../../../docs/framework/winforms/controls/richtextbox-control-windows-forms.md)  
 [<span data-ttu-id="c5a5a-118">Windows Forms에 사용할 수 있는 컨트롤</span><span class="sxs-lookup"><span data-stu-id="c5a5a-118">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
