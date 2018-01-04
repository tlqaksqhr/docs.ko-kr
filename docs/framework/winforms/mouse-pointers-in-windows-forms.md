---
title: "Windows Forms의 마우스 포인터"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pointers [Windows Forms], setting
- mouse pointers
- mouse cursors
- mouse pointers [Windows Forms], setting
- cursors [Windows Forms], setting
- mouse [Windows Forms], cursors
ms.assetid: c3400d85-de5b-42e8-abc3-d6088d69ee53
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: aaca18bff265fafbb5bad26adfe2a8c490d85132
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="mouse-pointers-in-windows-forms"></a>Windows Forms의 마우스 포인터
마우스 *포인터*, 마우스를 사용 하 여 사용자 입력에 대 한 화면에 포커스가 위치를 지정 하는 비트맵은 커서 참조 되는 경우에 따라 있는 합니다. 이 항목 Windows Forms에서 마우스 포인터의 개요를 제공 하 고 수정 하 고 마우스 포인터를 제어 하는 방법 중 일부에 대해 설명 합니다.  
  
## <a name="accessing-the-mouse-pointer"></a>마우스 포인터에 액세스  
 마우스 포인터가 나타내는 <xref:System.Windows.Forms.Cursor> 클래스 및 각 <xref:System.Windows.Forms.Control> 에 <xref:System.Windows.Forms.Control.Cursor%2A?displayProperty=nameWithType> 해당 컨트롤에 대 한 포인터를 지정 하는 속성입니다. <xref:System.Windows.Forms.Cursor> 클래스와 같은 포인터를 설명 하는 속성이 포함 된 <xref:System.Windows.Forms.Cursor.Position%2A> 및 <xref:System.Windows.Forms.Cursor.HotSpot%2A> 속성과 같은 포인터의 모양을 수정할 수 있는 메서드는 <xref:System.Windows.Forms.Cursor.Show%2A>, <xref:System.Windows.Forms.Cursor.Hide%2A>, 및 <xref:System.Windows.Forms.Cursor.DrawStretched%2A> 메서드를 합니다.  
  
## <a name="controlling-the-mouse-pointer"></a>마우스 포인터를 제어합니다.  
 경우에 따라 다음 마우스 포인터 사용할 수 있거나 마우스 위치를 변경할 영역을 제한 하는 것이 좋습니다. 가져오거나 사용 하 여 마우스의 현재 위치를 설정할 수는 <xref:System.Windows.Forms.Cursor.Position%2A> 의 속성은 <xref:System.Windows.Forms.Cursor>합니다. 마우스 포인터를 사용할 수 있습니다 영역을 제한할 수는 또한 설정 수는 <xref:System.Windows.Forms.Cursor.Clip%2A> 속성입니다. 기본적으로의 클립 영역에는 전체 화면입니다.  
  
## <a name="changing-the-mouse-pointer"></a>마우스 포인터 변경  
 사용자에 게 피드백을 제공 하는 중요 한 차이점은 마우스 포인터를 변경 합니다. 예를 들어의 처리기에서 마우스 포인터를 수정할 수 있습니다는 <xref:System.Windows.Forms.Control.MouseEnter> 및 <xref:System.Windows.Forms.Control.MouseLeave> 계산이 수행 되는 사용자에 게 알림를 제한 하 고 컨트롤의 사용자 상호 작용 하는 이벤트입니다. 경우에 따라 끌어서 놓기 작업에서 응용 프로그램은 포함 하는 경우와 같은 시스템 이벤트 때문에 마우스 포인터 변경 됩니다.  
  
 설정 된 경우 마우스 포인터를 변경 하는 기본적인 방법은 <xref:System.Windows.Forms.Control.Cursor%2A?displayProperty=nameWithType> 또는 <xref:System.Windows.Forms.Control.DefaultCursor%2A> 새 컨트롤의 속성 <xref:System.Windows.Forms.Cursor>합니다. 마우스 포인터 변경의 예의 코드 예제를 참조 하십시오.는 <xref:System.Windows.Forms.Cursor> 클래스입니다. 또한는 <xref:System.Windows.Forms.Cursors> 클래스 집합을 노출 <xref:System.Windows.Forms.Cursor> 다양 한 유형의 손 모양 유사한 포인터와 같은 포인터에 대 한 개체입니다. 사용 하 여는 경우 언제 든 지 마우스 포인터가 컨트롤에는 모래 시계과 비슷한, 대기 포인터의 표시는 <xref:System.Windows.Forms.Control.UseWaitCursor%2A> 속성의는 <xref:System.Windows.Forms.Control> 클래스.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.Cursor>  
 [Windows Forms 응용 프로그램의 마우스 입력](../../../docs/framework/winforms/mouse-input-in-a-windows-forms-application.md)  
 [Windows Forms에서의 끌어서 놓기 기능](../../../docs/framework/winforms/drag-and-drop-functionality-in-windows-forms.md)
