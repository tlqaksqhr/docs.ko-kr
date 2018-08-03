---
title: Model-View-View Model과 함께 이식 가능한 클래스 라이브러리 사용
ms.date: 07/18/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Portable Class Library [.NET Framework], and MVVM
- MVVM, and Portable Class Library
ms.assetid: 41a0b9f8-15a2-431a-bc35-e310b2953b03
author: mairaw
ms.author: mairaw
ms.openlocfilehash: aa8423c5c9453a9edb1058f0d5bdf4c494ece088
ms.sourcegitcommit: e8dc507cfdaad504fc9d4c83d28d24569dcef91c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/03/2018
ms.locfileid: "33574110"
---
# <a name="using-portable-class-library-with-model-view-view-model"></a><span data-ttu-id="52e80-102">Model-View-View Model과 함께 이식 가능한 클래스 라이브러리 사용</span><span class="sxs-lookup"><span data-stu-id="52e80-102">Using Portable Class Library with Model-View-View Model</span></span>
<span data-ttu-id="52e80-103">.NET Framework를 사용 하 여 [이식 가능한 클래스 라이브러리](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md) 모델-뷰 모델 (MVVM) 패턴을 구현 하 여 여러 플랫폼 간에 어셈블리를 공유 합니다.</span><span class="sxs-lookup"><span data-stu-id="52e80-103">You can use the .NET Framework [Portable Class Library](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md) to implement the Model-View-View Model (MVVM) pattern and share assemblies across multiple platforms.</span></span>  

[!INCLUDE[standard](../../../includes/pcl-to-standard.md)]

 <span data-ttu-id="52e80-104">MVVM은 내부 비즈니스 논리에서 사용자 인터페이스를 분리하는 응용 프로그램 패턴입니다.</span><span class="sxs-lookup"><span data-stu-id="52e80-104">MVVM is an application pattern that isolates the user interface from the underlying business logic.</span></span> <span data-ttu-id="52e80-105">[!INCLUDE[net_portable](../../../includes/net-portable-md.md)]의 [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)] 프로젝트에서 모델을 구현하고 모델 클래스를 본 다음, 여러 플랫폼을 위해 사용자 지정된 뷰를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52e80-105">You can implement the model and view model classes in a [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] project in [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], and then create views that are customized for different platforms.</span></span> <span data-ttu-id="52e80-106">이 접근 방식을 사용하면 한 번만 데이터 모델과 비즈니스 논리를 작성하고, 다음 설명에서와 같이 .NET Framework, Silverlight, Windows Phone 및 [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] 응용 프로그램의 해당 코드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52e80-106">This approach enables you to write the data model and business logic only once, and use that code from .NET Framework, Silverlight, Windows Phone, and [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] apps, as shown in the following illustration.</span></span>  
  
 <span data-ttu-id="52e80-107">![MVVM 다이어그램으로 이식 가능한](../../../docs/standard/cross-platform/media/portablemvvmdiagram.png "PortableMVVMdiagram")</span><span class="sxs-lookup"><span data-stu-id="52e80-107">![Portable with MVVM diagram](../../../docs/standard/cross-platform/media/portablemvvmdiagram.png "PortableMVVMdiagram")</span></span>  
  
 <span data-ttu-id="52e80-108">이 항목에서는 MVVM 패턴에 대 한 일반 정보를 제공 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="52e80-108">This topic does not provide general information about the MVVM pattern.</span></span> <span data-ttu-id="52e80-109">만 사용 하는 방법에 대 한 정보를 제공 [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] MVVM을 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="52e80-109">It only provides information about how to use [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] to implement MVVM.</span></span> <span data-ttu-id="52e80-110">MVVM에 대 한 자세한 내용은 참조는 [MVVM 퀵 스타트](https://msdn.microsoft.com/library/gg430869(v=PandP.40).aspx)합니다.</span><span class="sxs-lookup"><span data-stu-id="52e80-110">For more information about MVVM, see the [MVVM Quickstart](https://msdn.microsoft.com/library/gg430869(v=PandP.40).aspx).</span></span>  
  
## <a name="classes-that-support-mvvm"></a><span data-ttu-id="52e80-111">MVVM을 지 원하는 클래스</span><span class="sxs-lookup"><span data-stu-id="52e80-111">Classes That Support MVVM</span></span>  
 <span data-ttu-id="52e80-112">대상 하는 경우는 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)], Silverlight 또는 Windows Phone 7.5에 대 한 프로그램 [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] 프로젝트에 다음 클래스는 MVVM 패턴을 구현 하기 위한 사용할 수 있습니다:</span><span class="sxs-lookup"><span data-stu-id="52e80-112">When you target the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)], Silverlight, or Windows Phone 7.5 for your [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] project, the following classes are available for implementing the MVVM pattern:</span></span>  
  
