---
title: "How to: Draw Lines with the LineShape Control (Visual Studio) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "LineShape control"
  - "lines, drawing"
ms.assetid: 83e71b4e-aa76-4f9b-b547-8704309fd1e5
caps.latest.revision: 14
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 14
---
# How to: Draw Lines with the LineShape Control (Visual Studio)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

<xref:Microsoft.VisualBasic.PowerPacks.LineShape> 컨트롤을 사용하여 디자인 타임과 런타임 모두에서 폼 또는 컨테이너에 가로선, 세로선 또는 대각선을 그립니다.  
  
 **참고** 컴퓨터에서 일부 Visual Studio 사용자 인터페이스 요소에 대해 다음 지침에서 설명한 것과 다른 이름 또는 위치를 표시할 수 있습니다.  설치한 Visual Studio 버전과 사용하는 설정에 따라 이러한 요소가 결정됩니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
### 디자인 타임에 선을 그리려면  
  
1.  **도구 상자**의 **Visual Basic PowerPacks** 탭에서 폼 또는 컨테이너 컨트롤로 <xref:Microsoft.VisualBasic.PowerPacks.LineShape> 컨트롤을 끌어 옵니다.  
  
2.  크기 조정 핸들을 끌어 이동하여 선의 크기를 조정하고 선을 배치합니다.  
  
     또한 **속성** 창에서 `X1`, `X2`, `Y1` 및 `Y2` 속성을 변경하여 선의 크기를 조정하고 선을 배치할 수 있습니다.  
  
3.  **속성** 창에서 필요에 따라 `BorderStyle` 또는 `BorderColor`와 같은 추가 속성을 설정하여 선 모양을 변경할 수 있습니다.  
  
### 런타임에 선을 그리려면  
  
1.  **프로젝트** 메뉴에서 **참조 추가**를 클릭합니다.  
  
2.  **참조 추가** 대화 상자에서 **Microsoft.VisualBasic.PowerPacks.VS**를 선택한 다음 **확인**을 클릭합니다.  
  
3.  **코드 편집기**에서 모듈의 맨 위에 `Imports` 또는 `using` 문을 추가합니다.  
  
    ```vb#  
    Imports Microsoft.VisualBasic.PowerPacks  
    ```  
  
    ```c#  
    using Microsoft.VisualBasic.PowerPacks;  
    ```  
  
4.  `Event` 프로시저에 다음 코드를 추가합니다.  
  
     [!code-cs[VbPowerPacksLine#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-draw-lines-with-the-lineshape-control-visual-studio_1.cs)]
     [!code-vb[VbPowerPacksLine#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-draw-lines-with-the-lineshape-control-visual-studio_1.vb)]  
  
## 참고 항목  
 <xref:Microsoft.VisualBasic.PowerPacks.LineShape>   
 [Introduction to the Line and Shape Controls](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-line-and-shape-controls-visual-studio.md)   
 [How to: Draw Shapes with the OvalShape and RectangleShape Controls](../../../visual-basic/developing-apps/windows-forms/how-to-draw-shapes-with-the-ovalshape-and-rectangleshape-controls.md)