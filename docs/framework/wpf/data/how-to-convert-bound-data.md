---
title: "방법: 바인딩된 데이터 변환"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- converting [WPF], bound data
- data binding [WPF], converting bound data
- binding data [WPF], converting bound data
ms.assetid: b00aaa19-c6df-4c3b-a9fd-88a0b488df2b
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 88e248c7c8e60fbe8e55567cb642200820b25214
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-convert-bound-data"></a><span data-ttu-id="e5024-102">방법: 바인딩된 데이터 변환</span><span class="sxs-lookup"><span data-stu-id="e5024-102">How to: Convert Bound Data</span></span>
<span data-ttu-id="e5024-103">이 예제에서는 바인딩에 사용 되는 데이터에 변환을 적용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e5024-103">This example shows how to apply conversion to data that is used in bindings.</span></span>  
  
 <span data-ttu-id="e5024-104">데이터 바인딩 중으로 변환 하려면 구현 하는 클래스 만들어야 합니다는 <xref:System.Windows.Data.IValueConverter> 포함 된 인터페이스는 <xref:System.Windows.Data.IValueConverter.Convert%2A> 및 <xref:System.Windows.Data.IValueConverter.ConvertBack%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="e5024-104">To convert data during binding, you must create a class that implements the <xref:System.Windows.Data.IValueConverter> interface, which includes the <xref:System.Windows.Data.IValueConverter.Convert%2A> and <xref:System.Windows.Data.IValueConverter.ConvertBack%2A> methods.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e5024-105">예제</span><span class="sxs-lookup"><span data-stu-id="e5024-105">Example</span></span>  
 <span data-ttu-id="e5024-106">다음 예제에는 연도, 월 및 일만 표시 되도록에 전달 되는 날짜 값을 변환 하는 날짜 변환기의 구현을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e5024-106">The following example shows the implementation of a date converter that converts the date value passed in so that it only shows the year, the month, and the day.</span></span> <span data-ttu-id="e5024-107">구현 하는 경우는 <xref:System.Windows.Data.IValueConverter> 인터페이스를 사용 하 여 구현을 데코 레이트 하는 것이 좋습니다는는 <xref:System.Windows.Data.ValueConversionAttribute> 개발에 알리기 위해 특성 도구는 다음 예제 에서처럼 변환과 관련 된 데이터 형식:</span><span class="sxs-lookup"><span data-stu-id="e5024-107">When implementing the <xref:System.Windows.Data.IValueConverter> interface, it is a good practice to decorate the implementation with a <xref:System.Windows.Data.ValueConversionAttribute> attribute to indicate to development tools the data types involved in the conversion, as in the following example:</span></span>  
  
 [!code-csharp[DataBindingLab#18](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DateConverter.cs#18)]
 [!code-vb[DataBindingLab#18](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/DateConverter.vb#18)]  
  
 <span data-ttu-id="e5024-108">변환기를 만든 후에 리소스로 추가할 수 있습니다 프로그램 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="e5024-108">Once you have created a converter, you can add it as a resource in your [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file.</span></span> <span data-ttu-id="e5024-109">다음 예에서 *src* 는 네임 스페이스로 매핑되면 *DateConverter* 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5024-109">In the following example, *src* maps to the namespace in which *DateConverter* is defined.</span></span>  
  
 [!code-xaml[DataBindingLab#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DataBindingLabApp.xaml#15)]  
  
 <span data-ttu-id="e5024-110">마지막으로 다음 구문을 사용 하 여 바인딩을에서 변환기를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5024-110">Finally, you can use the converter in your binding using the following syntax.</span></span> <span data-ttu-id="e5024-111">다음 예제에서는 텍스트의 콘텐츠는 <xref:System.Windows.Controls.TextBlock> 에 바인딩된 *StartDate*, 외부 데이터 원본의 속성인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5024-111">In the following example, the text content of the <xref:System.Windows.Controls.TextBlock> is bound to *StartDate*, which is a property of an external data source.</span></span>  
  
 [!code-xaml[DataBindingLab#17](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DataBindingLabApp.xaml#17)]  
  
 <span data-ttu-id="e5024-112">위의 예제에서 참조 된 스타일 리소스는이 항목에 표시 되지 않은 리소스 섹션에 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5024-112">The style resources referenced in the above example are defined in a resource section not shown in this topic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5024-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e5024-113">See Also</span></span>  
 [<span data-ttu-id="e5024-114">바인딩 유효성 검사 구현</span><span class="sxs-lookup"><span data-stu-id="e5024-114">Implement Binding Validation</span></span>](../../../../docs/framework/wpf/data/how-to-implement-binding-validation.md)  
 [<span data-ttu-id="e5024-115">데이터 바인딩 개요</span><span class="sxs-lookup"><span data-stu-id="e5024-115">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="e5024-116">방법 항목</span><span class="sxs-lookup"><span data-stu-id="e5024-116">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