-   <span data-ttu-id="52e80-113"><xref:System.Collections.ObjectModel.ObservableCollection%601?displayProperty=nameWithType> 클래스</span><span class="sxs-lookup"><span data-stu-id="52e80-113"><xref:System.Collections.ObjectModel.ObservableCollection%601?displayProperty=nameWithType> class</span></span>  
  
-   <span data-ttu-id="52e80-114"><xref:System.Collections.ObjectModel.ReadOnlyObservableCollection%601?displayProperty=nameWithType> 클래스</span><span class="sxs-lookup"><span data-stu-id="52e80-114"><xref:System.Collections.ObjectModel.ReadOnlyObservableCollection%601?displayProperty=nameWithType> class</span></span>  
  
-   <span data-ttu-id="52e80-115"><xref:System.Collections.Specialized.INotifyCollectionChanged?displayProperty=nameWithType> 클래스</span><span class="sxs-lookup"><span data-stu-id="52e80-115"><xref:System.Collections.Specialized.INotifyCollectionChanged?displayProperty=nameWithType> class</span></span>  
  
-   <span data-ttu-id="52e80-116"><xref:System.Collections.Specialized.NotifyCollectionChangedAction?displayProperty=nameWithType> 클래스</span><span class="sxs-lookup"><span data-stu-id="52e80-116"><xref:System.Collections.Specialized.NotifyCollectionChangedAction?displayProperty=nameWithType> class</span></span>  
  
-   <span data-ttu-id="52e80-117"><xref:System.Collections.Specialized.NotifyCollectionChangedEventArgs?displayProperty=nameWithType> 클래스</span><span class="sxs-lookup"><span data-stu-id="52e80-117"><xref:System.Collections.Specialized.NotifyCollectionChangedEventArgs?displayProperty=nameWithType> class</span></span>  
  
-   <span data-ttu-id="52e80-118"><xref:System.Collections.Specialized.NotifyCollectionChangedEventHandler?displayProperty=nameWithType> 클래스</span><span class="sxs-lookup"><span data-stu-id="52e80-118"><xref:System.Collections.Specialized.NotifyCollectionChangedEventHandler?displayProperty=nameWithType> class</span></span>  
  
-   <span data-ttu-id="52e80-119"><xref:System.ComponentModel.DataErrorsChangedEventArgs?displayProperty=nameWithType> 클래스</span><span class="sxs-lookup"><span data-stu-id="52e80-119"><xref:System.ComponentModel.DataErrorsChangedEventArgs?displayProperty=nameWithType> class</span></span>  
  
-   <span data-ttu-id="52e80-120"><xref:System.ComponentModel.INotifyDataErrorInfo?displayProperty=nameWithType> 클래스</span><span class="sxs-lookup"><span data-stu-id="52e80-120"><xref:System.ComponentModel.INotifyDataErrorInfo?displayProperty=nameWithType> class</span></span>  
  
