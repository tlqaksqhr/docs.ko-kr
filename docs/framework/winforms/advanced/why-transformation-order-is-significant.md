---
title: "변형 순서의 중요성"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- transformations [Windows Forms], order signficance
ms.assetid: 37d5f9dc-a5cf-4475-aa5d-34d714e808a9
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: cd3363a1afb8658ed3bb27359259cb752464507d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="why-transformation-order-is-significant"></a><span data-ttu-id="8204f-102">변형 순서의 중요성</span><span class="sxs-lookup"><span data-stu-id="8204f-102">Why Transformation Order Is Significant</span></span>
<span data-ttu-id="8204f-103">단일 <xref:System.Drawing.Drawing2D.Matrix> 개체는 단일 변환 또는 일련의 변환 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8204f-103">A single <xref:System.Drawing.Drawing2D.Matrix> object can store a single transformation or a sequence of transformations.</span></span> <span data-ttu-id="8204f-104">후자 보다 복합 변환을 이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="8204f-104">The latter is called a composite transformation.</span></span> <span data-ttu-id="8204f-105">복합 변환 매트릭스 개별 변환 행렬을 곱하여 구합니다.</span><span class="sxs-lookup"><span data-stu-id="8204f-105">The matrix of a composite transformation is obtained by multiplying the matrices of individual transformations.</span></span>  
  
