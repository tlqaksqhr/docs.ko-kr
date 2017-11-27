---
title: "방법: Windows Forms MonthCalendar 컨트롤을 사용하여 특정 날짜를 굵게 표시"
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
- calendars [Windows Forms], displaying dates in bold
- examples [Windows Forms], calendar controls
- GetDayBold event
- MonthCalendar control [Windows Forms], dates displayed in bold
ms.assetid: 8b20db5b-8118-4825-90e8-2c45c186ac7d
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 18a199592a8bfbef2e4a15b056e37af6d885f5f8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-display-specific-days-in-bold-with-the-windows-forms-monthcalendar-control"></a><span data-ttu-id="1c971-102">방법: Windows Forms MonthCalendar 컨트롤을 사용하여 특정 날짜를 굵게 표시</span><span class="sxs-lookup"><span data-stu-id="1c971-102">How to: Display Specific Days in Bold with the Windows Forms MonthCalendar Control</span></span>
<span data-ttu-id="1c971-103">Windows Forms <xref:System.Windows.Forms.MonthCalendar> 반복적으로 또는 단 수 날짜로 컨트롤 굵은 글꼴로 일 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c971-103">The Windows Forms <xref:System.Windows.Forms.MonthCalendar> control can display days in bold type, either as singular dates or on a repeating basis.</span></span> <span data-ttu-id="1c971-104">휴일 및 주말 같은 특정 날짜에 주목 하도록이 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c971-104">You might do this to draw attention to special dates, such as holidays and weekends.</span></span>  
  
 <span data-ttu-id="1c971-105">이 기능을 제어 하는 세 가지 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="1c971-105">Three properties control this feature.</span></span> <span data-ttu-id="1c971-106"><xref:System.Windows.Forms.MonthCalendar.BoldedDates%2A> 속성 단일 날짜를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c971-106">The <xref:System.Windows.Forms.MonthCalendar.BoldedDates%2A> property contains single dates.</span></span> <span data-ttu-id="1c971-107"><xref:System.Windows.Forms.MonthCalendar.AnnuallyBoldedDates%2A> 속성 매년 굵게 표시 되는 날짜를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c971-107">The <xref:System.Windows.Forms.MonthCalendar.AnnuallyBoldedDates%2A> property contains dates that appear in bold every year.</span></span> <span data-ttu-id="1c971-108"><xref:System.Windows.Forms.MonthCalendar.MonthlyBoldedDates%2A> 속성 매월 굵게 표시 되는 날짜를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c971-108">The <xref:System.Windows.Forms.MonthCalendar.MonthlyBoldedDates%2A> property contains dates that appear in bold every month.</span></span> <span data-ttu-id="1c971-109">이러한 각 속성의 배열을 포함 <xref:System.DateTime> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="1c971-109">Each of these properties contains an array of <xref:System.DateTime> objects.</span></span> <span data-ttu-id="1c971-110">를 추가 하거나 날짜 이러한 목록에서 제거 하려면 추가 하거나 제거 해야 합니다는 <xref:System.DateTime> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="1c971-110">To add or remove a date from one of these lists, you must add or remove a <xref:System.DateTime> object.</span></span>  
  
### <a name="to-make-a-date-appear-in-bold-type"></a><span data-ttu-id="1c971-111">날짜를 굵게 표시 하려면</span><span class="sxs-lookup"><span data-stu-id="1c971-111">To make a date appear in bold type</span></span>  
  
1.  <span data-ttu-id="1c971-112">만들기는 <xref:System.DateTime> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="1c971-112">Create the <xref:System.DateTime> objects.</span></span>  
  
    ```vb  
    Dim myVacation1 As Date = New DateTime(2001, 6, 10)  
    Dim myVacation2 As Date = New DateTime(2001, 6, 17)  
    ```  
  
    ```csharp  
    DateTime myVacation1 = new DateTime(2001, 6, 10);  
    DateTime myVacation2 = new DateTime(2001, 6, 17);  
    ```  
  
    ```cpp  
    DateTime myVacation1 = DateTime(2001, 6, 10);  
    DateTime myVacation2 = DateTime(2001, 6, 17);  
    ```  
  
