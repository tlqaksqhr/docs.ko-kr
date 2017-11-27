---
title: "속성 변경 이벤트"
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
helpviewer_keywords:
- custom controls [Windows Forms], property changes (using code)
- properties [Windows Forms], changes
ms.assetid: 268039ec-5aaa-4d76-b902-acccb036c850
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7685891e99f1dcb2ca9e515c7dc6d7730ff0b2e5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="property-changed-events"></a><span data-ttu-id="1cfa7-102">속성 변경 이벤트</span><span class="sxs-lookup"><span data-stu-id="1cfa7-102">Property-Changed Events</span></span>
<span data-ttu-id="1cfa7-103">원하는 경우 라는 속성이 알림을 보내도록 컨트롤 *PropertyName* 명명 된 이벤트를 정의 하는 변경 내용을 *PropertyName* `Changed` 라는 이름의 메서드 `On` *PropertyName* `Changed` 이벤트를 발생 시키는 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cfa7-103">If you want your control to send notifications when a property named *PropertyName* changes, define an event named *PropertyName*`Changed` and a method named `On`*PropertyName*`Changed` that raises the event.</span></span> <span data-ttu-id="1cfa7-104">단어를 추가할 Windows Forms의 명명 규칙은 *Changed* 속성의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="1cfa7-104">The naming convention in Windows Forms is to append the word *Changed* to the name of the property.</span></span> <span data-ttu-id="1cfa7-105">속성 변경 이벤트에 대 한 관련된 이벤트 대리자 형식이 <xref:System.EventHandler>, 이벤트 데이터 형식이 고 <xref:System.EventArgs>합니다.</span><span class="sxs-lookup"><span data-stu-id="1cfa7-105">The associated event delegate type for property-changed events is <xref:System.EventHandler>, and the event data type is <xref:System.EventArgs>.</span></span> <span data-ttu-id="1cfa7-106">기본 클래스 <xref:System.Windows.Forms.Control> 와 같은 대부분의 속성 변경 이벤트를 정의 <xref:System.Windows.Forms.Control.BackColorChanged>, <xref:System.Windows.Forms.Control.BackgroundImageChanged>, <xref:System.Windows.Forms.Control.FontChanged>, <xref:System.Windows.Forms.Control.LocationChanged>, 등입니다.</span><span class="sxs-lookup"><span data-stu-id="1cfa7-106">The base class <xref:System.Windows.Forms.Control> defines many property-changed events, such as <xref:System.Windows.Forms.Control.BackColorChanged>, <xref:System.Windows.Forms.Control.BackgroundImageChanged>, <xref:System.Windows.Forms.Control.FontChanged>, <xref:System.Windows.Forms.Control.LocationChanged>, and others.</span></span> <span data-ttu-id="1cfa7-107">이벤트에 대 한 배경 정보를 참조 하십시오. [이벤트](../../../../docs/standard/events/index.md) 및 [Windows Forms 컨트롤의 이벤트](../../../../docs/framework/winforms/controls/events-in-windows-forms-controls.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1cfa7-107">For background information about events, see [Events](../../../../docs/standard/events/index.md) and [Events in Windows Forms Controls](../../../../docs/framework/winforms/controls/events-in-windows-forms-controls.md).</span></span>  
  
 <span data-ttu-id="1cfa7-108">속성 변경 이벤트는 변경에 응답 하는 이벤트 처리기를 연결 하는 컨트롤의 소비자 수 있기 때문에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cfa7-108">Property-changed events are useful because they allow consumers of a control to attach event handlers that respond to the change.</span></span> <span data-ttu-id="1cfa7-109">컨트롤을 발생 시킨 속성 변경 이벤트에 응답 하는 경우 해당 재정의 `On` *PropertyName* `Changed` 메서드가 아닌 이벤트에 대리자를 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cfa7-109">If your control needs to respond to a property-changed event that it raises, override the corresponding `On`*PropertyName*`Changed` method instead of attaching a delegate to the event.</span></span> <span data-ttu-id="1cfa7-110">일반적으로 컨트롤 그리기 화면의의 일부 또는 전부를 다시 그리기 하거나 다른 속성을 업데이트 하 여 속성 변경 이벤트에 응답 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cfa7-110">A control typically responds to a property-changed event by updating other properties or by redrawing some or all of its drawing surface.</span></span>  
  
 <span data-ttu-id="1cfa7-111">다음 예제와 방법을 `FlashTrackBar` 일부에서 상속 된 속성 변경 이벤트에 응답 하는 사용자 지정 컨트롤 <xref:System.Windows.Forms.Control>합니다.</span><span class="sxs-lookup"><span data-stu-id="1cfa7-111">The following example shows how the `FlashTrackBar` custom control responds to some of the property-changed events that it inherits from <xref:System.Windows.Forms.Control>.</span></span> <span data-ttu-id="1cfa7-112">전체 샘플을 참조 하십시오. [하는 방법: Windows Forms 컨트롤을 표시 진행률 만들기](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1cfa7-112">For the complete sample, see [How to: Create a Windows Forms Control That Shows Progress](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md).</span></span>  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#2)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="1cfa7-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1cfa7-113">See Also</span></span>  
 [<span data-ttu-id="1cfa7-114">이벤트</span><span class="sxs-lookup"><span data-stu-id="1cfa7-114">Events</span></span>](../../../../docs/standard/events/index.md)  
 [<span data-ttu-id="1cfa7-115">Windows Forms 컨트롤의 이벤트</span><span class="sxs-lookup"><span data-stu-id="1cfa7-115">Events in Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/events-in-windows-forms-controls.md)  
 [<span data-ttu-id="1cfa7-116">Windows Forms 컨트롤의 속성</span><span class="sxs-lookup"><span data-stu-id="1cfa7-116">Properties in Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/properties-in-windows-forms-controls.md)
