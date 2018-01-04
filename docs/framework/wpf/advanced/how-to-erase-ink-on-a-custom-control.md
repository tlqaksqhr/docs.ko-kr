---
title: "방법: 사용자 지정 컨트롤에서 잉크 지우기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [WPF], erasing ink on
- ink [WPF], erasing on custom control
ms.assetid: d88c50f9-b4d8-4962-a28b-67d6a15a5fe0
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e05163bcbafd360e0929fe784ff1111bd0663ef3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-erase-ink-on-a-custom-control"></a>방법: 사용자 지정 컨트롤에서 잉크 지우기
<xref:System.Windows.Ink.IncrementalStrokeHitTester> 현재 그려진된 스트로크에 다른 획 교차 하는지 여부를 결정 합니다.  앱을 통해 컨트롤을 만드는 사용자가 스트로크 일부를 지울 수 유용, 방식에서 할 수 있는 사용자는 <xref:System.Windows.Controls.InkCanvas> 때는 <xref:System.Windows.Controls.InkCanvas.EditingMode%2A> 로 설정 된 <xref:System.Windows.Controls.InkCanvasEditingMode.EraseByPoint>합니다.  
  
## <a name="example"></a>예  
 다음 예제에서는 일부 스트로크를 지울 수 있는 사용자 지정 컨트롤을 만듭니다.  이 예제는 초기화 될 때 잉크를 포함 하는 컨트롤을 만듭니다.  잉크를 수집 하는 컨트롤을 만들려면 참조 [잉크 입력 컨트롤을 만드는](../../../../docs/framework/wpf/advanced/creating-an-ink-input-control.md)합니다.  
  
 [!code-csharp[HowToEraseInk#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToEraseInk/CSharp/InkEraser.cs#1)]
 [!code-vb[HowToEraseInk#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToEraseInk/VisualBasic/InkEraser.vb#1)]
