---
title: "방법: Viewport3D의 적중 테스트 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "3차원 표시, 적중 테스트"
  - "적중 테스트, 3차원 표시"
  - "Viewport3D"
ms.assetid: 42bfbd99-c7c6-43f1-940b-90448faa412e
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# 방법: Viewport3D의 적중 테스트
이 예제에서는 <xref:System.Windows.Controls.Viewport3D>에서 3차원 시각적 표시를 적중 테스트하는 방법을 보여 줍니다.  
  
 <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A>에서 2차원 및 3차원 정보를 반환하기 때문에 3차원 결과만 읽는 테스트 결과를 반복할 수 있습니다.  
  
 [!code-csharp[HitTest3D#HitTest3D3DN4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HitTest3D/CSharp/Window1.xaml.cs#hittest3d3dn4)]
 [!code-vb[HitTest3D#HitTest3D3DN4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HitTest3D/visualbasic/window1.xaml.vb#hittest3d3dn4)]  
  
 다음 코드에서 <xref:System.Windows.Media.HitTestResultBehavior>는 적중 테스트 결과를 처리하는 방식을 결정합니다.  `UpdateResultInfo` 및 `UpdateMaterial`은 로컬로 정의된 메서드입니다.  
  
 [!code-csharp[HitTest3D#HitTest3D3DN5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HitTest3D/CSharp/Window1.xaml.cs#hittest3d3dn5)]
 [!code-vb[HitTest3D#HitTest3D3DN5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HitTest3D/visualbasic/window1.xaml.vb#hittest3d3dn5)]  
  
## 참고 항목  
 [3\-D Hit Testing 샘플](http://go.microsoft.com/fwlink/?LinkID=159959)