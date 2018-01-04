---
title: "방법: GridView를 사용하여 ListView 콘텐츠 표시"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ListView controls [WPF], displaying contents with GridView
- GridView [WPF], displaying ListView contents
ms.assetid: 5bc1e767-ab46-4f14-bd41-3d5d39e1d000
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ee2885868c07b00f16290b6414e7f7bdd64fd68c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-display-listview-contents-by-using-a-gridview"></a>방법: GridView를 사용하여 ListView 콘텐츠 표시
정의 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.GridView> 에 대 한 보기 모드는 <xref:System.Windows.Controls.ListView> 제어 합니다.  
  
## <a name="example"></a>예  
 보기 모드를 정의할 수 있습니다는 <xref:System.Windows.Controls.GridView> 지정 하 여 <xref:System.Windows.Controls.GridViewColumn> 개체입니다. 다음 예제에서는 정의 하는 방법을 보여 줍니다. <xref:System.Windows.Controls.GridViewColumn> 에 대해 지정 된 데이터 콘텐츠를 바인딩하는 개체는 <xref:System.Windows.Controls.ListView> 제어 합니다. 이 <xref:System.Windows.Controls.GridView> 3을 지정 하는 예제 <xref:System.Windows.Controls.GridViewColumn> 개체에 매핑되는 `FirstName`, `LastName`, 및 `EmployeeNumber` 의 필드는 `EmployeeInfoDataSource` 로 설정 되어 있는 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> 의 <xref:System.Windows.Controls.ListView> 제어 합니다.  
  
 [!code-xaml[ListViewCode#ListViewEmployee](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#listviewemployee)]  
  
 다음 그림은이 예제에서는 표시 되는 방법을 보여 줍니다.  
  
 ![GridView 출력이 있는 ListView](../../../../docs/framework/wpf/controls/media/listviewgridview.JPG "ListViewGridView")  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Controls.ListView>  
 <xref:System.Windows.Controls.GridView>  
 [ListView 개요](../../../../docs/framework/wpf/controls/listview-overview.md)  
 [GridView 개요](../../../../docs/framework/wpf/controls/gridview-overview.md)  
 [방법 항목](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)
