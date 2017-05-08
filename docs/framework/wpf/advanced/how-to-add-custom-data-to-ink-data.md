---
title: "방법: 잉크 데이터에 사용자 지정 데이터 추가 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "잉크 데이터, 사용자 지정 데이터 추가"
  - "InkCanvas, 표시"
ms.assetid: f02aac6f-3436-4f7c-b6ea-0452cba5332c
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# 방법: 잉크 데이터에 사용자 지정 데이터 추가
잉크를 ISF\(Serialize된 잉크 형식\)로 저장할 때 잉크에 사용자 지정 데이터를 추가할 수 있습니다.  사용자 지정 데이터는 <xref:System.Windows.Ink.DrawingAttributes>, <xref:System.Windows.Ink.StrokeCollection> 또는 <xref:System.Windows.Ink.Stroke>에 저장할 수 있습니다.  사용자 지정 데이터를 세 개체에 저장할 수 있기 때문에 데이터를 저장할 최적의 위치를 선택할 수 있습니다.  세 클래스 모두 비슷한 메서드로 사용자 지정 데이터를 저장하고 액세스합니다.  
  
 다음 형식만 사용자 지정 데이터로 저장할 수 있습니다.  
  
-   <xref:System.Boolean>  
  
-   <xref:System.Boolean>\[\]  
  
-   <xref:System.Byte>  
  
-   <xref:System.Byte>\[\]  
  
-   <xref:System.Char>  
  
-   <xref:System.Char>\[\]  
  
-   <xref:System.DateTime>  
  
-   <xref:System.DateTime>\[\]  
  
-   <xref:System.Decimal>  
  
-   <xref:System.Decimal>\[\]  
  
-   <xref:System.Double>  
  
-   <xref:System.Double>\[\]  
  
-   <xref:System.Int16>  
  
-   <xref:System.Int16>\[\]  
  
-   <xref:System.Int32>  
  
-   <xref:System.Int32>\[\]  
  
-   <xref:System.Int64>  
  
-   <xref:System.Int64>\[\]  
  
-   <xref:System.Single>  
  
-   <xref:System.Single>\[\]  
  
-   <xref:System.String>  
  
-   <xref:System.UInt16>  
  
-   <xref:System.UInt16>\[\]  
  
-   <xref:System.UInt32>  
  
-   <xref:System.UInt32>\[\]  
  
-   <xref:System.UInt64>  
  
-   <xref:System.UInt64>\[\]  
  
## 예제  
 다음 예제에서는 <xref:System.Windows.Ink.StrokeCollection>에서 사용자 지정 데이터를 추가하고 검색하는 방법을 보여 줍니다.  
  
 [!code-csharp[HowToAddCustomDataToInk#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToAddCustomDataToInk/CSharp/Window1.xaml.cs#1)]  
  
 다음 예제에서는 <xref:System.Windows.Controls.InkCanvas> 및 두 개의 단추를 표시하는 응용 프로그램을 만듭니다.  `switchAuthor` 단추를 통해 두 명의 작성자가 두 개의 펜을 사용할 수 있습니다.  `changePenColors` 단추는 작성자에 따라 <xref:System.Windows.Controls.InkCanvas>의 각 스트로크 색을 변경합니다.  응용 프로그램은 두 개의 <xref:System.Windows.Ink.DrawingAttributes> 개체를 정의하고 <xref:System.Windows.Ink.Stroke>를 그린 작성자를 나타내는 사용자 지정 속성을 각 개체에 추가합니다.  사용자가 `changePenColors`를 클릭하면 응용 프로그램에서 스트로크의 모양이 사용자 지정 속성의 값에 따라 변경됩니다.  
  
 [!code-xml[HowToAddCustomDataToInk#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToAddCustomDataToInk/CSharp/Window1.xaml#2)]  
  
 [!code-csharp[HowToAddCustomDataToInk#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToAddCustomDataToInk/CSharp/Window1.xaml.cs#3)]