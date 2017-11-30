---
title: "방법: 도형 간 탭 이동 사용(Visual Studio)"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Line control [Visual Basic], implementing tabbing
- Shape control [Visual Basic], implementing tabbing
ms.assetid: 09731b34-3900-4fcb-a9df-ce5280328433
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a39957ffaa67d6abeb6d394ae9826d42ad2230de
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-enable-tabbing-between-shapes-visual-studio"></a>방법: 도형 간 탭 이동 사용(Visual Studio)
Line 및 shape 컨트롤 `TabStop` 또는 `TabIndex` 있지만 속성을 계속 사용할 수 있습니다 그중에서 탭 이동 합니다. 다음 예제에서는 도형; 간에 탭은 CTRL과 탭 키를 누르면 단추 사이만 TAB 키를 누를 tab 합니다.  
  
> [!NOTE]
>  일부 Visual Studio 사용자 인터페이스 요소의 경우 다음 지침에 설명된 것과 다른 이름 또는 위치가 시스템에 표시될 수 있습니다. 이러한 요소는 사용하는 Visual Studio 버전 및 설정에 따라 결정됩니다. 자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.  
  
## <a name="to-enable-tabbing-among-shapes"></a>도형 간 탭 이동 사용 하도록 설정 하려면  
  
1.  세 개의 끌어 <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> 컨트롤과 두 개의 <xref:System.Windows.Forms.Button> 에서 제어는 **도구 상자** 폼에 있습니다.  
  
2.  에 **코드 편집기**, 추가 `Imports` 또는 `using` 모듈 맨 위에 있는 문:  
  
```vb  
Imports Microsoft.VisualBasic.PowerPacks  
```  
  
```csharp  
using Microsoft.VisualBasic.PowerPacks;  
```  

3.  이벤트 프로시저에 다음 코드를 추가 합니다.  
  
[!code-csharp[VbPowerPacksTabbing#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-enable-tabbing-between-shapes-visual-studio_1.cs)]
[!code-vb[VbPowerPacksTabbing#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-enable-tabbing-between-shapes-visual-studio_1.vb)]  
  
4.  다음 코드에 추가 `Button1_PreviewKeyDown` 이벤트 프로시저:  
  
[!code-csharp[VbPowerPacksTabbing#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-enable-tabbing-between-shapes-visual-studio_2.cs)]
[!code-vb[VbPowerPacksTabbing#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-enable-tabbing-between-shapes-visual-studio_2.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [방법: OvalShape 및 RectangleShape 컨트롤을 사용하여 도형 그리기](../../../visual-basic/developing-apps/windows-forms/how-to-draw-shapes-with-the-ovalshape-and-rectangleshape-controls.md)  
 [방법: LineShape 컨트롤로 선 그리기](../../../visual-basic/developing-apps/windows-forms/how-to-draw-lines-with-the-lineshape-control-visual-studio.md)  
 [Line 및 Shape 컨트롤 소개](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-line-and-shape-controls-visual-studio.md)
