---
title: "중첩된 Graphics 컨테이너 사용 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "그래픽[Windows Forms], 클리핑"
  - "그래픽, 중첩 컨테이너"
  - "그래픽, 중첩 개체에서 변환"
ms.assetid: a0d9f178-43a4-4323-bb5a-d3e3f77ae6c1
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# 중첩된 Graphics 컨테이너 사용
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]에서는 <xref:System.Drawing.Graphics> 개체에서 상태의 일부를 임시로 교체하거나 확대하는 데 사용할 수 있는 컨테이너를 제공합니다.  컨테이너를 만들 경우에는 <xref:System.Drawing.Graphics> 개체의 <xref:System.Drawing.Graphics.BeginContainer%2A> 메서드를 호출합니다.  <xref:System.Drawing.Graphics.BeginContainer%2A>를 반복적으로 호출하여 중첩 컨테이너를 만들 수 있습니다.  <xref:System.Drawing.Graphics.BeginContainer%2A>를 한 번 호출할 때마다 <xref:System.Drawing.Graphics.EndContainer%2A>도 한 번씩 호출해야 합니다.  
  
## 중첩 컨테이너에서 변환  
 다음 예제에서는 <xref:System.Drawing.Graphics> 개체와 이 <xref:System.Drawing.Graphics> 개체 안에 컨테이너를 만듭니다.  <xref:System.Drawing.Graphics> 개체에 대한 전역 변환에서는 x 방향으로 100단위 이동하고 y 방향으로 80단위 이동합니다.  컨테이너에 대한 전역 변환에서는 30도 회전합니다.  이 코드에서는  `DrawRectangle(pen, -60, -30, 120, 60)` 을 두 번 호출합니다.  첫 번째 <xref:System.Drawing.Graphics.DrawRectangle%2A> 호출은 컨테이너 안에서 수행됩니다. 즉, <xref:System.Drawing.Graphics.BeginContainer%2A>를 호출한 후 <xref:System.Drawing.Graphics.EndContainer%2A>를 호출하기 전에 수행됩니다.  두 번째 <xref:System.Drawing.Graphics.DrawRectangle%2A> 호출은 <xref:System.Drawing.Graphics.EndContainer%2A>를 호출한 후에 수행됩니다.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#61](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.MiscLegacyTopics#61](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#61)]  
  
 위의 코드에서 컨테이너 안에서 그린 사각형은 먼저 컨테이너의 전역 변환을 통해 변환된 다음\(회전\) <xref:System.Drawing.Graphics> 개체의 전역 변환을 통해 변환되고\(이동\)  컨테이너 밖에서 그린 사각형은 <xref:System.Drawing.Graphics> 개체의 전역 변환을 통해서만 변환됩니다\(이동\).  아래 그림에 이러한 두 개의 사각형이 나와 있습니다.  
  
 ![중첩 컨테이너](../../../../docs/framework/winforms/advanced/media/csnestedcontainers1.png "csnestedcontainers1")  
  
