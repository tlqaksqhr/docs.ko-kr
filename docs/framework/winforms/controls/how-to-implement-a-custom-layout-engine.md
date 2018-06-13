---
title: '방법: 사용자 지정 레이아웃 엔진 구현'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- layout engines [Windows Forms], custom
- TableLayoutPanel control [Windows Forms], layout engine
- layout engines [Windows Forms], implementing
- FlowLayoutPanel control [Windows Forms], layout engine
ms.assetid: f91aa91c-29f4-4089-95ca-5d48b774b00e
ms.openlocfilehash: 0444f0d03a36adf833c04167c6d7a3c302ab15dd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33531299"
---
# <a name="how-to-implement-a-custom-layout-engine"></a>방법: 사용자 지정 레이아웃 엔진 구현
다음 코드 예제에서는 간단한 선형 레이아웃을 수행 하는 사용자 지정 레이아웃 엔진을 만드는 방법을 보여 줍니다. 명명 된 패널 컨트롤을 구현 `DemoFlowPanel`, 재정의 하는 <xref:System.Windows.Forms.Control.LayoutEngine%2A> 속성의 인스턴스를 제공 하는 `DemoFlowLayout` 클래스입니다.  
  
## <a name="example"></a>예제  
 [!code-cpp[System.Windows.Forms.Layout.LayoutEngine#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.Layout.LayoutEngine/cpp/DemoFlowLayout.cpp#1)]
 [!code-csharp[System.Windows.Forms.Layout.LayoutEngine#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Layout.LayoutEngine/CS/DemoFlowLayout.cs#1)]
 [!code-vb[System.Windows.Forms.Layout.LayoutEngine#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Layout.LayoutEngine/VB/DemoFlowLayout.vb#1)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.Layout.LayoutEngine>  
 <xref:System.Windows.Forms.Control.LayoutEngine%2A?displayProperty=nameWithType>
