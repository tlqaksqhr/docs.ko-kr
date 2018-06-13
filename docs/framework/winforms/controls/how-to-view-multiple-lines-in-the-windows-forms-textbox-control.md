---
title: '방법: Windows Forms TextBox 컨트롤에 여러 줄 표시'
ms.date: 03/30/2017
helpviewer_keywords:
- newline
- end of line
- ScrollBars property [Windows Forms], in TextBox control
- CRLF
- MultiLine property in TextBox control
- line-feed
- TextBox control [Windows Forms], viewing multiple lines
- carriage return
ms.assetid: 43173201-0b74-4067-a472-605029ca5f35
ms.openlocfilehash: c826a519d8be05430eb6e2434209424514347b5e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33538569"
---
# <a name="how-to-view-multiple-lines-in-the-windows-forms-textbox-control"></a><span data-ttu-id="3dfc2-102">방법: Windows Forms TextBox 컨트롤에 여러 줄 표시</span><span class="sxs-lookup"><span data-stu-id="3dfc2-102">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>
<span data-ttu-id="3dfc2-103">기본적으로 Windows Forms <xref:System.Windows.Forms.TextBox> 컨트롤의 텍스트 한 줄을 표시 하 고 스크롤 막대를 표시 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3dfc2-103">By default, the Windows Forms <xref:System.Windows.Forms.TextBox> control displays a single line of text and does not display scroll bars.</span></span> <span data-ttu-id="3dfc2-104">텍스트 사용 가능한 공간 보다 긴 경우에 텍스트의 일부만 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3dfc2-104">If the text is longer than the available space, only part of the text is visible.</span></span> <span data-ttu-id="3dfc2-105">설정 하 여이 기본 동작을 변경할 수 있습니다는 <xref:System.Windows.Forms.TextBox.Multiline%2A>, <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A>, 및 <xref:System.Windows.Forms.TextBox.ScrollBars%2A> 속성을 적절 한 값입니다.</span><span class="sxs-lookup"><span data-stu-id="3dfc2-105">You can change this default behavior by setting the <xref:System.Windows.Forms.TextBox.Multiline%2A>, <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A>, and <xref:System.Windows.Forms.TextBox.ScrollBars%2A> properties to appropriate values.</span></span>  
  
### <a name="to-display-a-carriage-return-in-the-textbox-control"></a><span data-ttu-id="3dfc2-106">TextBox 컨트롤에 캐리지 리턴을 표시 하려면</span><span class="sxs-lookup"><span data-stu-id="3dfc2-106">To display a carriage return in the TextBox control</span></span>  
  
-   <span data-ttu-id="3dfc2-107">여러 줄에 캐리지 리턴을 표시 하려면 <xref:System.Windows.Forms.TextBox>를 사용 하 여는 <xref:System.Environment.NewLine%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="3dfc2-107">To display a carriage return in a multi-line <xref:System.Windows.Forms.TextBox>, use the <xref:System.Environment.NewLine%2A> property.</span></span>  
  
     <span data-ttu-id="3dfc2-108">알아야 하는 이스케이프 문자를 해석 (\\)는 언어에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="3dfc2-108">Be aware that the interpretation of escape characters (\\) is language-specific.</span></span> <span data-ttu-id="3dfc2-109">Visual Basic 사용 하 여 `Chr$(13) & Chr$(10)` 캐리지 리턴 및 줄 바꿈 문자 조합에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="3dfc2-109">Visual Basic uses `Chr$(13) & Chr$(10)` for the carriage return and linefeed character combination.</span></span>  
  
### <a name="to-view-multiple-lines-in-the-textbox-control"></a><span data-ttu-id="3dfc2-110">여러 줄 TextBox 컨트롤에서 보려면</span><span class="sxs-lookup"><span data-stu-id="3dfc2-110">To view multiple lines in the TextBox control</span></span>  
  
1.  <span data-ttu-id="3dfc2-111"><xref:System.Windows.Forms.TextBox.Multiline%2A> 속성을 `true`으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3dfc2-111">Set the <xref:System.Windows.Forms.TextBox.Multiline%2A> property to `true`.</span></span> <span data-ttu-id="3dfc2-112">경우 <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> 은 `true` (기본값), 컨트롤의 텍스트를 하나 이상의 단락 표시 됩니다; 그렇지 않으면 일부 줄 컨트롤의 가장자리에 잘릴 수 있는 목록으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3dfc2-112">If <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> is `true` (the default), then the text in the control will appear as one or more paragraphs; otherwise it will appear as a list, in which some lines may be clipped at the edge of the control.</span></span>  
  
