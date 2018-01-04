---
title: "방법: XDocument, XElement 또는 LINQ for XML 쿼리 결과에 바인딩"
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
- data binding [WPF], binding to XDocument
- data binding [WPF], binding to XElement
ms.assetid: 6a629a49-fe1c-465d-b76a-3dcbf4307b64
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ceb6023157d487aebeff4fb5335b58c0958f2851
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results"></a><span data-ttu-id="2466b-102">방법: XDocument, XElement 또는 LINQ for XML 쿼리 결과에 바인딩</span><span class="sxs-lookup"><span data-stu-id="2466b-102">How to: Bind to XDocument, XElement, or LINQ for XML Query Results</span></span>
<span data-ttu-id="2466b-103">XML 데이터를 바인딩하는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.ItemsControl> 를 사용 하 여 <xref:System.Xml.Linq.XDocument>합니다.</span><span class="sxs-lookup"><span data-stu-id="2466b-103">This example demonstrates how to bind XML data to an <xref:System.Windows.Controls.ItemsControl> using <xref:System.Xml.Linq.XDocument>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2466b-104">예</span><span class="sxs-lookup"><span data-stu-id="2466b-104">Example</span></span>  
 <span data-ttu-id="2466b-105">다음 XAML 코드 정의 <xref:System.Windows.Controls.ItemsControl> 형식의 데이터에 대 한 데이터 템플릿을 포함 `Planet` 에 `http://planetsNS` XML 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="2466b-105">The following XAML code defines an <xref:System.Windows.Controls.ItemsControl> and includes a data template for data of type `Planet` in the `http://planetsNS` XML namespace.</span></span> <span data-ttu-id="2466b-106">네임스페이스를 차지하는 XML 데이터 형식은 중괄호에서 네임스페이스를 포함해야 하고 XAML 태그 확장이 표시되는 위치에 표시되는 경우 중괄호 이스케이프 시퀀스를 가진 네임스페이스 앞에 표시되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2466b-106">An XML data type that occupies a namespace must include the namespace in braces, and if it appears where a XAML markup extension could appear, it must precede the namespace with a brace escape sequence.</span></span> <span data-ttu-id="2466b-107">이 코드에 해당 하는 동적 속성에 바인딩하는 <xref:System.Xml.Linq.XContainer.Element%2A> 및 <xref:System.Xml.Linq.XElement.Attribute%2A> 의 메서드는 <xref:System.Xml.Linq.XElement> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="2466b-107">This code binds to dynamic properties that correspond to the <xref:System.Xml.Linq.XContainer.Element%2A> and <xref:System.Xml.Linq.XElement.Attribute%2A> methods of the <xref:System.Xml.Linq.XElement> class.</span></span> <span data-ttu-id="2466b-108">동적 속성을 사용하면 XAML을 메서드의 이름을 공유하는 동적 속성에 바인딩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2466b-108">Dynamic properties enable XAML to bind to dynamic properties that share the names of methods.</span></span> <span data-ttu-id="2466b-109">자세한 내용은 [LINQ to XML 동적 속성](/visualstudio/designers/linq-to-xml-dynamic-properties)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2466b-109">To learn more, see [LINQ to XML Dynamic Properties](/visualstudio/designers/linq-to-xml-dynamic-properties).</span></span> <span data-ttu-id="2466b-110">XML의 기본 네임스페이스 선언이 특성 이름에 적용되지 않는지를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="2466b-110">Notice how the default namespace declaration for the XML does not apply to attribute names.</span></span>  
  
 [!code-xaml[XLinqExample#StackPanelResources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml#stackpanelresources)]  
[!code-xaml[XLinqExample#ItemsControl](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml#itemscontrol)]  
  
 <span data-ttu-id="2466b-111">다음 C# 코드에서는 <xref:System.Xml.Linq.XDocument.Load%2A> 라는 요소의 모든 하위 요소를 스택 패널 데이터 컨텍스트를 설정 하 고 `SolarSystemPlanets` 에 `http://planetsNS` XML 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="2466b-111">The following C# code calls <xref:System.Xml.Linq.XDocument.Load%2A> and sets the stack panel data context to all subelements of the element named `SolarSystemPlanets` in the `http://planetsNS` XML namespace.</span></span>  
  
 [!code-csharp[XLinqExample#LoadDCFromFile](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml.cs#loaddcfromfile)]
 [!code-vb[XLinqExample#LoadDCFromFile](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/XLinqExample/visualbasic/window1.xaml.vb#loaddcfromfile)]  
  
 <span data-ttu-id="2466b-112">XML 데이터를 사용 하 여 XAML 리소스도 저장할 수 <xref:System.Windows.Data.ObjectDataProvider>합니다.</span><span class="sxs-lookup"><span data-stu-id="2466b-112">XML data can be stored as a XAML resource using <xref:System.Windows.Data.ObjectDataProvider>.</span></span> <span data-ttu-id="2466b-113">전체 예제는 [L2DBForm.xaml 소스 코드](http://msdn.microsoft.com/library/624e96d4-6d27-4195-8ac2-2f3835f6c57e)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2466b-113">For a complete example, see  [L2DBForm.xaml Source Code](http://msdn.microsoft.com/library/624e96d4-6d27-4195-8ac2-2f3835f6c57e).</span></span> <span data-ttu-id="2466b-114">다음 샘플에서는 코드가 데이터 컨텍스트를 개체 리소스로 설정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2466b-114">The following sample shows how code can set the data context to an object resource.</span></span>  
  
 [!code-csharp[XLinqExample#LoadDCFromXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml.cs#loaddcfromxaml)]
 [!code-vb[XLinqExample#LoadDCFromXAML](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/XLinqExample/visualbasic/window1.xaml.vb#loaddcfromxaml)]  
  
 <span data-ttu-id="2466b-115">동적 속성에 매핑되는 <xref:System.Xml.Linq.XContainer.Element%2A> 및 <xref:System.Xml.Linq.XElement.Attribute%2A> XAML 내에서 유연성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2466b-115">The dynamic properties that map to <xref:System.Xml.Linq.XContainer.Element%2A> and <xref:System.Xml.Linq.XElement.Attribute%2A> provide flexibility within XAML.</span></span> <span data-ttu-id="2466b-116">코드는 LINQ for XML 쿼리의 결과에 바인딩될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2466b-116">Your code can also bind to the results of a LINQ for XML query.</span></span> <span data-ttu-id="2466b-117">이 예제는 요소 값으로 정렬된 쿼리 결과에 바인딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="2466b-117">This example binds to query results ordered by an element value.</span></span>  
  
 [!code-csharp[XLinqExample#BindToResults](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml.cs#bindtoresults)]
 [!code-vb[XLinqExample#BindToResults](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/XLinqExample/visualbasic/window1.xaml.vb#bindtoresults)]  
  
## <a name="see-also"></a><span data-ttu-id="2466b-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2466b-118">See Also</span></span>  
 [<span data-ttu-id="2466b-119">바인딩 소스 개요</span><span class="sxs-lookup"><span data-stu-id="2466b-119">Binding Sources Overview</span></span>](../../../../docs/framework/wpf/data/binding-sources-overview.md)  
 [<span data-ttu-id="2466b-120">LINQ to XML로 WPF 데이터 바인딩 개요</span><span class="sxs-lookup"><span data-stu-id="2466b-120">WPF Data Binding with LINQ to XML Overview</span></span>](/visualstudio/designers/wpf-data-binding-with-linq-to-xml-overview)  
 [<span data-ttu-id="2466b-121">LINQ to XML 예제를 사용한 WPF 데이터 바인딩</span><span class="sxs-lookup"><span data-stu-id="2466b-121">WPF Data Binding Using LINQ to XML Example</span></span>](/visualstudio/designers/wpf-data-binding-using-linq-to-xml-example)  
 [<span data-ttu-id="2466b-122">LINQ to XML 동적 속성</span><span class="sxs-lookup"><span data-stu-id="2466b-122">LINQ to XML Dynamic Properties</span></span>](/visualstudio/designers/linq-to-xml-dynamic-properties)
