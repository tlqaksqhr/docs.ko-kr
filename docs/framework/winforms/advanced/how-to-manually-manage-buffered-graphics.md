---
title: "방법: 버퍼링된 그래픽 수동 관리"
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
- flicker [Windows Forms], reducing by manually managing graphics
- graphics [Windows Forms], managing buffered
ms.assetid: 4c2a90ee-bbbe-4ff6-9170-1b06c195c918
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4f545cf4689a2c8058e77f4b4721788ffb0e7247
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-manually-manage-buffered-graphics"></a>방법: 버퍼링된 그래픽 수동 관리
더 많은 고급 이중 버퍼링 시나리오를 사용할 수 있습니다는 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 이중 버퍼링 논리를 구현 하는 클래스입니다. 할당 및 개별 그래픽 버퍼를 관리 하는 일을 담당 하는 클래스는 <xref:System.Drawing.BufferedGraphicsContext> 클래스입니다. 모든 응용 프로그램에는 자체 기본 <xref:System.Drawing.BufferedGraphicsContext> 기본 이중 버퍼링 해당 응용 프로그램의 모든 관리입니다. 호출 하 여이 인스턴스에 대 한 참조를 검색할 수 있습니다는 <xref:System.Drawing.BufferedGraphicsManager.Current%2A>합니다.  
  
### <a name="to-obtain-a-reference-to-the-default-bufferedgraphicscontext"></a>BufferedGraphicsContext 기본에 대 한 참조를 가져오려면  
  
-   설정의 <xref:System.Drawing.BufferedGraphicsManager.Current%2A> 속성을 다음 코드 예제와 같이 합니다.  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#11)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#11)]  
  
    > [!NOTE]
    >  호출할 필요가 없습니다는 `Dispose` 에서 메서드는 <xref:System.Drawing.BufferedGraphicsContext> 에서 수신 하는 참조는 <xref:System.Drawing.BufferedGraphicsManager> 클래스. <xref:System.Drawing.BufferedGraphicsManager> 메모리 할당 및 기본에 대 한 배포의 모든 처리 <xref:System.Drawing.BufferedGraphicsContext> 인스턴스.  
  
     애니메이션 같은 그래픽 위주의 응용 프로그램에 대 한 경우에 따라 성능을 개선할 수 있습니다 전용을 사용 하 여 <xref:System.Drawing.BufferedGraphicsContext> 대신는 <xref:System.Drawing.BufferedGraphicsContext> 에서 제공 되는 <xref:System.Drawing.BufferedGraphicsManager>합니다. 따라서 만들고 모든는 다른 버퍼링 된 그래픽 관리 응용 프로그램과 연결 된 경우에 응용 프로그램에서 사용 되는 메모리 뛰어날 것의 성능 오버 헤드를 발생 시 키 지 않고 그래픽 버퍼를 개별적으로 관리할 수 있습니다.  
  
### <a name="to-create-a-dedicated-bufferedgraphicscontext"></a>전용된 BufferedGraphicsContext를 만들려면  
  
-   선언 하 고의 새 인스턴스를 만듭니다는 <xref:System.Drawing.BufferedGraphicsContext> 다음 코드 예제와 같이 클래스입니다.  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#12](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#12)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#12](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#12)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Drawing.BufferedGraphicsContext>  
 [이중 버퍼링 그래픽](../../../../docs/framework/winforms/advanced/double-buffered-graphics.md)  
 [방법: 버퍼링된 그래픽 수동 렌더링](../../../../docs/framework/winforms/advanced/how-to-manually-render-buffered-graphics.md)