2.  <span data-ttu-id="3dfc2-113"><xref:System.Windows.Forms.TextBox.ScrollBars%2A> 속성을 적절한 값으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3dfc2-113">Set the <xref:System.Windows.Forms.TextBox.ScrollBars%2A> property to an appropriate value.</span></span>  
  
    |<span data-ttu-id="3dfc2-114">값</span><span class="sxs-lookup"><span data-stu-id="3dfc2-114">Value</span></span>|<span data-ttu-id="3dfc2-115">설명</span><span class="sxs-lookup"><span data-stu-id="3dfc2-115">Description</span></span>|  
    |-----------|-----------------|  
    |<xref:System.Windows.Forms.ScrollBars.None>|<span data-ttu-id="3dfc2-116">텍스트를 단락 수 없는 경우이 값을 사용 하는 컨트롤을 거의 대부분 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="3dfc2-116">Use this value if the text will be a paragraph that almost always fits the control.</span></span> <span data-ttu-id="3dfc2-117">사용자는 텍스트 한 번에 표시할 너무 길면 컨트롤 내부 이동할 수 마우스 포인터를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3dfc2-117">The user can use the mouse pointer to move around inside the control if the text is too long to display all at once.</span></span>|  
    |<xref:System.Windows.Forms.ScrollBars.Horizontal>|<span data-ttu-id="3dfc2-118">너비 보다 클 수 있으며 다음과 같은 줄의 목록을 표시 하려면이 값을 사용 하 여는 <xref:System.Windows.Forms.TextBox> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="3dfc2-118">Use this value if you want to display a list of lines, some of which may be longer than the width of the <xref:System.Windows.Forms.TextBox> control.</span></span>|  
    |<xref:System.Windows.Forms.ScrollBars.Both>|<span data-ttu-id="3dfc2-119">목록 컨트롤의 높이 보다 클 수 있으며이 값을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3dfc2-119">Use this value if the list may be longer than the height of the control.</span></span>|  
  
3.  <span data-ttu-id="3dfc2-120"><xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> 속성을 적절한 값으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3dfc2-120">Set the <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> property to an appropriate value.</span></span>  
  
    |<span data-ttu-id="3dfc2-121">값</span><span class="sxs-lookup"><span data-stu-id="3dfc2-121">Value</span></span>|<span data-ttu-id="3dfc2-122">설명</span><span class="sxs-lookup"><span data-stu-id="3dfc2-122">Description</span></span>|  
    |-----------|-----------------|  
    |`false`|<span data-ttu-id="3dfc2-123">컨트롤의에서 텍스트를 자동으로 줄 바꿈됩니다, 줄 바꿈에 도달할 때까지 오른쪽으로 스크롤됩니다.</span><span class="sxs-lookup"><span data-stu-id="3dfc2-123">Text in the control will not automatically be wrapped, so it will scroll to the right until a line break is reached.</span></span> <span data-ttu-id="3dfc2-124">선택한 경우이 값을 사용 하 여 <xref:System.Windows.Forms.ScrollBars.Horizontal> 스크롤 막대 또는 <xref:System.Windows.Forms.ScrollBars.Both>위의 합니다.</span><span class="sxs-lookup"><span data-stu-id="3dfc2-124">Use this value if you chose <xref:System.Windows.Forms.ScrollBars.Horizontal> scroll bars or <xref:System.Windows.Forms.ScrollBars.Both>, above.</span></span>|  
    |<span data-ttu-id="3dfc2-125">`true`(기본값)</span><span class="sxs-lookup"><span data-stu-id="3dfc2-125">`true` (default)</span></span>|<span data-ttu-id="3dfc2-126">가로 스크롤 막대가 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3dfc2-126">The horizontal scrollbar will not appear.</span></span> <span data-ttu-id="3dfc2-127">선택한 경우이 값을 사용 하 여 <xref:System.Windows.Forms.ScrollBars.Vertical> 스크롤 막대 또는 <xref:System.Windows.Forms.ScrollBars.None>위의 하나 이상의 단락 표시를 합니다.</span><span class="sxs-lookup"><span data-stu-id="3dfc2-127">Use this value if you chose <xref:System.Windows.Forms.ScrollBars.Vertical> scroll bars or <xref:System.Windows.Forms.ScrollBars.None>, above, to display one or more paragraphs.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3dfc2-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3dfc2-128">See Also</span></span>  
 <xref:System.Windows.Forms.TextBox>  
 [<span data-ttu-id="3dfc2-129">TextBox 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="3dfc2-129">TextBox Control Overview</span></span>](../../../../docs/framework/winforms/controls/textbox-control-overview-windows-forms.md)  
 [<span data-ttu-id="3dfc2-130">방법: Windows Forms TextBox 컨트롤에서 삽입 지점 제어</span><span class="sxs-lookup"><span data-stu-id="3dfc2-130">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)  
 [<span data-ttu-id="3dfc2-131">방법: Windows Forms TextBox 컨트롤을 사용하여 암호 텍스트 상자 만들기</span><span class="sxs-lookup"><span data-stu-id="3dfc2-131">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)  
 [<span data-ttu-id="3dfc2-132">방법: 읽기 전용 텍스트 상자 만들기</span><span class="sxs-lookup"><span data-stu-id="3dfc2-132">How to: Create a Read-Only Text Box</span></span>](../../../../docs/framework/winforms/controls/how-to-create-a-read-only-text-box-windows-forms.md)  
 [<span data-ttu-id="3dfc2-133">방법: 문자열에 인용 부호 넣기</span><span class="sxs-lookup"><span data-stu-id="3dfc2-133">How to: Put Quotation Marks in a String</span></span>](../../../../docs/framework/winforms/controls/how-to-put-quotation-marks-in-a-string-windows-forms.md)  
 [<span data-ttu-id="3dfc2-134">방법: Windows Forms TextBox 컨트롤에서 텍스트 선택</span><span class="sxs-lookup"><span data-stu-id="3dfc2-134">How to: Select Text in the Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-select-text-in-the-windows-forms-textbox-control.md)  
 [<span data-ttu-id="3dfc2-135">TextBox 컨트롤</span><span class="sxs-lookup"><span data-stu-id="3dfc2-135">TextBox Control</span></span>](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)
