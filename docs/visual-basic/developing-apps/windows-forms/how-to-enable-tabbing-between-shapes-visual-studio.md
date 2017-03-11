---
title: "How to: Enable Tabbing Between Shapes (Visual Studio) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Line control, implementing tabbing"
  - "Shape control, implementing tabbing"
ms.assetid: 09731b34-3900-4fcb-a9df-ce5280328433
caps.latest.revision: 14
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 14
---
# How to: Enable Tabbing Between Shapes (Visual Studio)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

선 및 도형 컨트롤에 `TabStop` 또는 `TabIndex` 속성이 없지만 이러한 컨트롤 간 탭 이동을 계속 사용할 수 있습니다.  다음 예제에서는 Ctrl 키와 Tab 키를 모두 누르면 도형 간에 탭이 이동하고 Tab 키를 누르면 단추 간에 탭이 이동합니다.  
  
> [!NOTE]
>  일부 Visual Studio 사용자 인터페이스 요소의 경우 다음 지침에 설명된 것과 다른 이름 또는 위치가 시스템에 표시될 수 있습니다.  설치한 Visual Studio 버전과 사용하는 설정에 따라 이러한 요소가 결정됩니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
### 도형 간 탭 이동을 사용하려면  
  
1.  **도구 상자**에서 폼으로 <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> 컨트롤 세 개와 <xref:System.Windows.Forms.Button> 컨트롤 두 개를 끌어 옵니다.  
  
2.  **코드 편집기**에서 모듈의 맨 위에 `Imports` 또는 `using` 문을 추가합니다.  
  
    ```vb#  
    Imports Microsoft.VisualBasic.PowerPacks  
    ```  
  
    ```c#  
    using Microsoft.VisualBasic.PowerPacks;  
    ```  
  
3.  이벤트 프로시저에 다음 코드를 추가합니다.  
  
     [!code-cs[VbPowerPacksTabbing#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/csharp/VbPowerPacksTabbingCS/VbPowerPacksTabbing.cs#1)]
     [!code-vb[VbPowerPacksTabbing#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/visualbasic/VbPowerPacksTabbing/VbPowerPacksTabbing.vb#1)]  
  
4.  `Button1_PreviewKeyDown` 이벤트 프로시저에 다음 코드를 추가합니다.  
  
     [!code-cs[VbPowerPacksTabbing#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/csharp/VbPowerPacksTabbingCS/VbPowerPacksTabbing.cs#2)]
     [!code-vb[VbPowerPacksTabbing#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/visualbasic/VbPowerPacksTabbing/VbPowerPacksTabbing.vb#2)]  
  
## 참고 항목  
 [How to: Draw Shapes with the OvalShape and RectangleShape Controls](../../../visual-basic/developing-apps/windows-forms/how-to-draw-shapes-with-the-ovalshape-and-rectangleshape-controls.md)   
 [How to: Draw Lines with the LineShape Control](../../../visual-basic/developing-apps/windows-forms/how-to-draw-lines-with-the-lineshape-control-visual-studio.md)   
 [Introduction to the Line and Shape Controls](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-line-and-shape-controls-visual-studio.md)