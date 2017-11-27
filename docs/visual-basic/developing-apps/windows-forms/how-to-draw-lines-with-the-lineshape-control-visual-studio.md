---
title: "방법: LineShape 컨트롤로 선 그리기(Visual Studio)"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- LineShape control [Visual Basic]
- lines, drawing
ms.assetid: 83e71b4e-aa76-4f9b-b547-8704309fd1e5
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f170250dde2f6db31ed68908936c0e9714a7e846
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-draw-lines-with-the-lineshape-control-visual-studio"></a>방법: LineShape 컨트롤로 선 그리기(Visual Studio)
사용할 수 있습니다는 <xref:Microsoft.VisualBasic.PowerPacks.LineShape> 컨트롤을 디자인 타임 및 런타임에 폼 이나 컨테이너에서 가로, 세로 또는 대각선를 그립니다.  
  
 **참고** 컴퓨터 표시 될 수 있습니다 다른 이름 또는 위치가 시스템에 일부 Visual Studio 사용자 인터페이스 요소의 경우 다음 지침에에서 있습니다. 이러한 요소는 사용하는 Visual Studio 버전 및 설정에 따라 결정됩니다. 자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.  
  
### <a name="to-draw-a-line-at-design-time"></a>디자인 타임에 선을 그리려면  
  
1.  끌어는 <xref:Microsoft.VisualBasic.PowerPacks.LineShape> 에서 제어는 **Visual Basic PowerPacks** 탭에 **도구 상자** 폼 이나 컨테이너 컨트롤로 끌어 옵니다.  
  
2.  크기 조정 끌어서 크기 및 줄 위치에 대 한 핸들을 이동 합니다.  
  
     크기 조정 하 고 변경 하 여 선을 배치할 수도 있습니다는 `X1`, `X2`, `Y1`, 및 `Y2` 속성에는 **속성** 창.  
  
3.  에 **속성** 창, 필요에 따라 추가 속성을 설정 같은 `BorderStyle` 또는 `BorderColor` 줄의 모양을 변경 하 합니다.  
  
### <a name="to-draw-a-line-at-run-time"></a>런타임 시 선을 그리려면  
  
1.  **프로젝트** 메뉴에서 **참조 추가**를 클릭합니다.  
  
2.  에 **참조 추가** 대화 상자에서 **Microsoft.VisualBasic.PowerPacks.VS**, 클릭 하 고 **확인**합니다.  
  
3.  에 **코드 편집기**, 추가 `Imports` 또는 `using` 모듈 맨 위에 있는 문:  
  
```vb  
Imports Microsoft.VisualBasic.PowerPacks  
```  
  
```csharp  
using Microsoft.VisualBasic.PowerPacks;  
```  
  
4.  `Event` 프로시저에 다음 코드를 추가합니다.  
  
     [!code-csharp[VbPowerPacksLine#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-draw-lines-with-the-lineshape-control-visual-studio_1.cs)]
     [!code-vb[VbPowerPacksLine#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-draw-lines-with-the-lineshape-control-visual-studio_1.vb)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualBasic.PowerPacks.LineShape>  
 [Line 및 Shape 컨트롤 소개](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-line-and-shape-controls-visual-studio.md)  
 [방법: OvalShape 및 RectangleShape 컨트롤을 사용하여 도형 그리기](../../../visual-basic/developing-apps/windows-forms/how-to-draw-shapes-with-the-ovalshape-and-rectangleshape-controls.md)
