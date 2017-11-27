---
title: "방법: 응용 프로그램 범위 리소스 사전 사용"
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
- dictionaries [WPF], resource
- resource dictionaries [WPF], application-scope
- application-scope resource dictionaries
ms.assetid: 53857682-bd2c-4f2c-8f25-1307d0b451a2
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 417fea4dcbb5a8d0a27f9605be19de5921aaf0ed
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-an-application-scope-resource-dictionary"></a><span data-ttu-id="12287-102">방법: 응용 프로그램 범위 리소스 사전 사용</span><span class="sxs-lookup"><span data-stu-id="12287-102">How to: Use an Application-Scope Resource Dictionary</span></span>
<span data-ttu-id="12287-103">이 예제에서는 응용 프로그램 범위 사용자 지정 리소스 사전을 정의하고 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="12287-103">This example shows how to define and use an application-scope custom resource dictionary.</span></span>  
  
## <a name="example"></a><span data-ttu-id="12287-104">예제</span><span class="sxs-lookup"><span data-stu-id="12287-104">Example</span></span>  
 <span data-ttu-id="12287-105"><xref:System.Windows.Application>공유 리소스에 대 한 응용 프로그램 범위 저장소는 노출: <xref:System.Windows.Application.Resources%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="12287-105"><xref:System.Windows.Application> exposes an application-scope store for shared resources: <xref:System.Windows.Application.Resources%2A>.</span></span> <span data-ttu-id="12287-106">기본적으로는 <xref:System.Windows.Application.Resources%2A> 의 인스턴스로 속성은 초기화는 <xref:System.Windows.ResourceDictionary> 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="12287-106">By default, the <xref:System.Windows.Application.Resources%2A> property is initialized with an instance of the <xref:System.Windows.ResourceDictionary> type.</span></span> <span data-ttu-id="12287-107">이 인스턴스를 사용 하 여 가져오고 사용 하 여 응용 프로그램 범위의 속성을 설정할 때 <xref:System.Windows.Application.Resources%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="12287-107">You use this instance when you get and set application-scope properties using <xref:System.Windows.Application.Resources%2A>.</span></span> <span data-ttu-id="12287-108">자세한 내용은 참조 [하는 방법: 가져오기 및 설정 응용 프로그램 범위 리소스](http://msdn.microsoft.com/en-us/39e0420c-c9fc-47dc-8956-fdd95b214095)합니다.</span><span class="sxs-lookup"><span data-stu-id="12287-108">For more information, see [How to: Get and Set an Application-Scope Resource](http://msdn.microsoft.com/en-us/39e0420c-c9fc-47dc-8956-fdd95b214095).</span></span>
  
 <span data-ttu-id="12287-109">여러 리소스를 사용 하 여 설정한 경우 <xref:System.Windows.Application.Resources%2A>, 사용자 지정 리소스 사전을 해당 리소스를 저장 하 고 설정 하려면 대신 사용할 수 있습니다 <xref:System.Windows.Application.Resources%2A> 된 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="12287-109">If you have multiple resources that you set using <xref:System.Windows.Application.Resources%2A>, you can instead use a custom resource dictionary to store those resources and set <xref:System.Windows.Application.Resources%2A> with it instead.</span></span> <span data-ttu-id="12287-110">다음 XAML을 사용 하 여 사용자 지정 리소스 사전을 선언 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="12287-110">The following shows how you declare a custom resource dictionary using XAML.</span></span>
  
 [!code-xaml[HOWTOResourceDictionaries#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MyResourceDictionary.xaml#1)]  
  
 <span data-ttu-id="12287-111">전체 리소스 사전을 사용 하 여 교환 <xref:System.Windows.Application.Resources%2A> 테마 마다 단일 리소스 사전에서 캡슐화 되어 있는 응용 프로그램 범위 테마가 지원 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12287-111">Swapping entire resource dictionaries using <xref:System.Windows.Application.Resources%2A> allows you to support application-scope themes, where each theme is encapsulated by a single resource dictionary.</span></span> <span data-ttu-id="12287-112">다음 예제에서는 <xref:System.Windows.ResourceDictionary>를 설정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="12287-112">The following example shows how to set the <xref:System.Windows.ResourceDictionary>.</span></span>  
  
 [!code-xaml[HOWTOResourceDictionaries#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/App.xaml#2)]  
  
 <span data-ttu-id="12287-113">다음에 의해 노출 리소스 사전에서 응용 프로그램 범위 리소스를 가져오는 방법을 보여 줍니다. <xref:System.Windows.Application.Resources%2A> XAML에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="12287-113">The following shows how you can get application-scope resources from the resource dictionary exposed by <xref:System.Windows.Application.Resources%2A> in XAML.</span></span>  
  
 [!code-xaml[HOWTOResourceDictionaries#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MainWindow.xaml#4)]  
  
 <span data-ttu-id="12287-114">다음 예제에서는 코드에서 리소스를 가져오는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="12287-114">The following shows how you can also get the resources in code.</span></span>  
  
 [!code-csharp[HOWTOResourceDictionaries#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MainWindow.xaml.cs#3)]
 [!code-vb[HOWTOResourceDictionaries#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToResourceDictionaries/VB/MainWindow.xaml.vb#3)]  
  
 <span data-ttu-id="12287-115">사용 하는 경우를 확인 하려면 두 가지 고려 사항을 <xref:System.Windows.Application.Resources%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="12287-115">There are two considerations to make when using <xref:System.Windows.Application.Resources%2A>.</span></span> <span data-ttu-id="12287-116">먼저, 사전 *키* 은 개체를 설정 하 고 속성 값을 가져올 경우 정확히 동일한 개체 인스턴스를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="12287-116">First, the dictionary *key* is an object, so you must use exactly the same object instance when both setting and getting a property value.</span></span> <span data-ttu-id="12287-117">문자열을 사용할 경우 키는 대/소문자를 구분해야 합니다. 두 번째, 사전 *값* 가 속성 값을 가져올 때 값을 원하는 형식으로 변환 해야 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="12287-117">(Note that the key is case-sensitive when using a string.) Second, the dictionary *value* is an object, so you will have to convert the value to the desired type when getting a property value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12287-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="12287-118">See Also</span></span>  
 <xref:System.Windows.ResourceDictionary>  
 <xref:System.Windows.Application.Resources%2A>  
 [<span data-ttu-id="12287-119">XAML 리소스</span><span class="sxs-lookup"><span data-stu-id="12287-119">XAML Resources</span></span>](../../../../docs/framework/wpf/advanced/xaml-resources.md)  
 [<span data-ttu-id="12287-120">병합된 리소스 사전</span><span class="sxs-lookup"><span data-stu-id="12287-120">Merged Resource Dictionaries</span></span>](../../../../docs/framework/wpf/advanced/merged-resource-dictionaries.md)
