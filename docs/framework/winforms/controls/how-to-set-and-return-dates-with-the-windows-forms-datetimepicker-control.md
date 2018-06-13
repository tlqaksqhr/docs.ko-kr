---
title: '방법: Windows Forms DateTimePicker 컨트롤을 사용하여 날짜 설정 및 반환'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- dates [Windows Forms], setting in DateTimePicker
- DateTimePicker control [Windows Forms], setting and returning dates
- examples [Windows Forms], DateTimePicker control
ms.assetid: a8a48d68-e4b5-426e-9764-51230fc9acd2
ms.openlocfilehash: 017224aa493bfe0cd519df482a4d00e16f889a1a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33535671"
---
# <a name="how-to-set-and-return-dates-with-the-windows-forms-datetimepicker-control"></a><span data-ttu-id="29d78-102">방법: Windows Forms DateTimePicker 컨트롤을 사용하여 날짜 설정 및 반환</span><span class="sxs-lookup"><span data-stu-id="29d78-102">How to: Set and Return Dates with the Windows Forms DateTimePicker Control</span></span>
<span data-ttu-id="29d78-103">Windows Forms <xref:System.Windows.Forms.DateTimePicker> 컨트롤의 현재 선택된 날짜 또는 시간은 <xref:System.Windows.Forms.DateTimePicker.Value%2A> 속성에 의해 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="29d78-103">The currently selected date or time in the Windows Forms <xref:System.Windows.Forms.DateTimePicker> control is determined by the <xref:System.Windows.Forms.DateTimePicker.Value%2A> property.</span></span> <span data-ttu-id="29d78-104">컨트롤이 표시되기 전에(예: 디자인 타임에 또는 폼의 <xref:System.Windows.Forms.Form.Load> 이벤트에서) <xref:System.Windows.Forms.DateTimePicker.Value%2A> 속성을 설정하여 컨트롤에서 초기에 선택되는 날짜를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29d78-104">You can set the <xref:System.Windows.Forms.DateTimePicker.Value%2A> property before the control is displayed (for example, at design time or in the form's <xref:System.Windows.Forms.Form.Load> event) to determine which date will be initially selected in the control.</span></span> <span data-ttu-id="29d78-105">기본적으로 컨트롤의 <xref:System.Windows.Forms.DateTimePicker.Value%2A>는 현재 날짜로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="29d78-105">By default, the control's <xref:System.Windows.Forms.DateTimePicker.Value%2A> is set to the current date.</span></span> <span data-ttu-id="29d78-106">코드에서 컨트롤의 <xref:System.Windows.Forms.DateTimePicker.Value%2A>를 변경하는 경우 폼의 컨트롤이 새 설정을 반영하도록 자동으로 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="29d78-106">If you change the control's <xref:System.Windows.Forms.DateTimePicker.Value%2A> in code, the control is automatically updated on the form to reflect the new setting.</span></span>  
  
 <span data-ttu-id="29d78-107"><xref:System.Windows.Forms.DateTimePicker.Value%2A> 속성은 <xref:System.DateTime> 구조체를 해당 값으로 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="29d78-107">The <xref:System.Windows.Forms.DateTimePicker.Value%2A> property returns a <xref:System.DateTime> structure as its value.</span></span> <span data-ttu-id="29d78-108">표시된 날짜에 대한 특정 정보를 반환하는 <xref:System.DateTime> 구조체의 여러 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29d78-108">There are several properties of the <xref:System.DateTime> structure that return specific information about the displayed date.</span></span> <span data-ttu-id="29d78-109">이러한 속성은 값을 반환하는 데만 사용할 수 있습니다. 값을 설정하는 데 사용하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="29d78-109">These properties can only be used to return a value; do not use them to set a value.</span></span>  
  
-   <span data-ttu-id="29d78-110">날짜 값의 경우 <xref:System.DateTime.Month%2A>, <xref:System.DateTime.Day%2A> 및 <xref:System.DateTime.Year%2A> 속성은 선택한 날짜의 해당 시간 단위에 대한 정수 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="29d78-110">For date values, the <xref:System.DateTime.Month%2A>, <xref:System.DateTime.Day%2A>, and <xref:System.DateTime.Year%2A> properties return integer values for those time units of the selected date.</span></span> <span data-ttu-id="29d78-111"><xref:System.DateTime.DayOfWeek%2A> 속성은 선택한 요일을 나타내는 값을 반환합니다(가능한 값은 <xref:System.DayOfWeek> 열거형에 나열되어 있음).</span><span class="sxs-lookup"><span data-stu-id="29d78-111">The <xref:System.DateTime.DayOfWeek%2A> property returns a value indicating the selected day of the week (possible values are listed in the <xref:System.DayOfWeek> enumeration).</span></span>  
  