-   <span data-ttu-id="52e80-121"><xref:System.ComponentModel.INotifyPropertyChanged?displayProperty=nameWithType> 클래스</span><span class="sxs-lookup"><span data-stu-id="52e80-121"><xref:System.ComponentModel.INotifyPropertyChanged?displayProperty=nameWithType> class</span></span>  
  
-   <span data-ttu-id="52e80-122"><xref:System.Windows.Input.ICommand?displayProperty=nameWithType> 클래스</span><span class="sxs-lookup"><span data-stu-id="52e80-122"><xref:System.Windows.Input.ICommand?displayProperty=nameWithType> class</span></span>  
  
-   <span data-ttu-id="52e80-123">모든 클래스는 <xref:System.ComponentModel.DataAnnotations?displayProperty=nameWithType> 네임 스페이스</span><span class="sxs-lookup"><span data-stu-id="52e80-123">All classes in the <xref:System.ComponentModel.DataAnnotations?displayProperty=nameWithType> namespace</span></span>  
  
## <a name="implementing-mvvm"></a><span data-ttu-id="52e80-124">MVVM을 구현</span><span class="sxs-lookup"><span data-stu-id="52e80-124">Implementing MVVM</span></span>  
 <span data-ttu-id="52e80-125">MVVM을 구현 하려면 일반적으로 만든 모델과 뷰 모델을 [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] 때문에 프로젝트를 [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] 프로젝트 이식 가능 프로젝트를 참조할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="52e80-125">To implement MVVM, you typically create both the model and the view model in a [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] project, because a [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] project cannot reference a non-portable project.</span></span> <span data-ttu-id="52e80-126">동일한 프로젝트에서 또는 별도 프로젝트에서 모델 및 뷰 모델을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52e80-126">The model and view model can be in the same project or in separate projects.</span></span> <span data-ttu-id="52e80-127">별도 프로젝트를 사용 하는 경우 모델 프로젝트에 뷰 모델 프로젝트에서 참조를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="52e80-127">If you use separate projects, add a reference from the view model project to the model project.</span></span>  
  
 <span data-ttu-id="52e80-128">모델을 컴파일하여 모델 프로젝트를 확인 한 후 뷰가 포함 된 앱에서 해당 어셈블리를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="52e80-128">After you compile the model and view model projects, you reference those assemblies in the app that contains the view.</span></span> <span data-ttu-id="52e80-129">뷰는 뷰 모델만 상호 작용을 하는 경우 뷰 모델이 포함 된 어셈블리를 참조 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="52e80-129">If the view interacts only with the view model, you only have to reference the assembly that contains the view model.</span></span>  
  
