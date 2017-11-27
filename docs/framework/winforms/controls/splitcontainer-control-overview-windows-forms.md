---
title: "SplitContainer 컨트롤 개요(Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: SplitContainer
helpviewer_keywords: SplitContainer control [Windows Forms], about SplitContainer control
ms.assetid: 6de5a5f7-97a5-402d-be6d-7e2785483db5
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 10f18c46c85ed840b6625d9ed754d1d036a80975
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="splitcontainer-control-overview-windows-forms"></a>SplitContainer 컨트롤 개요(Windows Forms)
Windows Forms <xref:System.Windows.Forms.SplitContainer> 컨트롤은 복합으로 간주될 수 있습니다. 이동 가능한 막대로 구분된 두 개의 패널입니다. 마우스 포인터가 막대 위에 있으면 포인터 모양이 변경되어 막대를 이동할 수 있음을 표시합니다.  
  
> [!IMPORTANT]
>  에 **도구 상자**, <xref:System.Windows.Forms.SplitContainer> 대체 제어는 <xref:System.Windows.Forms.Splitter> 컨트롤의 이전 버전에 있던 [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)]합니다. <xref:System.Windows.Forms.SplitContainer> 컨트롤이 <xref:System.Windows.Forms.Splitter> 컨트롤보다 훨씬 선호됩니다. <xref:System.Windows.Forms.Splitter> 클래스에 여전히 포함 되어는 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 기존 응용 프로그램과 호환성에 대 한 하지만 좋습니다 사용 하 여 <xref:System.Windows.Forms.SplitContainer> 새 프로젝트에 대 한 제어 합니다.  
  
 와 <xref:System.Windows.Forms.SplitContainer> 컨트롤, 복잡 한 사용자 인터페이스를 만들 수 있습니다; 다른 패널에 표시 되는 개체가 한 패널에서 선택한 항목을 결정 하는 경우가 많습니다. 이 정렬은 정보를 표시하고 찾는 데 매우 효율적입니다. 두 개의 패널 수 있는 영역에 정보를 집계 하 고 막대 또는 "분할자"를 통해 사용자가 쉽게 패널 크기 조정 하 합니다.  
  
 둘 이상의 <xref:System.Windows.Forms.SplitContainer> 컨트롤 중첩 될 수 있습니다, 두 번째 <xref:System.Windows.Forms.SplitContainer> 제어 가로로 배치 위쪽 및 아래쪽 패널을 만들려고 합니다.  
  
 알아야 하는 <xref:System.Windows.Forms.SplitContainer> 컨트롤은 키보드 액세스 가능한 기본적으로 이며 사용자가 경우 분할자 이동 하려면 화살표 키를 눌러 수는 <xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> 속성이로 설정 된 `false`합니다.  
  
 <xref:System.Windows.Forms.SplitContainer.Orientation%2A> 의 속성은 <xref:System.Windows.Forms.SplitContainer> 컨트롤 컨트롤 자체 아닌 분할자의 방향을 결정 합니다. 이 속성이로 설정 된 경우에 따라서 <xref:System.Windows.Forms.Orientation.Vertical>, 분할자 위쪽에서 아래쪽, 왼쪽 및 오른쪽 패널 만들기를 실행 합니다.  
  
 또한 하는 값은 <xref:System.Windows.Forms.SplitContainer.SplitterRectangle%2A> 속성의 값에 따라 달라 집니다는 <xref:System.Windows.Forms.SplitContainer.Orientation%2A> 속성. 자세한 내용은 참조 <xref:System.Windows.Forms.SplitContainer.SplitterRectangle%2A> 속성입니다.  
  
 크기와의 이동을 제한할 수도 있습니다는 <xref:System.Windows.Forms.SplitContainer> 제어 합니다. <xref:System.Windows.Forms.SplitContainer.FixedPanel%2A> 속성 결정 한 후 같은 크기로 유지할 패널을는 <xref:System.Windows.Forms.SplitContainer> 컨트롤의 크기 조정 및 <xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> 속성은 키보드 또는 마우스 이동 가능한 분할자 인지 여부를 확인 합니다.  
  
> [!NOTE]
>  경우에는 <xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> 속성이 `true`, 분할자 이동할 수 있습니다 예를 들어, 프로그래밍 방식으로 사용 하 여는 <xref:System.Windows.Forms.SplitContainer.SplitterDistance%2A> 속성입니다.  
  
 마지막으로, 각 패널에는 <xref:System.Windows.Forms.SplitContainer> 컨트롤에는 개별 크기를 결정 하는 속성이 있습니다.  
  
## <a name="commonly-used-properties-methods-and-events"></a>일반적으로 사용되는 속성, 메서드 및 이벤트  
  
|이름|설명|  
|----------|-----------------|  
|<xref:System.Windows.Forms.SplitContainer.FixedPanel%2A> 속성|패널 동일 하 게 결정 한 후 크기가 <xref:System.Windows.Forms.SplitContainer> 컨트롤의 크기를 조정 합니다.|  
|<xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> 속성|분할자 키보드 또는 마우스를 이동할 수 있는지 확인 합니다.|  
|<xref:System.Windows.Forms.SplitContainer.Orientation%2A> 속성|분할 자가 가로 또는 세로로 정렬 된 경우를 결정 합니다.|  
|<xref:System.Windows.Forms.SplitContainer.SplitterDistance%2A> 속성|이동할 수 있는 분할 막대를 왼쪽 또는 위쪽 가장자리에서 픽셀 거리를 결정합니다.|  
|<xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> 속성|최소 거리 (픽셀)를 사용자가 분할자를 이동할 수 있는지를 결정 합니다.|  
|<xref:System.Windows.Forms.SplitContainer.SplitterWidth%2A> 속성|분할자의 픽셀 단위로 두께 결정합니다.|  
|<xref:System.Windows.Forms.SplitContainer.SplitterMoving>이벤트|분할자 이동 하는 경우 발생 합니다.|  
|<xref:System.Windows.Forms.SplitContainer.SplitterMoved>이벤트|분할 자가 이동한 때 발생 합니다.|  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.SplitContainer>  
 [SplitContainer 컨트롤](../../../../docs/framework/winforms/controls/splitcontainer-control-windows-forms.md)  
 [SplitContainer 컨트롤 샘플](http://msdn.microsoft.com/en-us/9015fad0-7108-4d85-a83a-a72d038c4f65)
