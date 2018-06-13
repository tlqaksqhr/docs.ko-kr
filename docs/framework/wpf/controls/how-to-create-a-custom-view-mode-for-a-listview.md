---
title: '방법: ListView의 사용자 지정 뷰 모드 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView controls [WPF], creating custom View mode
ms.assetid: 71077349-eeb9-4344-ab29-b5df96df3314
ms.openlocfilehash: b8600a2e201fdbcb566e6a322e3ecdabbe1641ef
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33551871"
---
# <a name="how-to-create-a-custom-view-mode-for-a-listview"></a>방법: ListView의 사용자 지정 뷰 모드 만들기
이 예제에는 사용자 지정을 만드는 방법을 보여 줍니다 <xref:System.Windows.Controls.ListView.View%2A> 에 대 한 모드는 <xref:System.Windows.Controls.ListView> 제어 합니다.  
  
## <a name="example"></a>예제  
 사용 해야 합니다는 <xref:System.Windows.Controls.ViewBase> 클래스에 대 한 사용자 지정 보기를 만들 때의 <xref:System.Windows.Controls.ListView> 제어 합니다. 다음 예제에서는 라고 하는 뷰 모드 `PlainView`에서 파생 되는 <xref:System.Windows.Controls.ViewBase> 클래스입니다.  
  
 [!code-csharp[ListViewCustomView#PlainView](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/PlainView.cs#plainview)]
 [!code-vb[ListViewCustomView#PlainView](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic/plainview.vb#plainview)]  
  
 사용자 지정 보기에는 스타일을 적용 하려면 사용 하 여는 <xref:System.Windows.Style> 클래스입니다. 다음 예제에서는 정의 <xref:System.Windows.Style> 에 대 한는 `PlainView` 보기 모드입니다. 이전 예제에서는이 스타일의 값으로 설정 된 <xref:System.Windows.Controls.ViewBase.DefaultStyleKey%2A> 속성에 대해 정의 된 `PlainView`합니다.  
  
 [!code-xaml[ListViewCustomView#PlainViewStyle](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Themes/Generic.xaml#plainviewstyle)]  
  
 사용자 지정 보기 모드에서 데이터의 레이아웃을 정의 하려면 정의 <xref:System.Windows.DataTemplate> 개체입니다. 다음 예제에서는 정의 <xref:System.Windows.DataTemplate> 에 데이터를 표시를 사용할 수 있는 `PlainView` 보기 모드입니다.  
  
 [!code-xaml[ListViewCustomView#PlainViewDataTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml#plainviewdatatemplate)]  
  
 다음 예제에서는 정의 하는 방법을 보여 줍니다.는 <xref:System.Windows.ResourceKey> 에 대 한는 `PlainView` 보기 모드를 사용 하는 <xref:System.Windows.DataTemplate> 앞의 예제에 정의 된 합니다.  
  
 [!code-xaml[ListViewCustomView#PlainViewtileView](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml#plainviewtileview)]  
  
 A <xref:System.Windows.Controls.ListView> 컨트롤 설정 하면 사용자 지정 보기를 사용할 수는 <xref:System.Windows.Controls.ListView.View%2A> 속성을 리소스 키입니다. 다음 예제에서는 지정 하는 방법을 보여 줍니다. `PlainView` 에 대 한 보기 모드와는 <xref:System.Windows.Controls.ListView>합니다.  
  
 [!code-csharp[ListViewCustomView#ListViewtileViewmode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml.cs#listviewtileviewmode)]
 [!code-vb[ListViewCustomView#ListViewtileViewmode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic/window1.xaml.vb#listviewtileviewmode)]  
  
 전체 샘플을 참조 하십시오. [여러 보기 샘플에는 ListView](http://go.microsoft.com/fwlink/?LinkID=160013)합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Controls.ListView>  
 <xref:System.Windows.Controls.GridView>  
 [방법 항목](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)  
 [ListView 개요](../../../../docs/framework/wpf/controls/listview-overview.md)  
 [GridView 개요](../../../../docs/framework/wpf/controls/gridview-overview.md)
