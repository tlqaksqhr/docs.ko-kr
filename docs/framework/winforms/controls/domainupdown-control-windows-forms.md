---
title: DomainUpDown 컨트롤(Windows Forms)
ms.date: 03/30/2017
helpviewer_keywords:
- DomainUpDown control [Windows Forms]
- spin button control [Windows Forms], up-down controls
- up-down controls
- spin button control
- up-down controls [Windows Forms], spin button controls
ms.assetid: fb7cf017-e931-4a95-9d21-8caee4ee122a
ms.openlocfilehash: c23f374f1ec9cab6e43b12d32b97c40533ac36cb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33527328"
---
# <a name="domainupdown-control-windows-forms"></a><span data-ttu-id="49fe7-102">DomainUpDown 컨트롤(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="49fe7-102">DomainUpDown Control (Windows Forms)</span></span>
<span data-ttu-id="49fe7-103">Windows Forms <xref:System.Windows.Forms.DomainUpDown> 컨트롤 쌍의 단추와 텍스트 상자의 조합 용 모양 목록에서 위로 또는 아래로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="49fe7-103">The Windows Forms <xref:System.Windows.Forms.DomainUpDown> control looks like a combination of a text box and a pair of buttons for moving up or down through a list.</span></span> <span data-ttu-id="49fe7-104">컨트롤은 표시 하거나 선택 목록에서 텍스트 문자열을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="49fe7-104">The control displays and sets a text string from a list of choices.</span></span> <span data-ttu-id="49fe7-105">위쪽 및 아래쪽 목록 사이 이동 하는 단추를 클릭 하 여, 위쪽 및 아래쪽 화살표 키를 누르거나 또는 목록에 있는 항목과 일치 하는 문자열을 입력 하 여 사용자 문자열을 선택할 수입니다.</span><span class="sxs-lookup"><span data-stu-id="49fe7-105">The user can select the string by clicking up and down buttons to move through a list, by pressing the UP and DOWN ARROW keys, or by typing a string that matches an item in the list.</span></span> <span data-ttu-id="49fe7-106">이름의 사전순으로 정렬된 된 목록에서 항목을 선택 하는이 컨트롤에 대 한 가능한 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="49fe7-106">One possible use for this control is for selecting items from an alphabetically sorted list of names.</span></span> <span data-ttu-id="49fe7-107">(설정 목록을 정렬 하는 <xref:System.Windows.Forms.DomainUpDown.Sorted%2A> 속성을 `true`.) 이 컨트롤의 기능 목록 상자 또는 콤보 상자에 매우 유사 하지만 매우 작은 공간을 차지 합니다.</span><span class="sxs-lookup"><span data-stu-id="49fe7-107">(To sort the list, set the <xref:System.Windows.Forms.DomainUpDown.Sorted%2A> property to `true`.) The function of this control is very similar to the list box or combo box, but it takes up very little space.</span></span>  
  
 <span data-ttu-id="49fe7-108">컨트롤의 주요 속성은 <xref:System.Windows.Forms.DomainUpDown.Items%2A>, <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A>, 및 <xref:System.Windows.Forms.DomainUpDown.Wrap%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="49fe7-108">The key properties of the control are <xref:System.Windows.Forms.DomainUpDown.Items%2A>, <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A>, and <xref:System.Windows.Forms.DomainUpDown.Wrap%2A>.</span></span> <span data-ttu-id="49fe7-109"><xref:System.Windows.Forms.DomainUpDown.Items%2A> 속성 컨트롤에 텍스트 값을 표시 하는 개체의 목록을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="49fe7-109">The <xref:System.Windows.Forms.DomainUpDown.Items%2A> property contains the list of objects whose text values are displayed in the control.</span></span> <span data-ttu-id="49fe7-110">경우 <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A> 로 설정 된 `false`, 사용자가 하 고 목록에서 값을 일치 하는 텍스트를 자동으로 완성 하는 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="49fe7-110">If <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A> is set to `false`, the control automatically completes text that the user types and matches it to a value in the list.</span></span> <span data-ttu-id="49fe7-111">경우 <xref:System.Windows.Forms.DomainUpDown.Wrap%2A> 로 설정 된 `true`, 마지막 항목을 스크롤할 첫 번째 항목 목록에서 이동 하 고 그 반대로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="49fe7-111">If <xref:System.Windows.Forms.DomainUpDown.Wrap%2A> is set to `true`, scrolling past the last item will take you to the first item in the list and vice versa.</span></span> <span data-ttu-id="49fe7-112">컨트롤의 주요 메서드는 <xref:System.Windows.Forms.DomainUpDown.UpButton%2A> 및 <xref:System.Windows.Forms.DomainUpDown.DownButton%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="49fe7-112">The key methods of the control are <xref:System.Windows.Forms.DomainUpDown.UpButton%2A> and <xref:System.Windows.Forms.DomainUpDown.DownButton%2A>.</span></span>  
  
 <span data-ttu-id="49fe7-113">이 컨트롤에는 텍스트 문자열만 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="49fe7-113">This control displays only text strings.</span></span> <span data-ttu-id="49fe7-114">숫자 값을 표시 하는 컨트롤 사용은 <xref:System.Windows.Forms.NumericUpDown> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="49fe7-114">If you want a control that displays numeric values, use the <xref:System.Windows.Forms.NumericUpDown> control.</span></span> <span data-ttu-id="49fe7-115">자세한 내용은 참조 [NumericUpDown 컨트롤](../../../../docs/framework/winforms/controls/numericupdown-control-windows-forms.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="49fe7-115">For more information, see [NumericUpDown Control](../../../../docs/framework/winforms/controls/numericupdown-control-windows-forms.md) .</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="49fe7-116">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="49fe7-116">In This Section</span></span>  
 [<span data-ttu-id="49fe7-117">DomainUpDown 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="49fe7-117">DomainUpDown Control Overview</span></span>](../../../../docs/framework/winforms/controls/domainupdown-control-overview-windows-forms.md)  
 <span data-ttu-id="49fe7-118">일반적인 개념을 소개는 <xref:System.Windows.Forms.DomainUpDown> 컨트롤 사용자가 탐색 하 고 텍스트 문자열의 목록에서 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49fe7-118">Introduces the general concepts of the <xref:System.Windows.Forms.DomainUpDown> control, which allows users to browse through and select from a list of text strings.</span></span>  
  
 [<span data-ttu-id="49fe7-119">방법: 프로그래밍 방식으로 Windows Forms DomainUpDown 컨트롤에 항목 추가</span><span class="sxs-lookup"><span data-stu-id="49fe7-119">How to: Add Items to Windows Forms DomainUpDown Controls Programmatically</span></span>](../../../../docs/framework/winforms/controls/how-to-add-items-to-windows-forms-domainupdown-controls-programmatically.md)  
 <span data-ttu-id="49fe7-120">텍스트 문자열을 지정 하는 방법에 설명 된 <xref:System.Windows.Forms.DomainUpDown> 표시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="49fe7-120">Describes how to specify the text strings the <xref:System.Windows.Forms.DomainUpDown> control should display.</span></span>  
  
 [<span data-ttu-id="49fe7-121">방법: Windows Forms DomainUpDown 컨트롤에서 항목 제거</span><span class="sxs-lookup"><span data-stu-id="49fe7-121">How to: Remove Items from Windows Forms DomainUpDown Controls</span></span>](../../../../docs/framework/winforms/controls/how-to-remove-items-from-windows-forms-domainupdown-controls.md)  
 <span data-ttu-id="49fe7-122">항목을 삭제 하는 방법에 설명 된 <xref:System.Windows.Forms.DomainUpDown> 코드에서 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="49fe7-122">Describes how to delete items from the <xref:System.Windows.Forms.DomainUpDown> control in code.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="49fe7-123">참조</span><span class="sxs-lookup"><span data-stu-id="49fe7-123">Reference</span></span>  
 <xref:System.Windows.Forms.DomainUpDown>  
 <span data-ttu-id="49fe7-124">이 클래스를 설명하고 모든 해당 멤버의 링크를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="49fe7-124">Describes this class and has links to all its members.</span></span>  
  
 <xref:System.Windows.Forms.NumericUpDown>  
 <span data-ttu-id="49fe7-125">이 클래스를 설명 하 고 모든 해당 멤버에 대 한 링크가...</span><span class="sxs-lookup"><span data-stu-id="49fe7-125">Describes this class and has links to all its members..</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="49fe7-126">관련 단원</span><span class="sxs-lookup"><span data-stu-id="49fe7-126">Related Sections</span></span>  
 [<span data-ttu-id="49fe7-127">Windows Forms에서 사용할 수 있는 컨트롤</span><span class="sxs-lookup"><span data-stu-id="49fe7-127">Controls You Can Use On Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 <span data-ttu-id="49fe7-128">사용 방법에 대한 정보 링크를 포함하는 Windows Forms 컨트롤의 전체 목록을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="49fe7-128">Provides a complete list of Windows Forms controls, with links to information on their use.</span></span>
