---
title: "방법: 표시기 구현"
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
helpviewer_keywords: adorners [WPF], implementing
ms.assetid: 56ae32b6-0599-455c-b52f-2ff97e6f1ec2
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 76bceae5b69fad4c217127617309484edcf18108
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-implement-an-adorner"></a><span data-ttu-id="a2352-102">방법: 표시기 구현</span><span class="sxs-lookup"><span data-stu-id="a2352-102">How to: Implement an Adorner</span></span>
<span data-ttu-id="a2352-103">이 예제에는 최소한의 표시기 구현을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a2352-103">This example shows a minimal adorner implementation.</span></span>  
  
## <a name="notes-for-implementers"></a><span data-ttu-id="a2352-104">구현자 참고 사항</span><span class="sxs-lookup"><span data-stu-id="a2352-104">Notes for Implementers</span></span>  
 <span data-ttu-id="a2352-105">표시기에는 고유 렌더링 동작이 포함되어 있지 않음에 유의해야 합니다. 표시기를 렌더링하는 것은 표시기 구현자의 책임입니다.</span><span class="sxs-lookup"><span data-stu-id="a2352-105">It is important to note that adorners do not include any inherent rendering behavior; ensuring that an adorner renders is the responsibility of the adorner implementer.</span></span>   <span data-ttu-id="a2352-106">렌더링 동작을 구현할 일반적으로 재정의 하는 <xref:System.Windows.UIElement.OnRender%2A> 메서드 및 사용법 하나 이상의 <xref:System.Windows.Media.DrawingContext> 개체 (이 예제 에서처럼) 필요에 따라 표시기의 시각적 요소를 렌더링 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2352-106">A common way of implementing rendering behavior is to override the <xref:System.Windows.UIElement.OnRender%2A> method and use one or more <xref:System.Windows.Media.DrawingContext> objects to render the adorner's visuals as needed (as shown in this example).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a2352-107">예</span><span class="sxs-lookup"><span data-stu-id="a2352-107">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="a2352-108">설명</span><span class="sxs-lookup"><span data-stu-id="a2352-108">Description</span></span>  
 <span data-ttu-id="a2352-109">추상에서 상속 되는 클래스를 구현 하 여 사용자 지정 표시기 만들어집니다 <xref:System.Windows.Documents.Adorner> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="a2352-109">A custom adorner is created by implementing a class that inherits from the abstract <xref:System.Windows.Documents.Adorner> class.</span></span>  <span data-ttu-id="a2352-110">예제에서는 표시기의 모서리를 간단히 보여는 <xref:System.Windows.UIElement> 재정의 하 여 원으로 <xref:System.Windows.UIElement.OnRender%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="a2352-110">The example adorner simply adorns the corners of a <xref:System.Windows.UIElement> with circles by overriding the <xref:System.Windows.UIElement.OnRender%2A> method.</span></span>  
  
### <a name="code"></a><span data-ttu-id="a2352-111">코드</span><span class="sxs-lookup"><span data-stu-id="a2352-111">Code</span></span>  
 [!code-csharp[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_simplecircleadornerbody)]
 [!code-vb[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_simplecircleadornerbody)]  
  
## <a name="see-also"></a><span data-ttu-id="a2352-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a2352-112">See Also</span></span>  
 [<span data-ttu-id="a2352-113">표시기 개요</span><span class="sxs-lookup"><span data-stu-id="a2352-113">Adorners Overview</span></span>](../../../../docs/framework/wpf/controls/adorners-overview.md)
