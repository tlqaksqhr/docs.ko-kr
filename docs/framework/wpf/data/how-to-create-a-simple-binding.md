---
title: '방법: 단순 바인딩 만들기'
ms.date: 03/30/2017
helpviewer_keywords:
- simple binding [WPF], creating
- data binding [WPF], creating simple bindings
- binding data [WPF], creating
ms.assetid: 69b80f72-6259-44cb-8294-5bdcebca1e08
ms.openlocfilehash: 8910dd3ec6c9f72f9d8fb64cd33912f0d4318e5f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33555021"
---
# <a name="how-to-create-a-simple-binding"></a><span data-ttu-id="81588-102">방법: 단순 바인딩 만들기</span><span class="sxs-lookup"><span data-stu-id="81588-102">How to: Create a Simple Binding</span></span>
<span data-ttu-id="81588-103">이 예제에서는 간단한을 만드는 방법을 보여 줍니다. <xref:System.Windows.Data.Binding>합니다.</span><span class="sxs-lookup"><span data-stu-id="81588-103">This example shows you how to create a simple <xref:System.Windows.Data.Binding>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="81588-104">예제</span><span class="sxs-lookup"><span data-stu-id="81588-104">Example</span></span>  
 <span data-ttu-id="81588-105">이 예에서 한는 `Person` 라는 문자열 속성이 있는 개체 `PersonName`합니다.</span><span class="sxs-lookup"><span data-stu-id="81588-105">In this example, you have a `Person` object with a string property named `PersonName`.</span></span> <span data-ttu-id="81588-106">`Person` 개체가 라는 네임 스페이스에 정의 된 `SDKSample`합니다.</span><span class="sxs-lookup"><span data-stu-id="81588-106">The `Person` object is defined in the namespace called `SDKSample`.</span></span>  
  
 <span data-ttu-id="81588-107">포함 하는 강조 표시 된 줄의 `<src>` 다음 예제에서 요소를 인스턴스화하는 `Person` 개체는 `PersonName` 속성 값이 `Joe`합니다.</span><span class="sxs-lookup"><span data-stu-id="81588-107">The highlighted line that contains the `<src>` element in the following example instantiates the `Person` object with a `PersonName` property value of `Joe`.</span></span> <span data-ttu-id="81588-108">이 작업은 `Resources` 섹션 및 할당 된 `x:Key`합니다.</span><span class="sxs-lookup"><span data-stu-id="81588-108">This is done in the `Resources` section and assigned an `x:Key`.</span></span>  
  
 [!code-xaml[SimpleBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml?highlight=9,37)]  
  
 <span data-ttu-id="81588-109">포함 하는 강조 표시 된 줄의 `<TextBlock>` 요소 다음 바인딩합니다는 <xref:System.Windows.Controls.TextBlock> 컨트롤을 `PersonName` 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="81588-109">The highlighted line that contains the `<TextBlock>` element then binds the <xref:System.Windows.Controls.TextBlock> control to the `PersonName` property.</span></span> <span data-ttu-id="81588-110">결과적으로 <xref:System.Windows.Controls.TextBlock> "Joe" 값으로 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="81588-110">As a result, the <xref:System.Windows.Controls.TextBlock> appears with the value "Joe".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81588-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="81588-111">See Also</span></span>  
 [<span data-ttu-id="81588-112">데이터 바인딩 개요</span><span class="sxs-lookup"><span data-stu-id="81588-112">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="81588-113">방법 항목</span><span class="sxs-lookup"><span data-stu-id="81588-113">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