### <a name="model"></a><span data-ttu-id="52e80-130">모델</span><span class="sxs-lookup"><span data-stu-id="52e80-130">Model</span></span>  
 <span data-ttu-id="52e80-131">다음 예제에서는 수에 있는 간단한 모델 클래스는 [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] 프로젝트입니다.</span><span class="sxs-lookup"><span data-stu-id="52e80-131">The following example shows a simplified model class that could reside in a [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] project.</span></span>  
  
 [!code-csharp[PortableClassLibraryMVVM#1](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/customer.cs#1)]
 [!code-vb[PortableClassLibraryMVVM#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customer.vb#1)]  
  
 <span data-ttu-id="52e80-132">다음 예에서는 채우기, 검색 및 데이터를 업데이트 하는 간단한 방법을 보여 줍니다는 [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] 프로젝트입니다.</span><span class="sxs-lookup"><span data-stu-id="52e80-132">The following example shows a simple way to populate, retrieve, and update the data in a [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] project.</span></span> <span data-ttu-id="52e80-133">실제 앱에서는 Windows Communication Foundation (WCF) 서비스와 같은 원본에서 데이터를 검색할 됩니다.</span><span class="sxs-lookup"><span data-stu-id="52e80-133">In a real app, you would retrieve the data from a source such as a Windows Communication Foundation (WCF) service.</span></span>  
  
 [!code-csharp[PortableClassLibraryMVVM#2](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/customerrepository.cs#2)]
 [!code-vb[PortableClassLibraryMVVM#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customerrepository.vb#2)]  
  
### <a name="view-model"></a><span data-ttu-id="52e80-134">뷰 모델</span><span class="sxs-lookup"><span data-stu-id="52e80-134">View Model</span></span>  
 <span data-ttu-id="52e80-135">보기 모델에 대 한 기본 클래스는 MVVM 패턴을 구현 하는 경우에 자주 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="52e80-135">A base class for view models is frequently added when implementing the MVVM pattern.</span></span> <span data-ttu-id="52e80-136">다음 예제에서는 기본 클래스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="52e80-136">The following example shows a base class.</span></span>  
  
 [!code-csharp[PortableClassLibraryMVVM#3](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/viewmodelbase.cs#3)]
 [!code-vb[PortableClassLibraryMVVM#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/viewmodelbase.vb#3)]  
  
 <span data-ttu-id="52e80-137">구현 된 <xref:System.Windows.Input.ICommand> 인터페이스 MVVM 패턴을 사용 하 여 자주 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="52e80-137">An implementation of the <xref:System.Windows.Input.ICommand> interface is frequently used with the MVVM pattern.</span></span> <span data-ttu-id="52e80-138">다음 예제에서는 <xref:System.Windows.Input.ICommand> 인터페이스의 구현을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="52e80-138">The following example shows an implementation of the <xref:System.Windows.Input.ICommand> interface.</span></span>  
  
 [!code-csharp[PortableClassLibraryMVVM#4](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/relaycommand.cs#4)]
 [!code-vb[PortableClassLibraryMVVM#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/relaycommand.vb#4)]  
  
 <span data-ttu-id="52e80-139">다음 예제에서는 단순화 된 보기 모델을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="52e80-139">The following example shows a simplified view model.</span></span>  
  
 [!code-csharp[PortableClassLibraryMVVM#5](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/mainpageviewmodel.cs#5)]
 [!code-vb[PortableClassLibraryMVVM#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customerviewmodel.vb#5)]  
  
### <a name="view"></a><span data-ttu-id="52e80-140">보기</span><span class="sxs-lookup"><span data-stu-id="52e80-140">View</span></span>  
 <span data-ttu-id="52e80-141">[!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 앱 [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] 앱, Silverlight 기반 앱 또는 Windows Phone 7.5 앱, 모델과 뷰 모델 프로젝트를 포함 하는 어셈블리를 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52e80-141">From a [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] app, [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] app, Silverlight-based app, or Windows Phone 7.5 app, you can reference the assembly that contains the model and view model projects.</span></span>  <span data-ttu-id="52e80-142">그런 다음 뷰 모델을 사용 하 여 상호 작용 하는 뷰를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="52e80-142">You then create a view that interacts with the view model.</span></span> <span data-ttu-id="52e80-143">다음 예제에서는 검색 및 보기 모델의 데이터를에서 업데이트 하는 간단한 Windows Presentation Foundation (WPF) 앱을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="52e80-143">The following example shows a simplified Windows Presentation Foundation (WPF) app that retrieves and updates data from the view model.</span></span> <span data-ttu-id="52e80-144">Windows Phone Silverlight에서 유사한 뷰를 만들 수 있습니다 또는 [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] 앱.</span><span class="sxs-lookup"><span data-stu-id="52e80-144">You could create similar views in Silverlight, Windows Phone, or [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] apps.</span></span>  
  
 [!code-xaml[PortableClassLibraryMVVM#6](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/mainwindow.xaml#6)]  
  
## <a name="see-also"></a><span data-ttu-id="52e80-145">참고 항목</span><span class="sxs-lookup"><span data-stu-id="52e80-145">See Also</span></span>  
 [<span data-ttu-id="52e80-146">이식 가능한 클래스 라이브러리</span><span class="sxs-lookup"><span data-stu-id="52e80-146">Portable Class Library</span></span>](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md)
