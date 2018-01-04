---
title: "이중 버퍼링 그래픽"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- double buffering
- graphics [Windows Forms], double-buffered
- flicker [Windows Forms], reducing with double buffering
- examples [Windows Forms], double-buffered graphics
ms.assetid: 4f6fef99-0972-436e-9d73-0167e4033f71
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e7e4445b0a729eb1f826d17340db02f0c56149b7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="double-buffered-graphics"></a>이중 버퍼링 그래픽
깜박임은 그래픽을 프로그래밍할 때 일반적으로 발생하는 문제입니다. 여러 개의 복잡한 그리기 작업이 필요한 그래픽 작업에서 렌더링된 이미지가 깜박이거나 그렇지 않고 의도하지 않은 모양이 나타날 수 있습니다. 이러한 문제를 해결하기 위해 .NET Framework에서 이중 버퍼링에 대한 액세스를 제공합니다.  
  
 이중 버퍼링은 메모리 버퍼를 사용하여 여러 그리기 작업과 관련된 깜박임 문제를 해결합니다. 이중 버퍼링을 사용하면 모든 그리기 작업이 그리기 화면 대신 메모리 버퍼에 먼저 렌더링됩니다. 모든 그리기 작업이 완료되면 메모리 버퍼가 연결된 그리기 화면에 직접 복사됩니다. 하나의 그래픽 작업만 화면에서 수행되기 때문에 복잡한 그리기 작업과 관련된 이미지 깜빡임이 제거됩니다.  
  
## <a name="default-double-buffering"></a>기본 이중 버퍼링  
 응용 프로그램에서 이중 버퍼링을 사용하는 가장 쉬운 방법은 .NET Framework에서 제공하는 양식과 컨트롤에 기본 이중 버퍼링을 사용하는 것입니다. 이중 버퍼링 Windows Forms에 대 한 기본 사용 하도록 설정할 수 있습니다 및을 설정 하 여 작성 된 Windows 컨트롤의 <xref:System.Windows.Forms.Control.DoubleBuffered%2A> 속성을 `true` 또는 사용 하 여는 <xref:System.Windows.Forms.Control.SetStyle%2A> 메서드. 자세한 내용은 [방법: 양식과 컨트롤에 이중 버퍼링을 사용하여 그래픽 깜빡임 줄이기](../../../../docs/framework/winforms/advanced/how-to-reduce-graphics-flicker-with-double-buffering-for-forms-and-controls.md)를 참조하세요.  
  
## <a name="manually-managing-buffered-graphics"></a>버퍼링된 그래픽 수동 관리  
 애니메이션 또는 고급 메모리 관리와 같은 고급 이중 버퍼링 시나리오에서는 .NET Framework 클래스를 사용하여 사용자 고유의 이중 버퍼링 논리를 구현할 수 있습니다. 할당 및 개별 그래픽 버퍼를 관리 하는 일을 담당 하는 클래스는 <xref:System.Drawing.BufferedGraphicsContext> 클래스입니다. 모든 응용 프로그램 도메인에는 자체 기본 <xref:System.Drawing.BufferedGraphicsContext> 기본 이중 버퍼링 해당 응용 프로그램의 모든 관리 인스턴스입니다. 대부분의 경우에서 있을 응용 프로그램 마다 하나의 응용 프로그램 도메인 이므로 일반적으로 하나의 기본 <xref:System.Drawing.BufferedGraphicsContext> 응용 프로그램당 합니다. 기본 <xref:System.Drawing.BufferedGraphicsContext> 의해 관리 되는 인스턴스는 <xref:System.Drawing.BufferedGraphicsManager> 클래스입니다. 기본값에 대 한 참조를 검색할 수 있습니다 <xref:System.Drawing.BufferedGraphicsContext> 호출 하 여 인스턴스는 <xref:System.Drawing.BufferedGraphicsManager.Current%2A>합니다. 전용 만들 수 <xref:System.Drawing.BufferedGraphicsContext> 인스턴스 그래픽 위주의 응용 프로그램의 성능을 향상 시킬 수 있습니다. 만드는 방법에 대 한 내용은 <xref:System.Drawing.BufferedGraphicsContext> 인스턴스를 참조 [하는 방법: 버퍼링 된 그래픽 수동 관리](../../../../docs/framework/winforms/advanced/how-to-manually-manage-buffered-graphics.md)합니다.  
  
## <a name="manually-displaying-buffered-graphics"></a>버퍼링된 그래픽 수동 표시  
 인스턴스를 사용할 수는 <xref:System.Drawing.BufferedGraphicsContext> 를 호출 하 여 그래픽 버퍼를 만들 클래스의 <xref:System.Drawing.BufferedGraphicsContext.Allocate%2A?displayProperty=nameWithType>의 인스턴스를 반환 하는 <xref:System.Drawing.BufferedGraphics> 클래스입니다. A <xref:System.Drawing.BufferedGraphics> 개체 표면 렌더링, 폼 또는 컨트롤과 같은 연관 된 메모리 버퍼를 관리 합니다.  
  
 인스턴스화된 후의 <xref:System.Drawing.BufferedGraphics> 클래스 관리 메모리 그래픽 버퍼를 렌더링 합니다. 통해 메모리 버퍼에 그래픽을 렌더링할 수는 <xref:System.Drawing.BufferedGraphics.Graphics%2A>를 노출 하는 <xref:System.Drawing.Graphics> 직접 메모리 버퍼를 나타내는 개체입니다. 이에 그릴 수 <xref:System.Drawing.Graphics> 하는 것 처럼 개체는 <xref:System.Drawing.Graphics> 그리기 화면을 나타내는 개체입니다. 버퍼에 그려진 모든 그래픽 후 사용할 수 있습니다는 <xref:System.Drawing.BufferedGraphics.Render%2A?displayProperty=nameWithType> 화면의 그리기 화면 버퍼의 내용을 복사 합니다.  
  
 사용 하 여 대 한 자세한 내용은 <xref:System.Drawing.BufferedGraphics> 클래스를 참조 하십시오. [버퍼링 된 그래픽 수동 렌더링](../../../../docs/framework/winforms/advanced/how-to-manually-render-buffered-graphics.md)합니다. 그래픽 렌더링에 대한 자세한 내용은 [Windows Forms의 그래픽 및 그리기](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Drawing.BufferedGraphics>  
 <xref:System.Drawing.BufferedGraphicsContext>  
 <xref:System.Drawing.BufferedGraphicsManager>  
 [방법: 버퍼링된 그래픽 수동 렌더링](../../../../docs/framework/winforms/advanced/how-to-manually-render-buffered-graphics.md)  
 [방법: 양식과 컨트롤에 이중 버퍼링을 사용하여 그래픽 깜빡임 줄이기](../../../../docs/framework/winforms/advanced/how-to-reduce-graphics-flicker-with-double-buffering-for-forms-and-controls.md)  
 [방법: 버퍼링된 그래픽 수동 관리](../../../../docs/framework/winforms/advanced/how-to-manually-manage-buffered-graphics.md)  
 [Windows Forms의 그래픽 및 그리기](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)
