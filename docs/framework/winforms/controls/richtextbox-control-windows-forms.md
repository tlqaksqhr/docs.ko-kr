---
title: "RichTextBox 컨트롤(Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- text boxes
- RichTextBox control [Windows Forms]
- rich edit controls
ms.assetid: 3225f2ef-c6d9-4bd4-9d3e-2219e58edbf2
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4325fd3eb2e3d7179ddb5270d073c7ba5f0f383f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="richtextbox-control-windows-forms"></a><span data-ttu-id="80a2c-102">RichTextBox 컨트롤(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="80a2c-102">RichTextBox Control (Windows Forms)</span></span>
<span data-ttu-id="80a2c-103">Windows Forms `RichTextBox` 표시, 입력, 및 서식이 지정 된 텍스트를 조작 하기 위한 컨트롤을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="80a2c-103">The Windows Forms `RichTextBox` control is used for displaying, entering, and manipulating text with formatting.</span></span> <span data-ttu-id="80a2c-104">`RichTextBox` 모든 작업을 수행 하는 컨트롤의 <xref:System.Windows.Forms.TextBox> 컨트롤 포함 하지만 또한 글꼴, 색 및 링크를 표시, 파일, 실행 취소 및 편집 작업을 다시 실행에서 텍스트 및 포함된 이미지를 로드 및 지정 된 문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="80a2c-104">The `RichTextBox` control does everything the <xref:System.Windows.Forms.TextBox> control does, but it can also display fonts, colors, and links; load text and embedded images from a file; undo and redo editing operations; and find specified characters.</span></span> <span data-ttu-id="80a2c-105">`RichTextBox` 컨트롤은 일반적으로 텍스트를 조작 하 고 Microsoft Word와 같은 워드 프로세싱 응용 프로그램과 유사한 기능을 표시 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="80a2c-105">The `RichTextBox` control is typically used to provide text manipulation and display features similar to word processing applications such as Microsoft Word.</span></span> <span data-ttu-id="80a2c-106">와 같은 <xref:System.Windows.Forms.TextBox> 컨트롤을는 `RichTextBox` 컨트롤; 스크롤 막대를 표시할 수 있습니다 하지만 달리는 <xref:System.Windows.Forms.TextBox> 컨트롤을 기본적으로 가로 및 세로 스크롤 막대를 표시 하 고 추가적인 스크롤 막대 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="80a2c-106">Like the <xref:System.Windows.Forms.TextBox> control, the `RichTextBox` control can display scroll bars; but unlike the <xref:System.Windows.Forms.TextBox> control, it displays both horizontal and vertical scrollbars by default and has additional scrollbar settings.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="80a2c-107">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="80a2c-107">In This Section</span></span>  
 [<span data-ttu-id="80a2c-108">RichTextBox 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="80a2c-108">RichTextBox Control Overview</span></span>](../../../../docs/framework/winforms/controls/richtextbox-control-overview-windows-forms.md)  
 <span data-ttu-id="80a2c-109">일반적인 개념을 소개는 `RichTextBox` 사용자 입력을 허용 하는 컨트롤을 표시 및 서식 지정 옵션으로 텍스트를 조작 합니다.</span><span class="sxs-lookup"><span data-stu-id="80a2c-109">Introduces the general concepts of the `RichTextBox` control, which allows users to enter, display, and manipulate text with formatting options.</span></span>  
  
 [<span data-ttu-id="80a2c-110">방법: Windows Forms RichTextBox 컨트롤에서 서식 특성의 변경 시기 결정</span><span class="sxs-lookup"><span data-stu-id="80a2c-110">How to: Determine When Formatting Attributes Change in the Windows Forms RichTextBox Control</span></span>](../../../../docs/framework/winforms/controls/determine-when-formatting-attributes-change-wf-richtextbox-control.md)  
 <span data-ttu-id="80a2c-111">글꼴 및의 단락 서식 지정의 변경 내용을 추적 하는 방법에 설명 된 `RichTextBox` 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="80a2c-111">Explains how to keep track of changes in font and paragraph formatting in the `RichTextBox` control.</span></span>  
  
 [<span data-ttu-id="80a2c-112">방법: Windows Forms RichTextBox 컨트롤에서 스크롤 막대 표시</span><span class="sxs-lookup"><span data-stu-id="80a2c-112">How to: Display Scroll Bars in the Windows Forms RichTextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-display-scroll-bars-in-the-windows-forms-richtextbox-control.md)  
 <span data-ttu-id="80a2c-113">스크롤 막대에 사용할 수 있는 여러 선택 항목이 설명의 `RichTextBox` 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="80a2c-113">Describes the many choices available for scroll bars in the `RichTextBox` control.</span></span>  
  
 [<span data-ttu-id="80a2c-114">방법: Windows Forms RichTextBox 컨트롤을 사용하여 웹 스타일 링크 표시</span><span class="sxs-lookup"><span data-stu-id="80a2c-114">How to: Display Web-Style Links with the Windows Forms RichTextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-display-web-style-links-with-the-windows-forms-richtextbox-control.md)  
 <span data-ttu-id="80a2c-115">웹 사이트에 연결 하는 방법에 설명 된 `RichTextBox` 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="80a2c-115">Explains how to link to Web sites from the `RichTextBox` control.</span></span>  
  
 [<span data-ttu-id="80a2c-116">방법: Windows Forms RichTextBox 컨트롤에서 끌어서 놓기 작업 사용</span><span class="sxs-lookup"><span data-stu-id="80a2c-116">How to: Enable Drag-and-Drop Operations with the Windows Forms RichTextBox Control</span></span>](../../../../docs/framework/winforms/controls/enable-drag-and-drop-operations-with-wf-richtextbox-control.md)  
 <span data-ttu-id="80a2c-117">데이터를 끌어에 대 한 지침을 제공 된 `RichTextBox` 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="80a2c-117">Provides instructions for dragging data into the `RichTextBox` control.</span></span>  
  
 [<span data-ttu-id="80a2c-118">방법: Windows Forms RichTextBox 컨트롤에 파일 로드</span><span class="sxs-lookup"><span data-stu-id="80a2c-118">How to: Load Files into the Windows Forms RichTextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-load-files-into-the-windows-forms-richtextbox-control.md)  
 <span data-ttu-id="80a2c-119">기존 파일을 로드 하기 위한 지침을 제공는 `RichTextBox` 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="80a2c-119">Provides instructions for loading an existing file into the `RichTextBox` control.</span></span>  
  
 [<span data-ttu-id="80a2c-120">방법: Windows Forms RichTextBox 컨트롤을 사용하여 파일 저장</span><span class="sxs-lookup"><span data-stu-id="80a2c-120">How to: Save Files with the Windows Forms RichTextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-save-files-with-the-windows-forms-richtextbox-control.md)  
 <span data-ttu-id="80a2c-121">내용을 저장 하기 위한 지침을 제공는 `RichTextBox` 파일을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="80a2c-121">Provides instructions for saving the contents of the `RichTextBox` control to a file.</span></span>  
  
 [<span data-ttu-id="80a2c-122">방법: Windows Forms RichTextBox 컨트롤의 글꼴 특성 설정</span><span class="sxs-lookup"><span data-stu-id="80a2c-122">How to: Set Font Attributes for the Windows Forms RichTextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-set-font-attributes-for-the-windows-forms-richtextbox-control.md)  
 <span data-ttu-id="80a2c-123">글꼴 패밀리, 크기, 스타일 및의 텍스트 색을 설정 하는 방법에 설명 된 `RichTextBox` 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="80a2c-123">Describes how to set the font family, size, style, and color of text in the `RichTextBox` control.</span></span>  
  
 [<span data-ttu-id="80a2c-124">방법: Windows Forms RichTextBox 컨트롤을 사용하여 들여쓰기, 내어쓰기 및 글머리 기호 단락 설정</span><span class="sxs-lookup"><span data-stu-id="80a2c-124">How to: Set Indents, Hanging Indents, and Bulleted Paragraphs with the Windows Forms RichTextBox Control</span></span>](../../../../docs/framework/winforms/controls/set-indents-hanging-indents-bulleted-paragraphs-with-wf-richtextbox.md)  
 <span data-ttu-id="80a2c-125">단락 서식을 지정 하는 방법을 설명의 `RichTextBox` 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="80a2c-125">Describes how to format paragraphs in the `RichTextBox` control.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="80a2c-126">참조</span><span class="sxs-lookup"><span data-stu-id="80a2c-126">Reference</span></span>  
 <span data-ttu-id="80a2c-127"><xref:System.Windows.Forms.RichTextBox> 클래스</span><span class="sxs-lookup"><span data-stu-id="80a2c-127"><xref:System.Windows.Forms.RichTextBox> class</span></span>  
 <span data-ttu-id="80a2c-128">이 클래스를 설명하고 모든 해당 멤버의 링크를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="80a2c-128">Describes this class and has links to all its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="80a2c-129">관련 단원</span><span class="sxs-lookup"><span data-stu-id="80a2c-129">Related Sections</span></span>  
 [<span data-ttu-id="80a2c-130">Windows Forms에 사용할 수 있는 컨트롤</span><span class="sxs-lookup"><span data-stu-id="80a2c-130">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 <span data-ttu-id="80a2c-131">사용 방법에 대한 정보 링크를 포함하는 Windows Forms 컨트롤의 전체 목록을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="80a2c-131">Provides a complete list of Windows Forms controls, with links to information on their use.</span></span>  
  
 [<span data-ttu-id="80a2c-132">TextBox 컨트롤</span><span class="sxs-lookup"><span data-stu-id="80a2c-132">TextBox Control</span></span>](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)  
 <span data-ttu-id="80a2c-133">일반적인 개념을 소개는 <xref:System.Windows.Forms.TextBox> 사용자의 입력을 편집 하거나 여러 줄 수 있는 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="80a2c-133">Introduces the general concepts of the <xref:System.Windows.Forms.TextBox> control, which allows editable, multiline input from the user.</span></span>
