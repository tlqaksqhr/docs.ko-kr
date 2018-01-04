---
title: "방법: Windows Forms DateTimePicker 컨트롤을 사용하여 날짜를 사용자 지정 형식으로 표시"
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
- DateTimePicker control [Windows Forms], display styles
- examples [Windows Forms], DateTimePicker control
- dates [Windows Forms], displaying in DateTimePicker control
ms.assetid: 39767691-2d2b-46b6-a663-b7901e581a6e
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a5f5c7d856991ae8e0bf7caff656bf7010255628
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-display-a-date-in-a-custom-format-with-the-windows-forms-datetimepicker-control"></a><span data-ttu-id="404d3-102">방법: Windows Forms DateTimePicker 컨트롤을 사용하여 날짜를 사용자 지정 형식으로 표시</span><span class="sxs-lookup"><span data-stu-id="404d3-102">How to: Display a Date in a Custom Format with the Windows Forms DateTimePicker Control</span></span>
<span data-ttu-id="404d3-103">Windows Forms <xref:System.Windows.Forms.DateTimePicker> 컨트롤의 컨트롤에서 날짜와 시간 표시를 서식 지정에 유연성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="404d3-103">The Windows Forms <xref:System.Windows.Forms.DateTimePicker> control gives you flexibility in formatting the display of dates and times in the control.</span></span> <span data-ttu-id="404d3-104"><xref:System.Windows.Forms.DateTimePicker.Format%2A> 속성에 나열 된 미리 정의 된 형식에서 선택할 수 있습니다는 <xref:System.Windows.Forms.DateTimePickerFormat>합니다.</span><span class="sxs-lookup"><span data-stu-id="404d3-104">The <xref:System.Windows.Forms.DateTimePicker.Format%2A> property allows you to select from predefined formats, listed in the <xref:System.Windows.Forms.DateTimePickerFormat>.</span></span> <span data-ttu-id="404d3-105">아무것도 용도 맞게 충분 않으면에 나열 된 형식 문자를 사용 하 여 사용자 고유의 형식 스타일을 만들 수 있습니다 <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="404d3-105">If none of these is adequate for your purposes, you can create your own format style using format characters listed in <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A>.</span></span>  
  
### <a name="to-display-a-custom-format"></a><span data-ttu-id="404d3-106">사용자 지정 형식을 표시 하려면</span><span class="sxs-lookup"><span data-stu-id="404d3-106">To display a custom format</span></span>  
  
1.  <span data-ttu-id="404d3-107"><xref:System.Windows.Forms.DateTimePicker.Format%2A> 속성을 `DateTimePickerFormat.Custom`으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="404d3-107">Set the <xref:System.Windows.Forms.DateTimePicker.Format%2A> property to `DateTimePickerFormat.Custom`.</span></span>  
  
2.  <span data-ttu-id="404d3-108">설정의 <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A> 서식 문자열에는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="404d3-108">Set the <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A> property to a format string.</span></span>  
  
    ```vb  
    DateTimePicker1.Format = DateTimePickerFormat.Custom  
    ' Display the date as "Mon 27 Feb 2012".  
    DateTimePicker1.CustomFormat = "ddd dd MMM yyyy"  
    ```  
  
    ```csharp  
    dateTimePicker1.Format = DateTimePickerFormat.Custom;  
    // Display the date as "Mon 27 Feb 2012".  
    dateTimePicker1.CustomFormat = "ddd dd MMM yyyy";  
    ```  
  
    ```cpp  
    dateTimePicker1->Format = DateTimePickerFormat::Custom;  
    // Display the date as "Mon 27 Feb 2012".  
    dateTimePicker1->CustomFormat = "ddd dd MMM yyyy";  
    ```  
  
### <a name="to-add-text-to-the-formatted-value"></a><span data-ttu-id="404d3-109">형식이 지정 된 값에 텍스트를 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="404d3-109">To add text to the formatted value</span></span>  
  
1.  <span data-ttu-id="404d3-110">"M"과 같은 형식 문자 또는 같은 구분 기호가 아닌 모든 문자를 포함 하려면 작은따옴표를 사용 하 여 ":".</span><span class="sxs-lookup"><span data-stu-id="404d3-110">Use single quotation marks to enclose any character that is not a format character like "M" or a delimiter like ":".</span></span> <span data-ttu-id="404d3-111">아래의 형식 문자열 형식으로 현재 날짜를 표시 하는 예를 들어 "임: 05시 30분: 31 2012 년 3 월 2 일 금요일" 영어 (미국) 문화권입니다.</span><span class="sxs-lookup"><span data-stu-id="404d3-111">For example, the format string below displays the current date with the format "Today is: 05:30:31 Friday March 02, 2012" in the English (United States) culture.</span></span>  
  
    ```vb  
    DateTimePicker1.CustomFormat = "'Today is:' hh:mm:ss dddd MMMM dd, yyyy"  
    ```  
  
    ```csharp  
    dateTimePicker1.CustomFormat = "'Today is:' hh:mm:ss dddd MMMM dd, yyyy";  
    ```  
  
    ```cpp  
    dateTimePicker1->CustomFormat =  
       "'Today is:' hh:mm:ss dddd MMMM dd, yyyy";  
    ```  
  
     <span data-ttu-id="404d3-112">문화권 설정에 따라 따옴표로 묶이지 않은 문자를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="404d3-112">Depending on the culture setting, any characters not enclosed in single quotation marks may be changed.</span></span> <span data-ttu-id="404d3-113">위의 형식 문자열 형식으로 현재 날짜를 표시 하는 예를 들어 "임: 05시 30분: 31 2012 년 3 월 2 일 금요일" 영어 (미국) 문화권입니다.</span><span class="sxs-lookup"><span data-stu-id="404d3-113">For example, the format string above displays the current date with the format "Today is: 05:30:31 Friday March 02, 2012" in the English (United States) culture.</span></span> <span data-ttu-id="404d3-114">참고 것이 아니기 때문에 "hh: mm:"에서 같이 구분 기호 문자를 첫 번째 콜론 단일 따옴표에 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="404d3-114">Note that the first colon is enclosed in single quotation marks, because it is not intended to be a delimiting character as it is in "hh:mm:ss".</span></span> <span data-ttu-id="404d3-115">다른 문화권이 형식으로 나타날 수 있습니다 "임: 2012 년 3 월 2 일 금요일 05.30.31"입니다.</span><span class="sxs-lookup"><span data-stu-id="404d3-115">In another culture, the format might appear as "Today is: 05.30.31 Friday March 02, 2012".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="404d3-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="404d3-116">See Also</span></span>  
 [<span data-ttu-id="404d3-117">DateTimePicker 컨트롤</span><span class="sxs-lookup"><span data-stu-id="404d3-117">DateTimePicker Control</span></span>](../../../../docs/framework/winforms/controls/datetimepicker-control-windows-forms.md)  
 [<span data-ttu-id="404d3-118">방법: Windows Forms DateTimePicker 컨트롤을 사용하여 날짜 설정 및 반환</span><span class="sxs-lookup"><span data-stu-id="404d3-118">How to: Set and Return Dates with the Windows Forms DateTimePicker Control</span></span>](../../../../docs/framework/winforms/controls/how-to-set-and-return-dates-with-the-windows-forms-datetimepicker-control.md)
