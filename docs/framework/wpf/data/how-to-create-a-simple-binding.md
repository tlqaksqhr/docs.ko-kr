---
title: "방법: 단순 바인딩 만들기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- simple binding [WPF], creating
- data binding [WPF], creating simple bindings
- binding data [WPF], creating
ms.assetid: 69b80f72-6259-44cb-8294-5bdcebca1e08
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a61844f917539f5d5e7c99299c8a33f4aa18450f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-simple-binding"></a><span data-ttu-id="981d6-102">방법: 단순 바인딩 만들기</span><span class="sxs-lookup"><span data-stu-id="981d6-102">How to: Create a Simple Binding</span></span>
<span data-ttu-id="981d6-103">이 예제에서는 간단한을 만드는 방법을 보여 줍니다. <xref:System.Windows.Data.Binding>합니다.</span><span class="sxs-lookup"><span data-stu-id="981d6-103">This example shows you how to create a simple <xref:System.Windows.Data.Binding>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="981d6-104">예제</span><span class="sxs-lookup"><span data-stu-id="981d6-104">Example</span></span>  
 <span data-ttu-id="981d6-105">이 예에서 한는 `Person` 라는 문자열 속성이 있는 개체 `PersonName`합니다.</span><span class="sxs-lookup"><span data-stu-id="981d6-105">In this example, you have a `Person` object with a string property named `PersonName`.</span></span> <span data-ttu-id="981d6-106">`Person` 개체가 라는 네임 스페이스에 정의 된 `SDKSample`합니다.</span><span class="sxs-lookup"><span data-stu-id="981d6-106">The `Person` object is defined in the namespace called `SDKSample`.</span></span>  
  
 <span data-ttu-id="981d6-107">다음 예제는 `Person` 개체는 `PersonName` 속성 값이 `Joe`합니다.</span><span class="sxs-lookup"><span data-stu-id="981d6-107">The following example instantiates the `Person` object with a `PersonName` property value of `Joe`.</span></span> <span data-ttu-id="981d6-108">이 작업은 `Resources` 섹션 및 할당 된 `x:Key`합니다.</span><span class="sxs-lookup"><span data-stu-id="981d6-108">This is done in the `Resources` section and assigned an `x:Key`.</span></span>  
  
 [!code-xaml[SimpleBinding#Instantiation](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#instantiation)]  
[!code-xaml[SimpleBinding#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#2)]  
[!code-xaml[SimpleBinding#EndWindow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#endwindow)]  
  
 <span data-ttu-id="981d6-109">바인딩할는 `PersonName` 속성 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="981d6-109">To bind to the `PersonName` property you would do the following:</span></span>  
  
 [!code-xaml[SimpleBinding#BDO1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#bdo1)]  
  
 <span data-ttu-id="981d6-110">결과적으로 <xref:System.Windows.Controls.TextBlock> "Joe" 값으로 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="981d6-110">As a result, the <xref:System.Windows.Controls.TextBlock> appears with the value "Joe".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="981d6-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="981d6-111">See Also</span></span>  
 [<span data-ttu-id="981d6-112">데이터 바인딩 개요</span><span class="sxs-lookup"><span data-stu-id="981d6-112">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="981d6-113">방법 항목</span><span class="sxs-lookup"><span data-stu-id="981d6-113">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
