---
title: "방법: 웹 서비스 바인딩"
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
- binding data [WPF], Web service
- Web service binding [WPF]
- data binding [WPF], Web service
ms.assetid: 77e2d373-69ba-4cbd-b6f5-2c83c38fc98b
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5d1b81949d6d91420c828564debd311af47dfdfd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-bind-to-a-web-service"></a><span data-ttu-id="dc8ba-102">방법: 웹 서비스 바인딩</span><span class="sxs-lookup"><span data-stu-id="dc8ba-102">How to: Bind to a Web Service</span></span>
<span data-ttu-id="dc8ba-103">이 예제에는 웹 서비스 메서드 호출에서 반환 된 개체에 바인딩하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="dc8ba-103">This example shows how to bind to objects returned by Web service method calls.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dc8ba-104">예제</span><span class="sxs-lookup"><span data-stu-id="dc8ba-104">Example</span></span>  
 <span data-ttu-id="dc8ba-105">사용 하 여이 예제는 [MSDN/TechNet 게시 시스템 (MTPS) 콘텐츠 서비스](http://go.microsoft.com/fwlink/?LinkId=95677) 지정된 된 문서에서 지 원하는 언어의 목록을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc8ba-105">This example uses the [MSDN/TechNet Publishing System (MTPS) Content Service](http://go.microsoft.com/fwlink/?LinkId=95677) to retrieve the list of languages supported by a specified document.</span></span>  
  
 <span data-ttu-id="dc8ba-106">웹 서비스를 호출 하기 전에 그에 대 한 참조 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc8ba-106">Before you call a Web service, you need to create a reference to it.</span></span> <span data-ttu-id="dc8ba-107">사용 하 여 MTPS 서비스에 대 한 웹 참조를 만들려면 [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)], 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc8ba-107">To create a Web reference to the MTPS service using [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)], follow the following steps:</span></span>  
  
1.  <span data-ttu-id="dc8ba-108">프로젝트를 열고 [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="dc8ba-108">Open your project in [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)].</span></span>  
  
2.  <span data-ttu-id="dc8ba-109">**프로젝트** 메뉴를 클릭 하 여 **웹 참조 추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="dc8ba-109">From the **Project** menu, click **Add Web Reference**.</span></span>  
  
3.  <span data-ttu-id="dc8ba-110">대화 상자에서 설정 된 **URL** 를 [http://services.msdn.microsoft.com/contentservices/contentservice.asmx?wsdl](http://services.msdn.microsoft.com/contentservices/contentservice.asmx?wsdl)합니다.</span><span class="sxs-lookup"><span data-stu-id="dc8ba-110">In the dialog box, set the **URL** to [http://services.msdn.microsoft.com/contentservices/contentservice.asmx?wsdl](http://services.msdn.microsoft.com/contentservices/contentservice.asmx?wsdl).</span></span>  
  
4.  <span data-ttu-id="dc8ba-111">키를 눌러 **이동** 차례로 **참조 추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="dc8ba-111">Press **Go** and then **Add Reference**.</span></span>  
  
 <span data-ttu-id="dc8ba-112">웹 서비스 메서드를 호출 하는 다음으로 설정 하 고는 <xref:System.Windows.FrameworkElement.DataContext%2A> 적절 한 컨트롤 또는 반환된 된 개체에는 창입니다.</span><span class="sxs-lookup"><span data-stu-id="dc8ba-112">Next, you call the Web service method and set the <xref:System.Windows.FrameworkElement.DataContext%2A> of the appropriate control or window to the returned object.</span></span> <span data-ttu-id="dc8ba-113">**GetContent** MTPS 서비스의 메서드 사용에 대 한 참조는 **getContentRequest** 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="dc8ba-113">The **GetContent** method of the MTPS service takes a reference to the **getContentRequest** object.</span></span> <span data-ttu-id="dc8ba-114">따라서 다음 예제에서는 먼저 요청 개체를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="dc8ba-114">Therefore, the following example first sets up a request object:</span></span>  
  
 [!code-csharp[BindToWebService#Namespace](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindToWebService/CSharp/Window1.xaml.cs#namespace)]
 [!code-vb[BindToWebService#Namespace](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BindToWebService/VisualBasic/Window1.xaml.vb#namespace)]  
[!code-csharp[BindToWebService#WebServiceCall](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindToWebService/CSharp/Window1.xaml.cs#webservicecall)]
[!code-vb[BindToWebService#WebServiceCall](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BindToWebService/VisualBasic/Window1.xaml.vb#webservicecall)]  
  
 <span data-ttu-id="dc8ba-115">후의 <xref:System.Windows.FrameworkElement.DataContext%2A> 하는 개체의 속성에 대 한 바인딩을 만들 수 있습니다 설정 된는 <xref:System.Windows.FrameworkElement.DataContext%2A> 으로 설정 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="dc8ba-115">After the <xref:System.Windows.FrameworkElement.DataContext%2A> has been set, you can create bindings to the properties of the object that the <xref:System.Windows.FrameworkElement.DataContext%2A> has been set to.</span></span> <span data-ttu-id="dc8ba-116">이 예제에서는 <xref:System.Windows.FrameworkElement.DataContext%2A> 로 설정 되는 **getContentResponse** 에서 반환 된 개체는 **GetContent** 메서드.</span><span class="sxs-lookup"><span data-stu-id="dc8ba-116">In this example, the <xref:System.Windows.FrameworkElement.DataContext%2A> is set to the **getContentResponse** object returned by the **GetContent** method.</span></span> <span data-ttu-id="dc8ba-117">다음 예제에서는 <xref:System.Windows.Controls.ItemsControl> 을 바인딩하고 표시는 **로캘** 값의 **availableVersionsAndLocales** 의 **getContentResponse**합니다.</span><span class="sxs-lookup"><span data-stu-id="dc8ba-117">In the following example, the <xref:System.Windows.Controls.ItemsControl> binds to and displays the **locale** values of **availableVersionsAndLocales** of **getContentResponse**.</span></span>  
  
 [!code-xaml[BindToWebService#Binding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindToWebService/CSharp/Window1.xaml#binding)]  
  
 <span data-ttu-id="dc8ba-118">구조에 대 한 내용은 **getContentResponse**, 참조 [콘텐츠 서비스 설명서](http://services.msdn.microsoft.com/ContentServices/ContentService.asmx)합니다.</span><span class="sxs-lookup"><span data-stu-id="dc8ba-118">For information about the structure of **getContentResponse**, see [Content Service documentation](http://services.msdn.microsoft.com/ContentServices/ContentService.asmx).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc8ba-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dc8ba-119">See Also</span></span>  
 [<span data-ttu-id="dc8ba-120">데이터 바인딩 개요</span><span class="sxs-lookup"><span data-stu-id="dc8ba-120">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="dc8ba-121">바인딩 소스 개요</span><span class="sxs-lookup"><span data-stu-id="dc8ba-121">Binding Sources Overview</span></span>](../../../../docs/framework/wpf/data/binding-sources-overview.md)  
 [<span data-ttu-id="dc8ba-122">XAML의 바인딩에 사용할 수 있는 데이터 만들기</span><span class="sxs-lookup"><span data-stu-id="dc8ba-122">Make Data Available for Binding in XAML</span></span>](../../../../docs/framework/wpf/data/how-to-make-data-available-for-binding-in-xaml.md)
