---
title: ListBox 대신 Windows Forms ComboBox를 사용해야 하는 경우
ms.date: 03/30/2017
helpviewer_keywords:
- ListBox control [Windows Forms], adding and removing items
- ListBox control [Windows Forms], vs. ComboBox
- bound controls [Windows Forms], combo boxes
- Windows Forms controls, data binding
- ComboBox control [Windows Forms], compared to ListBox
- combo boxes [Windows Forms], compared to list boxes
- ListBox control [Windows Forms], accessing items
- ListCount property
ms.assetid: 7bcaea58-1cfa-46db-9baf-b75a69d8f9ec
ms.openlocfilehash: 88b6a6023fbfdd8fa315fcd434357626ea69a9ae
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33537770"
---
# <a name="when-to-use-a-windows-forms-combobox-instead-of-a-listbox"></a><span data-ttu-id="4b497-102">ListBox 대신 Windows Forms ComboBox를 사용해야 하는 경우</span><span class="sxs-lookup"><span data-stu-id="4b497-102">When to Use a Windows Forms ComboBox Instead of a ListBox</span></span>
<span data-ttu-id="4b497-103"><xref:System.Windows.Forms.ComboBox> 및 <xref:System.Windows.Forms.ListBox> 컨트롤 유사 하 게 동작에 있으며 경우에 따라 수 서로 바꿔 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b497-103">The <xref:System.Windows.Forms.ComboBox> and the <xref:System.Windows.Forms.ListBox> controls have similar behaviors, and in some cases may be interchangeable.</span></span> <span data-ttu-id="4b497-104">그러나 하나 또는 다른 작업에 더 적절 한 경우 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b497-104">There are times, however, when one or the other is more appropriate to a task.</span></span>  
  
 <span data-ttu-id="4b497-105">일반적으로 콤보 상자는 제안 된 선택 목록이 않으며 목록 상자는 목록에는 무엇이에 대 한 입력을 제한 하려는 경우 적절 한 경우 적절 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b497-105">Generally, a combo box is appropriate when there is a list of suggested choices, and a list box is appropriate when you want to limit input to what is on the list.</span></span> <span data-ttu-id="4b497-106">콤보 상자 목록에 없는 항목에 입력할 수 있도록 텍스트 상자 필드를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b497-106">A combo box contains a text box field, so choices not on the list can be typed in.</span></span> <span data-ttu-id="4b497-107">경우는 예외는 <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> 속성이 <xref:System.Windows.Forms.ComboBoxStyle.DropDownList>합니다.</span><span class="sxs-lookup"><span data-stu-id="4b497-107">The exception is when the <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> property is set to <xref:System.Windows.Forms.ComboBoxStyle.DropDownList>.</span></span> <span data-ttu-id="4b497-108">이 경우 컨트롤의 첫 번째 문자를 입력 하는 경우 항목을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b497-108">In that case, the control will select an item if you type its first letter.</span></span>  
  
 <span data-ttu-id="4b497-109">또한, 콤보 상자 폼에서 공간을 절약 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b497-109">In addition, combo boxes save space on a form.</span></span> <span data-ttu-id="4b497-110">아래쪽 화살표를 클릭할 때까지 전체 목록이 표시 되지 않으므로, 콤보 상자 목록 상자에 적합 하지는 작은 공간에 쉽게 맞출 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b497-110">Because the full list is not displayed until the user clicks the down arrow, a combo box can easily fit in a small space where a list box would not fit.</span></span> <span data-ttu-id="4b497-111">경우는 예외는 <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> 속성이로 설정 되어 <xref:System.Windows.Forms.ComboBoxStyle.Simple>: 콤보 상자의 목록 상자 것 보다 더 많은 공간을 차지 하 고 전체 목록이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b497-111">An exception is when the <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> property is set to <xref:System.Windows.Forms.ComboBoxStyle.Simple>: the full list is displayed, and the combo box takes up more room than a list box would.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b497-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4b497-112">See Also</span></span>  
 <xref:System.Windows.Forms.ComboBox>  
 <xref:System.Windows.Forms.ListBox>  
 [<span data-ttu-id="4b497-113">방법: Windows Forms ComboBox, ListBox 또는 CheckedListBox 컨트롤에서 항목 추가 및 제거</span><span class="sxs-lookup"><span data-stu-id="4b497-113">How to: Add and Remove Items from a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>](../../../../docs/framework/winforms/controls/add-and-remove-items-from-a-wf-combobox.md)  
 [<span data-ttu-id="4b497-114">방법: Windows Forms ComboBox, ListBox 또는 CheckedListBox 컨트롤의 내용 정렬</span><span class="sxs-lookup"><span data-stu-id="4b497-114">How to: Sort the Contents of a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>](../../../../docs/framework/winforms/controls/sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)  
 [<span data-ttu-id="4b497-115">옵션 목록 표시에 사용된 Windows Forms 컨트롤</span><span class="sxs-lookup"><span data-stu-id="4b497-115">Windows Forms Controls Used to List Options</span></span>](../../../../docs/framework/winforms/controls/windows-forms-controls-used-to-list-options.md)