2.  <span data-ttu-id="1c971-113">호출 하 여 단일 날짜를 굵게는 <xref:System.Windows.Forms.MonthCalendar.AddBoldedDate%2A>, <xref:System.Windows.Forms.MonthCalendar.AddAnnuallyBoldedDate%2A>, 또는 <xref:System.Windows.Forms.MonthCalendar.AddMonthlyBoldedDate%2A> 의 메서드는 <xref:System.Windows.Forms.MonthCalendar> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c971-113">Make a single date bold by calling the <xref:System.Windows.Forms.MonthCalendar.AddBoldedDate%2A>, <xref:System.Windows.Forms.MonthCalendar.AddAnnuallyBoldedDate%2A>, or <xref:System.Windows.Forms.MonthCalendar.AddMonthlyBoldedDate%2A> method of the <xref:System.Windows.Forms.MonthCalendar> control.</span></span>  
  
    ```vb  
    MonthCalendar1.AddBoldedDate(myVacation1)  
    MonthCalendar1.AddBoldedDate(myVacation2)  
    ```  
  
    ```csharp  
    monthCalendar1.AddBoldedDate(myVacation1);  
    monthCalendar1.AddBoldedDate(myVacation2);  
    ```  
  
    ```cpp  
    monthCalendar1->AddBoldedDate(myVacation1);  
    monthCalendar1->AddBoldedDate(myVacation2);  
    ```  
  
     <span data-ttu-id="1c971-114">– 또는 –</span><span class="sxs-lookup"><span data-stu-id="1c971-114">–or–</span></span>  
  
     <span data-ttu-id="1c971-115">굵게 표시 된 날짜 집합이 한 번에 모두의 배열을 만들어 <xref:System.DateTime> 개체 및 속성 중 하나에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c971-115">Make a set of dates bold all at once by creating an array of <xref:System.DateTime> objects and assigning it to one of the properties.</span></span>  
  
    ```vb  
    Dim VacationDates As DateTime() = {myVacation1, myVacation2}  
    MonthCalendar1.BoldedDates = VacationDates  
    ```  
  
    ```csharp  
    DateTime[] VacationDates = {myVacation1, myVacation2};  
    monthCalendar1.BoldedDates = VacationDates;  
    ```  
  
    ```cpp  
    Array<DateTime>^ VacationDates = {myVacation1, myVacation2};  
    monthCalendar1->BoldedDates = VacationDates;  
    ```  
  
### <a name="to-make-a-date-appear-in-the-regular-font"></a><span data-ttu-id="1c971-116">날짜는 일반 글꼴로 표시 하려면</span><span class="sxs-lookup"><span data-stu-id="1c971-116">To make a date appear in the regular font</span></span>  
  
