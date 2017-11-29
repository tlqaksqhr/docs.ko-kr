---
title: "TextBox 컨트롤(Windows Forms)"
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
- TextBox control [Windows Forms]
ms.assetid: e5a06987-8aec-4271-b196-2245ba992d62
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4800b06b5d0bbc5ce51d7cf00798ca98ef8bf656
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="textbox-control-windows-forms"></a><span data-ttu-id="7afa4-102">TextBox 컨트롤(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="7afa4-102">TextBox Control (Windows Forms)</span></span>
<span data-ttu-id="7afa4-103">Windows Forms 텍스트 상자의 텍스트를 표시 하는 사용자 로부터 입력을 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7afa4-103">Windows Forms text boxes are used to get input from the user or to display text.</span></span> <span data-ttu-id="7afa4-104">`TextBox` 컨트롤은 일반적으로 편집 가능한 텍스트에 사용 것도 만들 수 있지만 읽기 전용입니다.</span><span class="sxs-lookup"><span data-stu-id="7afa4-104">The `TextBox` control is generally used for editable text, although it can also be made read-only.</span></span> <span data-ttu-id="7afa4-105">텍스트 상자는 여러 줄을 표시 하 고 텍스트는 컨트롤의 크기를 줄 바꿈할 기본 서식을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7afa4-105">Text boxes can display multiple lines, wrap text to the size of the control, and add basic formatting.</span></span> <span data-ttu-id="7afa4-106">`TextBox` 컨트롤을 표시 되거나 컨트롤에서 입력 텍스트의 서식을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7afa4-106">The `TextBox` control allows a single format for text displayed or entered in the control.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7afa4-107">단원 내용</span><span class="sxs-lookup"><span data-stu-id="7afa4-107">In This Section</span></span>  
 [<span data-ttu-id="7afa4-108">TextBox 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="7afa4-108">TextBox Control Overview</span></span>](../../../../docs/framework/winforms/controls/textbox-control-overview-windows-forms.md)  
 <span data-ttu-id="7afa4-109">이 컨트롤의 정의와 주요 기능 및 속성을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7afa4-109">Explains what this control is and its key features and properties.</span></span>  
  
 [<span data-ttu-id="7afa4-110">방법: Windows Forms TextBox 컨트롤에서 삽입 지점 제어</span><span class="sxs-lookup"><span data-stu-id="7afa4-110">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)  
 <span data-ttu-id="7afa4-111">편집 컨트롤의 포커스를 처음 가져오면 삽입 포인터가 표시 하는 위치를 지정 하기 위한 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="7afa4-111">Gives directions for specifying where the insertion point appears when an edit control first gets the focus.</span></span>  
  
 [<span data-ttu-id="7afa4-112">방법: Windows Forms TextBox 컨트롤을 사용하여 암호 텍스트 상자 만들기</span><span class="sxs-lookup"><span data-stu-id="7afa4-112">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)  
 <span data-ttu-id="7afa4-113">텍스트 상자에 입력 된 내용을 숨기는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="7afa4-113">Explains how to conceal what is typed into a text box.</span></span>  
  
 [<span data-ttu-id="7afa4-114">방법: 읽기 전용 텍스트 상자 만들기</span><span class="sxs-lookup"><span data-stu-id="7afa4-114">How to: Create a Read-Only Text Box</span></span>](../../../../docs/framework/winforms/controls/how-to-create-a-read-only-text-box-windows-forms.md)  
 <span data-ttu-id="7afa4-115">입력란의 내용이 변경 되지 않도록 방지 하는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="7afa4-115">Describes how to prevent the contents of a text box from being changed.</span></span>  
  
 [<span data-ttu-id="7afa4-116">방법: 문자열에 인용 부호 넣기</span><span class="sxs-lookup"><span data-stu-id="7afa4-116">How to: Put Quotation Marks in a String</span></span>](../../../../docs/framework/winforms/controls/how-to-put-quotation-marks-in-a-string-windows-forms.md)  
 <span data-ttu-id="7afa4-117">텍스트 상자에 문자열로 추가 인용 부호를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7afa4-117">Explains adding quotation marks to a string in a text box.</span></span>  
  
 [<span data-ttu-id="7afa4-118">방법: Windows Forms TextBox 컨트롤에서 텍스트 선택</span><span class="sxs-lookup"><span data-stu-id="7afa4-118">How to: Select Text in the Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-select-text-in-the-windows-forms-textbox-control.md)  
 <span data-ttu-id="7afa4-119">텍스트 상자에 텍스트를 강조 표시 하는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="7afa4-119">Explains how to highlight text in a text box.</span></span>  
  
 [<span data-ttu-id="7afa4-120">방법: Windows Forms TextBox 컨트롤에 여러 줄 표시</span><span class="sxs-lookup"><span data-stu-id="7afa4-120">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)  
 <span data-ttu-id="7afa4-121">만들기 텍스트 상자를 스크롤할 수 있는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="7afa4-121">Describes how to make a text box scrollable.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="7afa4-122">참조</span><span class="sxs-lookup"><span data-stu-id="7afa4-122">Reference</span></span>  
 <span data-ttu-id="7afa4-123"><xref:System.Windows.Forms.TextBox> 클래스</span><span class="sxs-lookup"><span data-stu-id="7afa4-123"><xref:System.Windows.Forms.TextBox> class</span></span>  
 <span data-ttu-id="7afa4-124">이 클래스를 설명하고 모든 해당 멤버의 링크를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="7afa4-124">Describes this class and has links to all its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="7afa4-125">관련 단원</span><span class="sxs-lookup"><span data-stu-id="7afa4-125">Related Sections</span></span>  
 [<span data-ttu-id="7afa4-126">Windows Forms에 사용할 수 있는 컨트롤</span><span class="sxs-lookup"><span data-stu-id="7afa4-126">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 <span data-ttu-id="7afa4-127">사용 방법에 대한 정보 링크를 포함하는 Windows Forms 컨트롤의 전체 목록을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7afa4-127">Provides a complete list of Windows Forms controls, with links to information on their use.</span></span>
