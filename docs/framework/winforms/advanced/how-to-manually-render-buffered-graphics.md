---
title: "방법: 버퍼링된 그래픽 수동 렌더링"
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
- flicker [Windows Forms], reducing by manually rendering graphics
- graphics [Windows Forms], rendering
ms.assetid: 5192295e-bd8e-45f7-8bd6-5c4f6bd21e61
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d3a5d06da3a398782b0285fb55807df5832cf771
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-manually-render-buffered-graphics"></a>방법: 버퍼링된 그래픽 수동 렌더링
버퍼링된 고유한 그래픽을 관리하는 경우 그래픽 버퍼를 만들고 렌더링할 수 있어야 합니다. <xref:System.Drawing.BufferedGraphicsContext.Allocate%2A> 메서드를 호출하여 화면의 그리기 화면과 연결된 <xref:System.Drawing.BufferedGraphics> 클래스의 인스턴스를 만들 수 있습니다. 이 메서드는 폼 또는 컨트롤과 같은 특정 렌더링 화면과 연결된 <xref:System.Drawing.BufferedGraphics> 인스턴스를 만듭니다. <xref:System.Drawing.BufferedGraphics> 인스턴스를 만든 후 <xref:System.Drawing.BufferedGraphics.Graphics%2A> 속성을 통해 나타내는 버퍼에 통해 나타내는 버퍼에 그래픽을 그릴 수 있습니다. 모든 그래픽 작업을 수행한 후 <xref:System.Drawing.BufferedGraphics.Render%2A> 메서드를 호출하여 버퍼 내용을 화면에 복사할 수 있습니다.  
  
> [!NOTE]
>  고유한 렌더링을 수행하는 경우 약간의 증가이긴 하지만 메모리 사용이 증가합니다.  
  
### <a name="to-manually-display-buffered-graphics"></a>버퍼링된 그래픽을 수동으로 표시하려면  
  
1.  <xref:System.Drawing.BufferedGraphicsContext> 클래스의 인스턴스에 대한 참조를 가져옵니다. 자세한 내용은 참조 [하는 방법: 버퍼링 된 그래픽 수동 관리](../../../../docs/framework/winforms/advanced/how-to-manually-manage-buffered-graphics.md)합니다.  
  
2.  다음 코드 예제와 같이 <xref:System.Drawing.BufferedGraphicsContext.Allocate%2A> 메서드를 호출하여 <xref:System.Drawing.BufferedGraphics> 클래스의 인스턴스를 만듭니다.  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#21)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#21)]  
  
3.  <xref:System.Drawing.BufferedGraphics.Graphics%2A> 속성을 설정하여 그래픽 버퍼에 그래픽을 그립니다. 예:  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#22)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#22)]  
  
4.  그래픽 버퍼에 그리기 작업을 모두 완료했으면, 다음 코드 예제와 같이 <xref:System.Drawing.BufferedGraphics.Render%2A> 메서드를 호출하여 해당 버퍼와 연결된 그리기 화면이나 지정된 그리기 화면에 버퍼를 렌더링합니다.  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#23)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#23)]  
  
5.  그래픽 렌더링을 마친 후 <xref:System.Drawing.BufferedGraphics> 인스턴스에 대해 `Dispose` 메서드를 호출하여 시스템 리소스를 해제합니다.  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#24](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#24)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#24](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#24)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Drawing.BufferedGraphicsContext>  
 <xref:System.Drawing.BufferedGraphics>  
 [이중 버퍼링 그래픽](../../../../docs/framework/winforms/advanced/double-buffered-graphics.md)  
 [방법: 버퍼링된 그래픽 수동 관리](../../../../docs/framework/winforms/advanced/how-to-manually-manage-buffered-graphics.md)
