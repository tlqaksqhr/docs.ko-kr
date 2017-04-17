---
title: "방법: 영역을 사용하여 적중 테스트 | Microsoft Docs"
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
  - "적중 테스트, 영역 사용"
  - "영역, 적중 테스트"
ms.assetid: 3a4c07cb-a40a-4d14-ad35-008f531910a8
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# 방법: 영역을 사용하여 적중 테스트
커서가 아이콘이나 단추 같은 특정 개체 위에 있는지 여부를 알기 위해 적중 테스트를 수행합니다.  
  
## 예제  
 아래 예제에서는 두 개의 사각형 영역을 결합하여 더하기 기호 모양의 영역을 만듭니다.   `point`  변수에는 가장 최근에 클릭한 위치가 포함된다고 가정합니다.  코드를 통해  `point`  변수의 값이 더하기 기호 모양의 영역에 있는지 여부를 확인하고  point 변수의 값이 영역에 있으면, 즉 적중 테스트 결과가 참이면 빨간색 불투명 브러시를 사용하여 영역을 채웁니다.  그렇지 않으면 빨간색 반투명 브러시를 사용하여 영역을 채웁니다.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.MiscLegacyTopics#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#31)]  
  
## 코드 컴파일  
 앞의 예제는 Windows Forms에서 사용해야 하며 <xref:System.Windows.Forms.PaintEventHandler>의 매개 변수인 <xref:System.Windows.Forms.PaintEventArgs> `e`를 필요로 합니다.  
  
## 참고 항목  
 <xref:System.Drawing.Region>   
 [GDI\+의 영역](../../../../docs/framework/winforms/advanced/regions-in-gdi.md)   
 [방법: 영역을 사용하여 클리핑](../../../../docs/framework/winforms/advanced/how-to-use-clipping-with-a-region.md)