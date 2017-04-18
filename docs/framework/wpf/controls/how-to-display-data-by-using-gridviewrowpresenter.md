---
title: "방법: GridViewRowPresenter를 사용하여 데이터 표시 | Microsoft Docs"
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
  - "GridViewRowPresenter를 사용하여 데이터 표시"
  - "GridViewRowPresenter"
ms.assetid: bdb785a5-a262-44d5-a517-ea14383e5f70
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# 방법: GridViewRowPresenter를 사용하여 데이터 표시
이 예제에서는 <xref:System.Windows.Controls.GridViewRowPresenter> 및 <xref:System.Windows.Controls.GridViewHeaderRowPresenter> 개체를 사용하여 데이터를 열에 표시하는 방법을 보여 줍니다.  
  
## 예제  
 다음 예제에서는 <xref:System.Windows.Controls.GridViewRowPresenter> 및 <xref:System.Windows.Controls.GridViewHeaderRowPresenter> 개체를 사용하여 <xref:System.DateTime> 개체의 <xref:System.DateTime.DayOfWeek%2A> 및 <xref:System.DateTime.Year%2A>를 표시하는 <xref:System.Windows.Controls.GridViewColumnCollection>을 지정하는 방법을 보여 줍니다.  또한 이 예제에서는 <xref:System.Windows.Controls.GridViewColumn>의 <xref:System.Windows.Controls.GridViewColumn.Header%2A>에 대한 <xref:System.Windows.Style>을 정의합니다.  
  
 [!code-xml[GridViewRowPresenterSample#GridViewRowPresenter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridViewRowPresenterSample/CS/Window1.xaml#gridviewrowpresenter)]  
  
## 참고 항목  
 <xref:System.Windows.Controls.GridViewHeaderRowPresenter>   
 <xref:System.Windows.Controls.GridViewRowPresenter>   
 <xref:System.Windows.Controls.GridViewColumnCollection>   
 [GridView 개요](../../../../docs/framework/wpf/controls/gridview-overview.md)