## <a name="composite-transform-examples"></a><span data-ttu-id="8204f-106">복합 변환 예제</span><span class="sxs-lookup"><span data-stu-id="8204f-106">Composite Transform Examples</span></span>  
 <span data-ttu-id="8204f-107">복합 변환에서 개별 변환의 순서가 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="8204f-107">In a composite transformation, the order of individual transformations is important.</span></span> <span data-ttu-id="8204f-108">예를 들어 하면 먼저 회전, 크기 조정을 차례로 변환, 메시지가 다른 결과 보다 먼저 변환 하는 경우 다음 회전 다음 크기를 조정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8204f-108">For example, if you first rotate, then scale, then translate, you get a different result than if you first translate, then rotate, then scale.</span></span> <span data-ttu-id="8204f-109">[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], 합성 변형 왼쪽에서 오른쪽에 빌드됩니다.</span><span class="sxs-lookup"><span data-stu-id="8204f-109">In [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], composite transformations are built from left to right.</span></span> <span data-ttu-id="8204f-110">S, R, 및 T 크기 조정, 회전 및 변환 행렬을 각각은, 한 다음 제품 SRT 순서에 따라 해당 복합 변환 매트릭스 해당 첫 번째 눈금, 다음 회전 경우 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="8204f-110">If S, R, and T are scale, rotation, and translation matrices respectively, then the product SRT (in that order) is the matrix of the composite transformation that first scales, then rotates, then translates.</span></span> <span data-ttu-id="8204f-111">제품에 의해 생성 되는 매트릭스 SRT는 TR 제품에 의해 생성 되는 매트릭스와에서 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="8204f-111">The matrix produced by the product SRT is different from the matrix produced by the product TRS.</span></span>  
  
 <span data-ttu-id="8204f-112">순서는 중요 한 가지 이유는 회전 및 배율 조정 같은 변환 좌표계의 원점을 기준으로 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8204f-112">One reason order is significant is that transformations like rotation and scaling are done with respect to the origin of the coordinate system.</span></span> <span data-ttu-id="8204f-113">원본에서 멀리 이동 된 개체를 확장 합니다. 결과 서로 다르게 생성 중심이 원점 하는 개체 크기를 조정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8204f-113">Scaling an object that is centered at the origin produces a different result than scaling an object that has been moved away from the origin.</span></span> <span data-ttu-id="8204f-114">마찬가지로, 중심이 원점 있는 개체를 회전 원본에서 멀리 이동 된 개체를 회전 다른 결과 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="8204f-114">Similarly, rotating an object that is centered at the origin produces a different result than rotating an object that has been moved away from the origin.</span></span>  
  
 <span data-ttu-id="8204f-115">다음 예제에서는 크기 조정, 회전, 순서 대로) (에서 이동 하는 복합 변환을 결합 합니다.</span><span class="sxs-lookup"><span data-stu-id="8204f-115">The following example combines scaling, rotation and translation (in that order) to form a composite transformation.</span></span> <span data-ttu-id="8204f-116">인수 <xref:System.Drawing.Drawing2D.MatrixOrder.Append> 에 전달 되는 <xref:System.Drawing.Graphics.RotateTransform%2A> 메서드 크기 조정을 회전을 따를 것을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8204f-116">The argument <xref:System.Drawing.Drawing2D.MatrixOrder.Append> passed to the <xref:System.Drawing.Graphics.RotateTransform%2A> method indicates that the rotation will follow the scaling.</span></span> <span data-ttu-id="8204f-117">마찬가지로, 인수 <xref:System.Drawing.Drawing2D.MatrixOrder.Append> 에 전달 되는 <xref:System.Drawing.Graphics.TranslateTransform%2A> 메서드 변환 회전을 따를 것을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8204f-117">Likewise, the argument <xref:System.Drawing.Drawing2D.MatrixOrder.Append> passed to the <xref:System.Drawing.Graphics.TranslateTransform%2A> method indicates that the translation will follow the rotation.</span></span> <span data-ttu-id="8204f-118"><xref:System.Drawing.Drawing2D.MatrixOrder.Append>및 <xref:System.Drawing.Drawing2D.MatrixOrder.Prepend> 의 구성원은 <xref:System.Drawing.Drawing2D.MatrixOrder> 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="8204f-118"><xref:System.Drawing.Drawing2D.MatrixOrder.Append> and <xref:System.Drawing.Drawing2D.MatrixOrder.Prepend> are members of the <xref:System.Drawing.Drawing2D.MatrixOrder> enumeration.</span></span>  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.MiscLegacyTopics#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#21)]  
  
 <span data-ttu-id="8204f-119">다음 예에서는 앞의 예제와 동일한 메서드를 호출 하지만 호출 하 여 순서가 반대로 바뀌었습니다.</span><span class="sxs-lookup"><span data-stu-id="8204f-119">The following example makes the same method calls as the preceding example, but the order of the calls is reversed.</span></span> <span data-ttu-id="8204f-120">작업의 결과 순서 회전, 첫 번째 눈금 보다에서 매우 다른 결과 생성 하 눈금 회전, 차례로 번역 먼저 변환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8204f-120">The resulting order of operations is first translate, then rotate, then scale, which produces a very different result than first scale, then rotate, then translate.</span></span>  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#22)]
 [!code-vb[System.Drawing.MiscLegacyTopics#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#22)]  
  
 <span data-ttu-id="8204f-121">복합 변환에서 개별 변환의 순서를 반대로 바꾸려면 가지 방법은 메서드 호출의 시퀀스의 순서를 반대로 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8204f-121">One way to reverse the order of individual transformations in a composite transformation is to reverse the order of a sequence of method calls.</span></span> <span data-ttu-id="8204f-122">작업의 순서를 제어 하는 두 번째 방법은 행렬 order 인수를 변경 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8204f-122">A second way to control the order of operations is to change the matrix order argument.</span></span> <span data-ttu-id="8204f-123">다음 예제는 점을 제외 하 고 앞의 예제와 동일 <xref:System.Drawing.Drawing2D.MatrixOrder.Append> 로 변경 되었습니다 <xref:System.Drawing.Drawing2D.MatrixOrder.Prepend>합니다.</span><span class="sxs-lookup"><span data-stu-id="8204f-123">The following example is the same as the preceding example, except that <xref:System.Drawing.Drawing2D.MatrixOrder.Append> has been changed to <xref:System.Drawing.Drawing2D.MatrixOrder.Prepend>.</span></span> <span data-ttu-id="8204f-124">행렬 곱 SRT, 여기서 S, R, T는 회전, 크기 조정에 대 한 행렬 이며 곱은 순서로 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8204f-124">The matrix multiplication is done in the order SRT, where S, R, and T are the matrices for scale, rotate, and translate, respectively.</span></span> <span data-ttu-id="8204f-125">복합 변환의 순서는 첫 번째 눈금 회전 차례로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="8204f-125">The order of the composite transformation is first scale, then rotate, then translate.</span></span>  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#23)]
 [!code-vb[System.Drawing.MiscLegacyTopics#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#23)]  
  
 <span data-ttu-id="8204f-126">바로 위 예의 결과이 항목의 첫 번째 예의 결과로는 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="8204f-126">The result of the immediately preceding example is the same as the result of the first example in this topic.</span></span> <span data-ttu-id="8204f-127">메서드 호출의 순서와 행렬 곱하기의 순서를 둘 다 바꾸었기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="8204f-127">This is because we reversed both the order of the method calls and the order of the matrix multiplication.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8204f-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8204f-128">See Also</span></span>  
 <xref:System.Drawing.Drawing2D.Matrix>  
 [<span data-ttu-id="8204f-129">좌표계 및 변형</span><span class="sxs-lookup"><span data-stu-id="8204f-129">Coordinate Systems and Transformations</span></span>](../../../../docs/framework/winforms/advanced/coordinate-systems-and-transformations.md)  
 [<span data-ttu-id="8204f-130">관리 GDI+에서 변형 사용</span><span class="sxs-lookup"><span data-stu-id="8204f-130">Using Transformations in Managed GDI+</span></span>](../../../../docs/framework/winforms/advanced/using-transformations-in-managed-gdi.md)
