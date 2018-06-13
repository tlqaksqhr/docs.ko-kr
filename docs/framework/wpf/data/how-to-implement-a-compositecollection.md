---
title: '방법: CompositeCollection 구현'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], CompositeCollection class
ms.assetid: 0d8fc84c-7920-427f-8ad7-d55ca656c170
ms.openlocfilehash: f8af8d806b8c889be11533392ee3c831399e9ab7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33556119"
---
# <a name="how-to-implement-a-compositecollection"></a><span data-ttu-id="0c39a-102">방법: CompositeCollection 구현</span><span class="sxs-lookup"><span data-stu-id="0c39a-102">How to: Implement a CompositeCollection</span></span>
## <a name="example"></a><span data-ttu-id="0c39a-103">예제</span><span class="sxs-lookup"><span data-stu-id="0c39a-103">Example</span></span>  
 <span data-ttu-id="0c39a-104">다음 예제에서는 여러 컬렉션 및 항목을 사용 하 여 하나의 목록으로 표시 하는 방법을 보여 줍니다는 <xref:System.Windows.Data.CompositeCollection> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="0c39a-104">The following example shows how to display multiple collections and items as one list using the <xref:System.Windows.Data.CompositeCollection> class.</span></span> <span data-ttu-id="0c39a-105">이 예제에서는 `GreekGods` 는 <xref:System.Collections.ObjectModel.ObservableCollection%601> 의 `GreekGod` 사용자 지정 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="0c39a-105">In this example, `GreekGods` is an <xref:System.Collections.ObjectModel.ObservableCollection%601> of `GreekGod` custom objects.</span></span> <span data-ttu-id="0c39a-106">데이터 템플릿이 정의 되어 있도록 `GreekGod` 개체 및 `GreekHero` 개체 각각 녹청 전경색은와 함께 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c39a-106">Data templates are defined so that `GreekGod` objects and `GreekHero` objects appear with a gold and a cyan foreground color respectively.</span></span>  
  
 [!code-xaml[CompositeCollections#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CompositeCollections/CS/Window1.xaml#1)]  
  
## <a name="see-also"></a><span data-ttu-id="0c39a-107">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0c39a-107">See Also</span></span>  
 <xref:System.Windows.Data.CollectionContainer>  
 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>  
 <xref:System.Windows.Data.XmlDataProvider>  
 <xref:System.Windows.DataTemplate>  
 [<span data-ttu-id="0c39a-108">데이터 바인딩 개요</span><span class="sxs-lookup"><span data-stu-id="0c39a-108">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="0c39a-109">방법 항목</span><span class="sxs-lookup"><span data-stu-id="0c39a-109">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
