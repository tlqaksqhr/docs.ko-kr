---
title: "방법: Point4D 구조체가 서로 같은지 및 다른지 여부 테스트"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- inequality [WPF], testing Point4D structures for
- equality [WPF], testing Point4D structures for
- testing [WPF], Point4D structures for equality
- Point4D structures [WPF], testing for inequality
- testing [WPF], Point4D structures for inequality
- Point4D structures [WPF], testing for equality
ms.assetid: e004a67e-db7f-4af8-a31f-e6b2a44ccf34
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ac69ec232485ebd3097f2db3b31d3fd43d0ccc99
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-test-point4d-structures-for-equality-and-inequality"></a><span data-ttu-id="ccbf9-102">방법: Point4D 구조체가 서로 같은지 및 다른지 여부 테스트</span><span class="sxs-lookup"><span data-stu-id="ccbf9-102">How to: Test Point4D structures for equality and inequality</span></span>
<span data-ttu-id="ccbf9-103">테스트 하는 방법을 보여 주는이 예제 <xref:System.Windows.Media.Media3D.Point4D> 같음과 다름을 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="ccbf9-103">This example shows how to test <xref:System.Windows.Media.Media3D.Point4D> structures for equality and inequality.</span></span>  
  
 <span data-ttu-id="ccbf9-104">다음 코드를 테스트 하는 방법을 보여 줍니다 <xref:System.Windows.Media.Media3D.Point4D> 같음 및 같지 않음을 사용 하 여에 대 한 구조는 <xref:System.Windows.Media.Media3D.Point4D> 같음 메서드.</span><span class="sxs-lookup"><span data-stu-id="ccbf9-104">The following code illustrates how to test <xref:System.Windows.Media.Media3D.Point4D> structures for equality and inequality using the <xref:System.Windows.Media.Media3D.Point4D> equality methods.</span></span>  <span data-ttu-id="ccbf9-105"><xref:System.Windows.Media.Media3D.Point4D> 구조를 오버 로드 된 같음을 사용 하 여 같음 여부 테스트 (`==`) 연산자 오버 로드 된 같지 않은지를 사용 하 여 다른 지에 대 한 다음 (`!=`) 연산자를 마지막으로 <xref:System.Windows.Media.Media3D.Point3D> 구조와 <xref:System.Windows.Media.Media3D.Point4D> 구조 정적을 사용 하 여 같은지 확인 <xref:System.Windows.Media.Media3D.Point4D.Equals%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="ccbf9-105">The <xref:System.Windows.Media.Media3D.Point4D> structures are tested for equality using the overloaded equality (`==`) operator, then for inequality using the overloaded inequality (`!=`) operator, and finally a <xref:System.Windows.Media.Media3D.Point3D> structure and a <xref:System.Windows.Media.Media3D.Point4D> structure are checked for equality using the static <xref:System.Windows.Media.Media3D.Point4D.Equals%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ccbf9-106">예</span><span class="sxs-lookup"><span data-stu-id="ccbf9-106">Example</span></span>  
 [!code-csharp[3DGallery_procedural_snip#Point4DEqualityExample_csharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/Misc3DOperationsExample.cs#point4dequalityexample_csharp)]  
  
## <a name="see-also"></a><span data-ttu-id="ccbf9-107">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ccbf9-107">See Also</span></span>  
 <xref:System.Windows.Media.Media3D.Point4D.op_Equality%2A>  
 <xref:System.Windows.Media.Media3D.Point4D.op_Inequality%2A>  
 <xref:System.Windows.Media.Media3D.Point4D.Equals%2A>