## 중첩 컨테이너에서 클리핑  
 아래 예제에서는 중첩된 컨테이너에서 클리핑 영역을 처리하는 방법을 보여 줍니다.  이 코드에서는 <xref:System.Drawing.Graphics> 개체와 이 <xref:System.Drawing.Graphics> 개체 안에 컨테이너를 만듭니다.  <xref:System.Drawing.Graphics> 개체의 클리핑 영역은 사각형이며 컨테이너의 클리핑 영역은 타원입니다.  이 코드에서는 <xref:System.Drawing.Graphics.DrawLine%2A> 메서드를 두 번 호출합니다.  첫 번째 <xref:System.Drawing.Graphics.DrawLine%2A> 호출은 컨테이너 안에서 수행되고 두 번째 <xref:System.Drawing.Graphics.DrawLine%2A> 호출은 <xref:System.Drawing.Graphics.EndContainer%2A>를 호출한 후 컨테이너 외부에서 수행됩니다.  첫 번째 선은 두 클리핑 영역의 교차 부분에 의해 클리핑됩니다.  두 번째 선은 <xref:System.Drawing.Graphics> 개체의 사각형 클리핑 영역에 의해서만 클리핑됩니다.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#62](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#62)]
 [!code-vb[System.Drawing.MiscLegacyTopics#62](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#62)]  
  
 아래 그림에 클리핑된 두 개의 선이 나와 있습니다.  
  
 ![중첩 컨테이너](../../../../docs/framework/winforms/advanced/media/nestedcontainers2.png "nestedcontainers2")  
  
 위의 두 예제에서 보았듯이 중첩된 컨테이너에서 변환과 클리핑 영역은 누진적으로 적용됩니다.  컨테이너와 <xref:System.Drawing.Graphics> 개체에 대해 둘 다 전역 변환을 설정하면 컨테이너 안에서 그리는 항목에 두 변환이 모두 적용됩니다.  이 때 컨테이너의 변환이 먼저 적용되고 <xref:System.Drawing.Graphics> 개체의 변환이 두 번째로 적용됩니다.  컨테이너와 <xref:System.Drawing.Graphics> 개체에 대해 둘 다 클리핑 영역을 설정하면 컨테이너 안에서 그리는 항목이 두 클리핑 영역의 교차 부분에 의해 클리핑됩니다.  
  
## 중첩 컨테이너에서 품질 설정  
 중첩 컨테이너에서 <xref:System.Drawing.Graphics.SmoothingMode%2A>, <xref:System.Drawing.Graphics.TextRenderingHint%2A>와 같은 품질 설정은 누적되지 않고 <xref:System.Drawing.Graphics> 개체의 품질 설정 대신 컨테이너의 품질 설정이 임시로 사용됩니다.  새로 만드는 컨테이너의 품질 설정은 기본값으로 지정됩니다.  예를 들어 다듬기 모드가 <xref:System.Drawing.Drawing2D.SmoothingMode>인 <xref:System.Drawing.Graphics> 개체가 있다고 가정합니다.  컨테이너를 만들 때 컨테이너 안의 다듬기 모드는 기본 다듬기 모드로 설정되지만,  필요하면 이를 다르게 설정하여 컨테이너 안에서 그리는 항목에 적용되도록 할 수 있습니다.  그러나 <xref:System.Drawing.Graphics.EndContainer%2A>를 호출한 후 그리는 항목에는 <xref:System.Drawing.Graphics.BeginContainer%2A>를 호출하기 전에 설정되어 있던 다듬기 모드\(<xref:System.Drawing.Drawing2D.SmoothingMode>\)가 적용됩니다.  
  
## 중첩된 컨테이너의 여러 계층  
 <xref:System.Drawing.Graphics> 개체에 여러 개의 컨테이너를 둘 수 있습니다.  연이어 중첩되는 일련의 컨테이너를 만들고 중첩된 컨테이너 각각에 대해 전역 변환, 클리핑 영역 및 품질 설정을 지정할 수 있습니다.  가장 안쪽의 컨테이너에서 그리기 메서드를 호출하면 가장 안쪽 컨테이너에서 시작하여 가장 바깥쪽 컨테이너까지 순서대로 변환이 적용됩니다.  가장 안쪽 컨테이너에서 그리는 항목은 모든 클리핑 영역의 교차 부분에 의해 클리핑됩니다.  
  
 다음 예제에서는 <xref:System.Drawing.Graphics> 개체를 만들고 텍스트 렌더링 힌트를 <xref:System.Drawing.Drawing2D.SmoothingMode>로 설정합니다.  이 코드에서는 한 컨테이너가 다른 컨테이너에 중첩된 방식으로 두 개의 컨테이너를 만듭니다.  이 때 외부 컨테이너의 텍스트 렌더링 힌트는 <xref:System.Drawing.Text.TextRenderingHint>로 설정하고 내부 컨테이너의 텍스트 렌더링 힌트는 <xref:System.Drawing.Drawing2D.SmoothingMode>로 설정합니다.  이 코드에서는 내부 컨테이너, 외부 컨테이너, <xref:System.Drawing.Graphics> 개체 자체에서 각각 하나씩 모두 세 개의 문자열을 그립니다.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#63](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#63)]
 [!code-vb[System.Drawing.MiscLegacyTopics#63](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#63)]  
  
 아래 그림에 세 개의 문자열이 나와 있습니다.  내부 컨테이너 및 <xref:System.Drawing.Graphics> 개체에서 그리는 문자열은 앤티 앨리어싱을 통해 다듬어집니다.  그러나 외부 컨테이너에서 그리는 문자열의 경우 <xref:System.Drawing.Graphics.TextRenderingHint%2A> 속성이 <xref:System.Drawing.Text.TextRenderingHint>로 설정되어 있으므로 앤티 앨리어싱을 통해 다듬어지지 않습니다.  
  
 ![중첩 컨테이너](../../../../docs/framework/winforms/advanced/media/nestedcontainers3.png "nestedcontainers3")  
  
## 참고 항목  
 <xref:System.Drawing.Graphics>   
 [Graphics 개체의 상태 관리](../../../../docs/framework/winforms/advanced/managing-the-state-of-a-graphics-object.md)