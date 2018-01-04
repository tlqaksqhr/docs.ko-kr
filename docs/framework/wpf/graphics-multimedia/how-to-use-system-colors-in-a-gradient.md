---
title: "방법: 그라데이션에 시스템 색 사용"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- gradients [WPF], system colors in
- system colors in gradients [WPF]
ms.assetid: 11942e7e-6300-4b50-8ed1-f50e8d20e7d2
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: acf0f2c63e0b176f28d611183aab1abecc8f1678
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-system-colors-in-a-gradient"></a><span data-ttu-id="a51a6-102">방법: 그라데이션에 시스템 색 사용</span><span class="sxs-lookup"><span data-stu-id="a51a6-102">How to: Use System Colors in a Gradient</span></span>
<span data-ttu-id="a51a6-103">그라데이션에서 시스템 색을 사용 하려면 사용는  *\<SystemColor >*색 및  *\<SystemColor >*ColorKey의 정적 속성은 <xref:System.Windows.SystemColors> 얻으려고 클래스는 표시 되는 색에 대 한 참조를  *\<SystemColor >* 시스템 색의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="a51a6-103">To use a system color in a gradient, you use the *\<SystemColor>*Color and *\<SystemColor>*ColorKey static properties of the <xref:System.Windows.SystemColors> class to obtain a reference to the color, where *\<SystemColor>* is the name of the desired system color.</span></span> <span data-ttu-id="a51a6-104">사용 하 여는  *\<SystemColor >*자동 시스템 테마 변경 내용으로 업데이트 하는 동적 참조를 만들려는 ColorKey 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="a51a6-104">Use the *\<SystemColor>*ColorKey properties when you want to create a dynamic reference that updates automatically as the system theme changes.</span></span> <span data-ttu-id="a51a6-105">그렇지 않은 경우 사용 된  *\<SystemColor >*색 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="a51a6-105">Otherwise, use the *\<SystemColor>*Color properties.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a51a6-106">예</span><span class="sxs-lookup"><span data-stu-id="a51a6-106">Example</span></span>  
 <span data-ttu-id="a51a6-107">다음 예제에서는 동적 시스템 색 리소스를 사용하여 그라데이션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a51a6-107">The following example uses dynamic system color resources to create a gradient.</span></span>  
  
 [!code-xaml[brushsamples_snip#GraphicsMMDynamicSystemColorGradientExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/DynamicSystemColorExample.xaml#graphicsmmdynamicsystemcolorgradientexamplewholepage)]  
  
 <span data-ttu-id="a51a6-108">그 다음 예제에서는 정적 시스템 색 리소스를 사용하여 그라데이션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a51a6-108">The next example uses static system color resources to create a gradient.</span></span>  
  
 [!code-xaml[brushsamples_snip#GraphicsMMStaticSystemColorGradientExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/StaticSystemColorExample.xaml#graphicsmmstaticsystemcolorgradientexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="a51a6-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a51a6-109">See Also</span></span>  
 <xref:System.Windows.SystemColors>  
 [<span data-ttu-id="a51a6-110">시스템 브러시로 영역 그리기</span><span class="sxs-lookup"><span data-stu-id="a51a6-110">Paint an Area with a System Brush</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)  
 [<span data-ttu-id="a51a6-111">단색 및 그라데이션을 사용한 그리기 개요</span><span class="sxs-lookup"><span data-stu-id="a51a6-111">Painting with Solid Colors and Gradients Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)
