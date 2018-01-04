---
title: "방법: 바인딩된 항목 목록을 기반으로 값 산출"
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
- data binding [WPF], MultiBinding
- Multibinding [WPF]
ms.assetid: b3d06378-b511-4181-95aa-316d60c9229b
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c3987690a1acb180ee22fa02e399accd9c5d481d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-produce-a-value-based-on-a-list-of-bound-items"></a><span data-ttu-id="c5975-102">방법: 바인딩된 항목 목록을 기반으로 값 산출</span><span class="sxs-lookup"><span data-stu-id="c5975-102">How to: Produce a Value Based on a List of Bound Items</span></span>
<span data-ttu-id="c5975-103"><xref:System.Windows.Data.MultiBinding>바인딩 대상 속성 원본 속성의 목록에 바인딩하고 다음 지정 된 입력을 지 원하는 값을 생성 하는 논리를 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5975-103"><xref:System.Windows.Data.MultiBinding> allows you to bind a binding target property to a list of source properties and then apply logic to produce a value with the given inputs.</span></span> <span data-ttu-id="c5975-104">사용 하는 방법을 보여 주는이 예제 <xref:System.Windows.Data.MultiBinding>합니다.</span><span class="sxs-lookup"><span data-stu-id="c5975-104">This example demonstrates how to use <xref:System.Windows.Data.MultiBinding>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c5975-105">예</span><span class="sxs-lookup"><span data-stu-id="c5975-105">Example</span></span>  
 <span data-ttu-id="c5975-106">다음 예제에서 `NameListData`은 `firstName`과 `lastName` 두 개의 속성을 포함하는 `PersonName` 개체의 컬렉션을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="c5975-106">In the following example, `NameListData` refers to a collection of `PersonName` objects, which are objects that contain two properties, `firstName` and `lastName`.</span></span> <span data-ttu-id="c5975-107">다음 예제에서는 생성 한 <xref:System.Windows.Controls.TextBlock> 성 가진 사람 성과 이름을 보여 주는 첫 번째입니다.</span><span class="sxs-lookup"><span data-stu-id="c5975-107">The following example produces a <xref:System.Windows.Controls.TextBlock> that shows the first and last names of a person with the last name first.</span></span>  
  
 [!code-xaml[MultiBinding#Resources1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#resources1)]  
[!code-xaml[MultiBinding#Resources2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#resources2)]  
[!code-xaml[MultiBinding#MultiBindingTextBox2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#multibindingtextbox2)]  
[!code-xaml[MultiBinding#Window](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#window)]  
  
 <span data-ttu-id="c5975-108">성이 먼저 표시되는 형식이 생성되는 방법을 이해하기 위해 `NameConverter`의 구현을 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="c5975-108">To understand how the last-name-first format is produced, let's take a look at the implementation of the `NameConverter`:</span></span>  
  
 [!code-csharp[MultiBinding#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/NameConverter.cs#3)]
 [!code-vb[MultiBinding#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MultiBinding/VisualBasic/NameConverter.vb#3)]  
  
 <span data-ttu-id="c5975-109">`NameConverter`는 <xref:System.Windows.Data.IMultiValueConverter> 인터페이스를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="c5975-109">`NameConverter` implements the <xref:System.Windows.Data.IMultiValueConverter> interface.</span></span> <span data-ttu-id="c5975-110">`NameConverter`은 개별 바인딩에서 값을 가져오고 값 개체 배열에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="c5975-110">`NameConverter` takes the values from the individual bindings and stores them in the values object array.</span></span> <span data-ttu-id="c5975-111">되는 순서는 <xref:System.Windows.Data.Binding> 요소 아래에 표시 된 <xref:System.Windows.Data.MultiBinding> 요소는 해당 값이 배열에 저장 되는 순서입니다.</span><span class="sxs-lookup"><span data-stu-id="c5975-111">The order in which the <xref:System.Windows.Data.Binding> elements appear under the <xref:System.Windows.Data.MultiBinding> element is the order in which those values are stored in the array.</span></span> <span data-ttu-id="c5975-112">값은 <xref:System.Windows.Data.MultiBinding.ConverterParameter%2A> 의 매개 변수 인수에 의해 참조는 <xref:System.Windows.Data.MultiBinding.Converter%2A> 메서드로 매개 변수에 이름의 서식을 지정 하는 방법을 결정 하는 스위치를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5975-112">The value of the <xref:System.Windows.Data.MultiBinding.ConverterParameter%2A> attribute is referenced by the parameter argument of the <xref:System.Windows.Data.MultiBinding.Converter%2A> method, which performs a switch on the parameter to determine how to format the name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5975-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c5975-113">See Also</span></span>  
 [<span data-ttu-id="c5975-114">바인딩된 데이터 변환</span><span class="sxs-lookup"><span data-stu-id="c5975-114">Convert Bound Data</span></span>](../../../../docs/framework/wpf/data/how-to-convert-bound-data.md)  
 [<span data-ttu-id="c5975-115">데이터 바인딩 개요</span><span class="sxs-lookup"><span data-stu-id="c5975-115">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="c5975-116">방법 항목</span><span class="sxs-lookup"><span data-stu-id="c5975-116">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
