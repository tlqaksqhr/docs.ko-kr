---
title: "방법: 합성 모드를 사용하여 알파 혼합 조절 | Microsoft Docs"
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
  - "알파 혼합, 합성"
  - "색, 혼합"
  - "색, 투명도 조정"
ms.assetid: f331df2d-b395-4b0a-95be-24fec8c9bbb5
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# 방법: 합성 모드를 사용하여 알파 혼합 조절
다음과 같은 특징이 있는 오프 스크린 비트맵을 만드는 경우가 있습니다.  
  
-   색의 알파 값이 255보다 작습니다.  
  
-   비트맵을 만들 때 색 상호 간에 알파 혼합이 발생하지 않습니다.  
  
-   완성한 비트맵을 표시할 때 비트맵에 있는 색이 디스플레이 장치의 배경색과 알파 혼합됩니다.  
  
 이러한 비트맵을 만들려면 빈 <xref:System.Drawing.Bitmap> 개체를 만든 다음 이 비트맵을 기반으로 <xref:System.Drawing.Graphics> 개체를 만들고  <xref:System.Drawing.Graphics> 개체의 합성 모드를 <xref:System.Drawing.Drawing2D.CompositingMode?displayProperty=fullName>로 설정합니다.  
  
## 예제  
 다음 예제에서는 <xref:System.Drawing.Bitmap> 개체를 기반으로 <xref:System.Drawing.Graphics> 개체를 만듭니다.  이 코드에서는 두 개의 반투명 브러시\(알파 \= 160\)와 함께 <xref:System.Drawing.Graphics> 개체를 사용하여 비트맵에서 그리고  반투명 브러시를 사용하여 빨강 타원과 녹색 타원을 채웁니다.  녹색 타원은 빨강 타원과 겹치지만 <xref:System.Drawing.Graphics> 개체의 합성 모드가 <xref:System.Drawing.Drawing2D.CompositingMode>로 설정되어 있으므로 빨강과 혼합되지는 않습니다.  
  
 이 코드에서는 화면에 비트맵을 두 번 그립니다. 한 번은 흰색 배경 위에 비트맵을 그리고 또 한 번은 여러 색으로 된 배경 위에 그립니다.  두 타원의 일부에 속하는 비트맵에 있는 픽셀의 알파 구성 요소는 160이므로 타원이 화면의 배경색과 혼합됩니다.  
  
 다음 그림에서는 코드 예제를 실행한 결과를 보여 줍니다.  이 그림에서 타원은 배경색과 혼합되지만 타원 서로 간에는 혼합되지 않음을 알 수 있습니다.  
  
 ![소스 복사본](../../../../docs/framework/winforms/advanced/media/sourcecopy.png "sourcecopy")  
  
 코드 예제에는 다음 문이 포함되어 있습니다.  
  
 [!code-csharp[System.Drawing.AlphaBlending#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.AlphaBlending#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#41)]  
  
 타원이 배경색과 혼합될 뿐만 아니라 타원 서로 간에도 혼합되게 하려면 이 문을 다음과 같이 변경합니다.  
  
 [!code-csharp[System.Drawing.AlphaBlending#42](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#42)]
 [!code-vb[System.Drawing.AlphaBlending#42](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#42)]  
  
 아래 그림에서는 수정한 코드를 실행한 결과를 보여 줍니다.  
  
 ![소스 위에 있음](../../../../docs/framework/winforms/advanced/media/sourceover.png "sourceover")  
  
 [!code-csharp[System.Drawing.AlphaBlending#43](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#43)]
 [!code-vb[System.Drawing.AlphaBlending#43](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#43)]  
  
## 코드 컴파일  
 앞의 예제는 Windows Forms에서 사용해야 하며 <xref:System.Windows.Forms.PaintEventHandler>의 매개 변수인 <xref:System.Windows.Forms.PaintEventArgs> `e`를 필요로 합니다.  
  
## 참고 항목  
 <xref:System.Drawing.Color.FromArgb%2A>   
 [선 및 채우기 알파 혼합](../../../../docs/framework/winforms/advanced/alpha-blending-lines-and-fills.md)