-   <span data-ttu-id="29d78-112">시간 값의 경우 <xref:System.DateTime.Hour%2A>, <xref:System.DateTime.Minute%2A>, <xref:System.DateTime.Second%2A> 및 <xref:System.DateTime.Millisecond%2A> 속성은 해당 시간 단위에 대한 정수 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="29d78-112">For time values, the <xref:System.DateTime.Hour%2A>, <xref:System.DateTime.Minute%2A>, <xref:System.DateTime.Second%2A>, and <xref:System.DateTime.Millisecond%2A> properties return integer values for those time units.</span></span> <span data-ttu-id="29d78-113">시간을 표시 하도록 컨트롤을 구성 하려면 참조 [하는 방법: DateTimePicker 컨트롤에 의해 지정 시간 표시](../../../../docs/framework/winforms/controls/how-to-display-time-with-the-datetimepicker-control.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="29d78-113">To configure the control to display times, see [How to: Display Time with the DateTimePicker Control](../../../../docs/framework/winforms/controls/how-to-display-time-with-the-datetimepicker-control.md).</span></span>  
  
### <a name="to-set-the-date-and-time-value-of-the-control"></a><span data-ttu-id="29d78-114">컨트롤의 날짜 및 시간 값을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="29d78-114">To set the date and time value of the control</span></span>  
  
-   <span data-ttu-id="29d78-115"><xref:System.Windows.Forms.DateTimePicker.Value%2A> 속성을 날짜 또는 시간 값으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="29d78-115">Set the <xref:System.Windows.Forms.DateTimePicker.Value%2A> property to a date or time value.</span></span>  
  
    ```vb  
    DateTimePicker1.Value = New DateTime(2001, 10, 20)  
    ```  
  
    ```csharp  
    dateTimePicker1.Value = new DateTime(2001, 10, 20);  
    ```  
  
    ```cpp  
    dateTimePicker1->Value = DateTime(2001, 10, 20);  
    ```  
  
### <a name="to-return-the-date-and-time-value"></a><span data-ttu-id="29d78-116">날짜 및 시간 값을 반환하려면</span><span class="sxs-lookup"><span data-stu-id="29d78-116">To return the date and time value</span></span>  
  
-   <span data-ttu-id="29d78-117"><xref:System.Windows.Forms.DateTimePicker.Text%2A> 속성을 호출하여 컨트롤에서 지정된 형식의 전체 값을 반환하거나, <xref:System.Windows.Forms.DateTimePicker.Value%2A> 값의 적절한 메서드를 호출하여 값의 일부를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="29d78-117">Call the <xref:System.Windows.Forms.DateTimePicker.Text%2A> property to return the entire value as formatted in the control, or call the appropriate method of the <xref:System.Windows.Forms.DateTimePicker.Value%2A> property to return a part of the value.</span></span> <span data-ttu-id="29d78-118"><xref:System.Windows.Forms.DateTimePicker.ToString%2A>을 통해 사용자에게 표시할 수 있는 문자열로 정보를 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="29d78-118">Use <xref:System.Windows.Forms.DateTimePicker.ToString%2A> to convert the information into a string that can be displayed to the user.</span></span>  
  
    ```vb  
    MessageBox.Show("The selected value is ", DateTimePicker1.Text)  
    MessageBox.Show("The day of the week is ",   
       DateTimePicker1.Value.DayOfWeek.ToString)  
    MessageBox.Show("Millisecond is: ",   
       DateTimePicker1.Value.Millisecond.ToString)  
    ```  
  
    ```csharp  
    MessageBox.Show ("The selected value is " +   
       dateTimePicker1.Text);  
    MessageBox.Show ("The day of the week is " +   
       dateTimePicker1.Value.DayOfWeek.ToString());  
    MessageBox.Show("Millisecond is: " +   
       dateTimePicker1.Value.Millisecond.ToString());  
    ```  
  
    ```cpp  
    MessageBox::Show (String::Concat("The selected value is ",  
       dateTimePicker1->Text));  
    MessageBox::Show (String::Concat("The day of the week is ",  
       dateTimePicker1->Value.DayOfWeek.ToString()));  
    MessageBox::Show(String::Concat("Millisecond is: ",  
       dateTimePicker1->Value.Millisecond.ToString()));  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="29d78-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="29d78-119">See Also</span></span>  
 [<span data-ttu-id="29d78-120">DateTimePicker 컨트롤</span><span class="sxs-lookup"><span data-stu-id="29d78-120">DateTimePicker Control</span></span>](../../../../docs/framework/winforms/controls/datetimepicker-control-windows-forms.md)  
 [<span data-ttu-id="29d78-121">방법: Windows Forms DateTimePicker 컨트롤을 사용하여 날짜를 사용자 지정 형식으로 표시</span><span class="sxs-lookup"><span data-stu-id="29d78-121">How to: Display a Date in a Custom Format with the Windows Forms DateTimePicker Control</span></span>](../../../../docs/framework/winforms/controls/display-a-date-in-a-custom-format-with-wf-datetimepicker-control.md)
