---
title: "방법: XAML의 바인딩에 사용할 수 있는 데이터 만들기"
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
- data binding [WPF], making data available for binding
- binding data [WPF], making data available for
ms.assetid: 7103c2e8-0e31-4a13-bf12-ca382221a8d5
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0c342f0d635a9220a88a2af79c76e2c1580dee2f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-make-data-available-for-binding-in-xaml"></a><span data-ttu-id="7b12d-102">방법: XAML의 바인딩에 사용할 수 있는 데이터 만들기</span><span class="sxs-lookup"><span data-stu-id="7b12d-102">How to: Make Data Available for Binding in XAML</span></span>
<span data-ttu-id="7b12d-103">이 항목에는 여러 가지 방법을 사용할 수 있게 만드는 데이터에 대 한 바인딩에서는 설명 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]응용 프로그램의 필요에 따라 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b12d-103">This topic discusses the different ways you can make data available for binding in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], depending on the needs of your application.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7b12d-104">예</span><span class="sxs-lookup"><span data-stu-id="7b12d-104">Example</span></span>  
 <span data-ttu-id="7b12d-105">있는 경우는 [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] 개체에서 바인딩할 원하는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], 사용할 수 있게 만드는 개체 바인딩 리소스로 정의 하 고 지정 하는 것 방법 중 하나는 `x:Key`합니다.</span><span class="sxs-lookup"><span data-stu-id="7b12d-105">If you have a [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] object you would like to bind to from [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], one way you can make the object available for binding is to define it as a resource and give it an `x:Key`.</span></span> <span data-ttu-id="7b12d-106">다음 예제는 `Person` 라는 문자열 속성이 있는 개체 `PersonName`합니다.</span><span class="sxs-lookup"><span data-stu-id="7b12d-106">In the following example, you have a `Person` object with a string property named `PersonName`.</span></span> <span data-ttu-id="7b12d-107">`Person` 개체가 라는 네임 스페이스에 정의 된 `SDKSample`합니다.</span><span class="sxs-lookup"><span data-stu-id="7b12d-107">The `Person` object is defined in the namespace called `SDKSample`.</span></span>  
  
 [!code-xaml[SimpleBinding#Instantiation](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#instantiation)]  
[!code-xaml[SimpleBinding#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#2)]  
  
 <span data-ttu-id="7b12d-108">개체에 바인딩할 수 있습니다 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]다음 예제에 나온 것 처럼 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b12d-108">You can then bind to the object in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], as shown in the following example.</span></span>  
  
 [!code-xaml[SimpleBinding#BDO1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#bdo1)]  
  
 <span data-ttu-id="7b12d-109">사용할 수 있습니다는 <xref:System.Windows.Data.ObjectDataProvider> 다음 예제와 같이 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="7b12d-109">Alternatively, you can use the <xref:System.Windows.Data.ObjectDataProvider> class, as in the following example.</span></span>  
  
 [!code-xaml[SimpleBinding#ODPCP](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Page1.xaml#odpcp)]  
  
 <span data-ttu-id="7b12d-110">바인딩을 정의 동일한 방식으로:</span><span class="sxs-lookup"><span data-stu-id="7b12d-110">You define the binding the same way:</span></span>  
  
 [!code-xaml[SimpleBinding#BDO1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#bdo1)]  
  
 <span data-ttu-id="7b12d-111">이 예의 경우 결과: 있는 <xref:System.Windows.Controls.TextBlock> 텍스트 콘텐츠로 `Joe`합니다.</span><span class="sxs-lookup"><span data-stu-id="7b12d-111">In this particular example, the result is the same: you have a <xref:System.Windows.Controls.TextBlock> with the text content `Joe`.</span></span> <span data-ttu-id="7b12d-112">그러나는 <xref:System.Windows.Data.ObjectDataProvider> 클래스 메서드의 결과에 바인딩할 수와 같은 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b12d-112">However, the <xref:System.Windows.Data.ObjectDataProvider> class provides functionality such as the ability to bind to the result of a method.</span></span> <span data-ttu-id="7b12d-113">사용 하도록 선택할 수는 <xref:System.Windows.Data.ObjectDataProvider> 클래스 제공 하는 기능이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b12d-113">You can choose to use the <xref:System.Windows.Data.ObjectDataProvider> class if you need the functionality it provides.</span></span>  
  
 <span data-ttu-id="7b12d-114">그러나 이미 만들어져 있는 개체에 바인딩하는 경우 설정 해야는 `DataContext` 다음 예제와 같이 코드에서.</span><span class="sxs-lookup"><span data-stu-id="7b12d-114">However, if you are binding to an object that has already been created, you need to set the `DataContext` in code, as in the following example.</span></span>  
  
 [!code-csharp[ADODataSet#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ADODataSet#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ADODataSet/VisualBasic/Window1.xaml.vb#1)]  
  
 <span data-ttu-id="7b12d-115">에 액세스 하려면 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 바인딩 사용에 대 한 데이터는 <xref:System.Windows.Data.XmlDataProvider> 클래스를 참조 하십시오. [XMLDataProvider 및 XPath 쿼리가 사용 하 여 XML 데이터에 바인딩할](../../../../docs/framework/wpf/data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7b12d-115">To access [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data for binding using the <xref:System.Windows.Data.XmlDataProvider> class, see [Bind to XML Data Using an XMLDataProvider and XPath Queries](../../../../docs/framework/wpf/data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md).</span></span> <span data-ttu-id="7b12d-116">에 액세스 하려면 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 바인딩 사용에 대 한 데이터는 <xref:System.Windows.Data.ObjectDataProvider> 클래스를 참조 하십시오. [XML 쿼리 결과 대 한 XDocument, XElement, 또는 LINQ를 바인딩할](../../../../docs/framework/wpf/data/how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7b12d-116">To access [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data for binding using the <xref:System.Windows.Data.ObjectDataProvider> class, see [Bind to XDocument, XElement, or LINQ for XML Query Results](../../../../docs/framework/wpf/data/how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md).</span></span>  
  
 <span data-ttu-id="7b12d-117">바인딩하는 데이터를 지정할 수 있는 다양 한 방법에 대 한 내용은 참조 하십시오. [바인딩 소스를 지정할](../../../../docs/framework/wpf/data/how-to-specify-the-binding-source.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7b12d-117">For information about the different ways you can specify the data you are binding to, see [Specify the Binding Source](../../../../docs/framework/wpf/data/how-to-specify-the-binding-source.md).</span></span> <span data-ttu-id="7b12d-118">어떤 유형의 데이터를 바인딩할 수 있습니다 또는 자체적으로 구현 하는 방법에 대 한 내용은 [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] 바인딩에 대 한 개체 참조 [바인딩 소스 개요](../../../../docs/framework/wpf/data/binding-sources-overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7b12d-118">For information about what types of data you can bind to or how to implement your own [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] objects for binding, see [Binding Sources Overview](../../../../docs/framework/wpf/data/binding-sources-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b12d-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7b12d-119">See Also</span></span>  
 [<span data-ttu-id="7b12d-120">데이터 바인딩 개요</span><span class="sxs-lookup"><span data-stu-id="7b12d-120">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="7b12d-121">방법 항목</span><span class="sxs-lookup"><span data-stu-id="7b12d-121">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
