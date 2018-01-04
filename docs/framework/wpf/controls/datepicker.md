---
title: DatePicker
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- controls [WPF], DatePicker
- DatePicker control [WPF]
ms.assetid: 619765c8-8d25-4315-aec2-79aea08fed9f
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: bd2a1755ae076369661b2c9a7a2b744961cdb129
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="datepicker"></a><span data-ttu-id="188ec-102">DatePicker</span><span class="sxs-lookup"><span data-stu-id="188ec-102">DatePicker</span></span>
<span data-ttu-id="188ec-103"><xref:System.Windows.Controls.DatePicker> 컨트롤을 사용 하면 날짜를 입력 하거나 텍스트 필드에 또는 드롭 다운을 사용 하 여 <xref:System.Windows.Controls.Calendar> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="188ec-103">The <xref:System.Windows.Controls.DatePicker> control allows the user to select a date by either typing it into a text field or by using a drop-down <xref:System.Windows.Controls.Calendar> control.</span></span>  
  
 <span data-ttu-id="188ec-104">다음 그림에서는 한 <xref:System.Windows.Controls.DatePicker>합니다.</span><span class="sxs-lookup"><span data-stu-id="188ec-104">The following illustration shows a <xref:System.Windows.Controls.DatePicker>.</span></span>  
  
 <span data-ttu-id="188ec-105">![DatePicker 컨트롤](../../../../docs/framework/wpf/controls/media/ndp-datepicker.png "NDP_DatePicker")</span><span class="sxs-lookup"><span data-stu-id="188ec-105">![DatePicker control](../../../../docs/framework/wpf/controls/media/ndp-datepicker.png "NDP_DatePicker")</span></span>  
<span data-ttu-id="188ec-106">DatePicker 컨트롤</span><span class="sxs-lookup"><span data-stu-id="188ec-106">DatePicker Control</span></span>  
  
 <span data-ttu-id="188ec-107">대부분의 <xref:System.Windows.Controls.DatePicker> 컨트롤의 속성은 해당 기본 제공 관리 하기 위한 <xref:System.Windows.Controls.Calendar>, 및 함수에 해당 하는 속성에 동일 하 게 <xref:System.Windows.Controls.Calendar>합니다.</span><span class="sxs-lookup"><span data-stu-id="188ec-107">Many of a <xref:System.Windows.Controls.DatePicker> control's properties are for managing its built-in <xref:System.Windows.Controls.Calendar>, and function identically to the equivalent property in <xref:System.Windows.Controls.Calendar>.</span></span> <span data-ttu-id="188ec-108">특히는 <xref:System.Windows.Controls.DatePicker.IsTodayHighlighted%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.FirstDayOfWeek%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.BlackoutDates%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.DisplayDateStart%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.DisplayDateEnd%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.DisplayDate%2A?displayProperty=nameWithType>, 및 <xref:System.Windows.Controls.DatePicker.SelectedDate%2A?displayProperty=nameWithType> 속성 동일 하 게 작동 자신의 <xref:System.Windows.Controls.Calendar> 대응 합니다.</span><span class="sxs-lookup"><span data-stu-id="188ec-108">In particular, the <xref:System.Windows.Controls.DatePicker.IsTodayHighlighted%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.FirstDayOfWeek%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.BlackoutDates%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.DisplayDateStart%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.DisplayDateEnd%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.DisplayDate%2A?displayProperty=nameWithType>, and <xref:System.Windows.Controls.DatePicker.SelectedDate%2A?displayProperty=nameWithType> properties function identically to their <xref:System.Windows.Controls.Calendar> counterparts.</span></span> <span data-ttu-id="188ec-109">자세한 내용은 <xref:System.Windows.Controls.Calendar>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="188ec-109">For more information, see <xref:System.Windows.Controls.Calendar>.</span></span>  
  
 <span data-ttu-id="188ec-110">사용자가 날짜를 설정 하는 텍스트 필드에 직접 입력할 수는 <xref:System.Windows.Controls.DatePicker.Text%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="188ec-110">Users can type a date directly into a text field, which sets the <xref:System.Windows.Controls.DatePicker.Text%2A> property.</span></span> <span data-ttu-id="188ec-111">경우는 <xref:System.Windows.Controls.DatePicker> 유효한 날짜를 입력 한 문자열을 변환할 수 없는 <xref:System.Windows.Controls.DatePicker.DateValidationError> 이벤트가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="188ec-111">If the <xref:System.Windows.Controls.DatePicker> cannot convert the entered string to a valid date, the <xref:System.Windows.Controls.DatePicker.DateValidationError> event will be raised.</span></span> <span data-ttu-id="188ec-112">기본적으로이 대 한 이벤트 처리기 하지만 예외를 발생 시키는 <xref:System.Windows.Controls.DatePicker.DateValidationError> 설정할 수는 <xref:System.Windows.Controls.DatePickerDateValidationErrorEventArgs.ThrowException%2A> 속성을 `false` 및 예외가 발생 하지 않게 합니다.</span><span class="sxs-lookup"><span data-stu-id="188ec-112">By default, this causes an exception, but an event handler for <xref:System.Windows.Controls.DatePicker.DateValidationError> can set the <xref:System.Windows.Controls.DatePickerDateValidationErrorEventArgs.ThrowException%2A> property to `false` and prevent an exception from being raised.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="188ec-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="188ec-113">See Also</span></span>  
 [<span data-ttu-id="188ec-114">컨트롤</span><span class="sxs-lookup"><span data-stu-id="188ec-114">Controls</span></span>](../../../../docs/framework/wpf/controls/index.md)  
 [<span data-ttu-id="188ec-115">스타일 지정 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="188ec-115">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)
