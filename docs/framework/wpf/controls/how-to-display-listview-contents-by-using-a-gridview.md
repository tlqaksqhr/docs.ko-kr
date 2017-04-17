---
title: "방법: GridView를 사용하여 ListView 콘텐츠 표시 | Microsoft Docs"
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
  - "GridView, ListView 콘텐츠 표시"
  - "ListView 컨트롤, GridView의 콘텐츠 표시"
ms.assetid: 5bc1e767-ab46-4f14-bd41-3d5d39e1d000
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# 방법: GridView를 사용하여 ListView 콘텐츠 표시
이 예제에서는 <xref:System.Windows.Controls.ListView> 컨트롤의 <xref:System.Windows.Controls.GridView> 보기 모드를 정의하는 방법을 보여 줍니다.  
  
## 예제  
 <xref:System.Windows.Controls.GridViewColumn> 개체를 지정하여 <xref:System.Windows.Controls.GridView>의 보기 모드를 정의할 수 있습니다.  다음 예제에서는 <xref:System.Windows.Controls.ListView> 컨트롤에 지정된 데이터 콘텐츠를 바인딩되는 <xref:System.Windows.Controls.GridViewColumn> 개체를 정의하는 방법을 보여 줍니다.  이 <xref:System.Windows.Controls.GridView> 예제에서는 <xref:System.Windows.Controls.ListView> 컨트롤의 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>로 설정되어 있는 `EmployeeInfoDataSource`의 `FirstName`, `LastName` 및 `EmployeeNumber` 필드에 매핑되는 세 가지 <xref:System.Windows.Controls.GridViewColumn> 개체를 지정합니다.  
  
 [!code-xml[ListViewCode#ListViewEmployee](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#listviewemployee)]  
  
 다음 그림에서는 이 예제가 표시되는 방법을 보여 줍니다.  
  
 ![GridView 출력이 있는 ListView](../../../../docs/framework/wpf/controls/media/listviewgridview.png "ListViewGridView")  
  
## 참고 항목  
 <xref:System.Windows.Controls.ListView>   
 <xref:System.Windows.Controls.GridView>   
 [ListView 개요](../../../../docs/framework/wpf/controls/listview-overview.md)   
 [GridView 개요](../../../../docs/framework/wpf/controls/gridview-overview.md)   
 [방법 항목](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)