1.  <span data-ttu-id="1c971-117">호출 하 여 일반 글꼴로 표시 단일 굵게 표시 된 날짜는 <xref:System.Windows.Forms.MonthCalendar.RemoveBoldedDate%2A>, <xref:System.Windows.Forms.MonthCalendar.RemoveAnnuallyBoldedDate%2A>, 또는 <xref:System.Windows.Forms.MonthCalendar.RemoveMonthlyBoldedDate%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="1c971-117">Make a single bolded date appear in the regular font by calling the <xref:System.Windows.Forms.MonthCalendar.RemoveBoldedDate%2A>, <xref:System.Windows.Forms.MonthCalendar.RemoveAnnuallyBoldedDate%2A>, or <xref:System.Windows.Forms.MonthCalendar.RemoveMonthlyBoldedDate%2A> method.</span></span>  
  
    ```vb  
    MonthCalendar1.RemoveBoldedDate(myVacation1)  
    MonthCalendar1.RemoveBoldedDate(myVacation2)  
    ```  
  
    ```csharp  
    monthCalendar1.RemoveBoldedDate(myVacation1);  
    monthCalendar1.RemoveBoldedDate(myVacation2);  
    ```  
  
    ```cpp  
    monthCalendar1->RemoveBoldedDate(myVacation1);  
    monthCalendar1->RemoveBoldedDate(myVacation2);  
    ```  
  
     <span data-ttu-id="1c971-118">– 또는 –</span><span class="sxs-lookup"><span data-stu-id="1c971-118">–or–</span></span>  
  
     <span data-ttu-id="1c971-119">굵게 표시 되는 모든 날짜를 호출 하 여 세 목록 중 하나에서 제거 된 <xref:System.Windows.Forms.MonthCalendar.RemoveAllBoldedDates%2A>, <xref:System.Windows.Forms.MonthCalendar.RemoveAllAnnuallyBoldedDates%2A>, 또는 <xref:System.Windows.Forms.MonthCalendar.RemoveAllMonthlyBoldedDates%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="1c971-119">Remove all the bolded dates from one of the three lists by calling the <xref:System.Windows.Forms.MonthCalendar.RemoveAllBoldedDates%2A>, <xref:System.Windows.Forms.MonthCalendar.RemoveAllAnnuallyBoldedDates%2A>, or <xref:System.Windows.Forms.MonthCalendar.RemoveAllMonthlyBoldedDates%2A> method.</span></span>  
  
    ```vb  
    MonthCalendar1.RemoveAllBoldedDates()  
    ```  
  
    ```csharp  
    monthCalendar1.RemoveAllBoldedDates();  
    ```  
  
    ```cpp  
    monthCalendar1->RemoveAllBoldedDates();  
    ```  
  
2.  <span data-ttu-id="1c971-120">호출 하 여 글꼴의 모양을 업데이트는 <xref:System.Windows.Forms.MonthCalendar.UpdateBoldedDates%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="1c971-120">Update the appearance of the font by calling the <xref:System.Windows.Forms.MonthCalendar.UpdateBoldedDates%2A> method.</span></span>  
  
    ```vb  
    MonthCalendar1.UpdateBoldedDates()  
    ```  
  
    ```csharp  
    monthCalendar1.UpdateBoldedDates();  
    ```  
  
    ```cpp  
    monthCalendar1->UpdateBoldedDates();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="1c971-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1c971-121">See Also</span></span>  
 [<span data-ttu-id="1c971-122">MonthCalendar 컨트롤</span><span class="sxs-lookup"><span data-stu-id="1c971-122">MonthCalendar Control</span></span>](../../../../docs/framework/winforms/controls/monthcalendar-control-windows-forms.md)  
 [<span data-ttu-id="1c971-123">방법: Windows Forms MonthCalendar 컨트롤에서 날짜 범위 선택</span><span class="sxs-lookup"><span data-stu-id="1c971-123">How to: Select a Range of Dates in the Windows Forms MonthCalendar Control</span></span>](../../../../docs/framework/winforms/controls/how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control.md)  
 [<span data-ttu-id="1c971-124">방법: Windows Forms MonthCalendar 컨트롤의 모양 변경</span><span class="sxs-lookup"><span data-stu-id="1c971-124">How to: Change the Windows Forms MonthCalendar Control's Appearance</span></span>](../../../../docs/framework/winforms/controls/how-to-change-monthcalendar-control-appearance.md)  
 [<span data-ttu-id="1c971-125">방법: Windows Forms MonthCalendar 컨트롤에서 여러 달 표시</span><span class="sxs-lookup"><span data-stu-id="1c971-125">How to: Display More than One Month in the Windows Forms MonthCalendar Control</span></span>](../../../../docs/framework/winforms/controls/display-more-than-one-month-wf-monthcalendar-control.md)
