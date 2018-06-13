---
title: '방법: 색 매트릭스를 사용하여 단색으로 변형'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- image colors [Windows Forms], transforming
- color matrices [Windows Forms], using
ms.assetid: 44df4556-a433-49c0-ac0f-9a12063a5860
ms.openlocfilehash: 741259fcf853c82dfd13b43edc92e50d8767887b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33527406"
---
# <a name="how-to-use-a-color-matrix-to-transform-a-single-color"></a><span data-ttu-id="3db8d-102">방법: 색 매트릭스를 사용하여 단색으로 변형</span><span class="sxs-lookup"><span data-stu-id="3db8d-102">How to: Use a Color Matrix to Transform a Single Color</span></span>
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="3db8d-103"> 제공 된 <xref:System.Drawing.Image> 및 <xref:System.Drawing.Bitmap> 저장 및 이미지 조작을 위한 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="3db8d-103"> provides the <xref:System.Drawing.Image> and <xref:System.Drawing.Bitmap> classes for storing and manipulating images.</span></span> <span data-ttu-id="3db8d-104"><xref:System.Drawing.Image> 및 <xref:System.Drawing.Bitmap> 개체는 32 비트 숫자 각 픽셀의 색을 저장 합니다: 각각 빨강, 녹색, 파랑 및 알파에 8 비트입니다.</span><span class="sxs-lookup"><span data-stu-id="3db8d-104"><xref:System.Drawing.Image> and <xref:System.Drawing.Bitmap> objects store the color of each pixel as a 32-bit number: 8 bits each for red, green, blue, and alpha.</span></span> <span data-ttu-id="3db8d-105">네 개의 구성 요소가 0부터 농도가 없음을 나타내고 255 전체 강도 나타내는 0부터 255 까지의 숫자입니다.</span><span class="sxs-lookup"><span data-stu-id="3db8d-105">Each of the four components is a number from 0 through 255, with 0 representing no intensity and 255 representing full intensity.</span></span> <span data-ttu-id="3db8d-106">알파 구성 요소는 색상의 투명도 지정 합니다.: 0은 완전히 투명 하며, 255은 완전히 불투명 합니다.</span><span class="sxs-lookup"><span data-stu-id="3db8d-106">The alpha component specifies the transparency of the color: 0 is fully transparent, and 255 is fully opaque.</span></span>  
  
 <span data-ttu-id="3db8d-107">색 벡터 (빨강, 녹색, 파란색, alpha) 형태의 4-튜플 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3db8d-107">A color vector is a 4-tuple of the form (red, green, blue, alpha).</span></span> <span data-ttu-id="3db8d-108">예를 들어 색 벡터 (0, 255, 0, 255) 빨강 및 파랑 하지만 농도가 녹색 불투명 한 색을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3db8d-108">For example, the color vector (0, 255, 0, 255) represents an opaque color that has no red or blue, but has green at full intensity.</span></span>  
  
 <span data-ttu-id="3db8d-109">색을 표시 하는 다른 규칙 전체 강도 대 한 숫자 1을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3db8d-109">Another convention for representing colors uses the number 1 for full intensity.</span></span> <span data-ttu-id="3db8d-110">이 규칙을 사용 하 여 이전 단락에 설명 된 색을 표시 벡터 (0, 1, 0, 1).</span><span class="sxs-lookup"><span data-stu-id="3db8d-110">Using that convention, the color described in the preceding paragraph would be represented by the vector (0, 1, 0, 1).</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="3db8d-111"> 색을 변환할 때 전체 강도으로 1의 규칙을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3db8d-111"> uses the convention of 1 as full intensity when it performs color transformations.</span></span>  
  
 <span data-ttu-id="3db8d-112">4x4 매트릭스 색 벡터를 곱하여 색 벡터 선형 변환 (예: 회전, 배율 및 like)을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3db8d-112">You can apply linear transformations (rotation, scaling, and the like) to color vectors by multiplying the color vectors by a 4×4 matrix.</span></span> <span data-ttu-id="3db8d-113">그러나는 비선형 변환을 수행 하는 4x4 매트릭스를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3db8d-113">However, you cannot use a 4×4 matrix to perform a translation (nonlinear).</span></span> <span data-ttu-id="3db8d-114">색 벡터의 각 더미 다섯 번째 좌표 (예를 들어 번호 1)를 추가 하는 경우에 선형 변환 및 번역의 조합을 적용할 5 × 5 매트릭스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3db8d-114">If you add a dummy fifth coordinate (for example, the number 1) to each of the color vectors, you can use a 5×5 matrix to apply any combination of linear transformations and translations.</span></span> <span data-ttu-id="3db8d-115">번역 나옵니다 선형 변환으로 구성 된 변환에는 3x3 유사 변환을 이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="3db8d-115">A transformation consisting of a linear transformation followed by a translation is called an affine transformation.</span></span>  
  
 <span data-ttu-id="3db8d-116">예를 들어 색 (0.2, 0.0, 0.4, 1.0)로 시작 하 고 다음과 같은 변환을 적용 하려는 있다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3db8d-116">For example, suppose you want to start with the color (0.2, 0.0, 0.4, 1.0) and apply the following transformations:</span></span>  
  
1.  <span data-ttu-id="3db8d-117">Double 빨강 구성 요소</span><span class="sxs-lookup"><span data-stu-id="3db8d-117">Double the red component</span></span>  
  
2.  <span data-ttu-id="3db8d-118">0.2 빨강, 녹색 및 파랑 구성 요소에 추가</span><span class="sxs-lookup"><span data-stu-id="3db8d-118">Add 0.2 to the red, green, and blue components</span></span>  
  
 <span data-ttu-id="3db8d-119">다음 매트릭스 곱 나열 된 순서로 변환이 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="3db8d-119">The following matrix multiplication will perform the pair of transformations in the order listed.</span></span>  
  
 <span data-ttu-id="3db8d-120">![다시 칠하기](../../../../docs/framework/winforms/advanced/media/recoloring01.gif "recoloring01")</span><span class="sxs-lookup"><span data-stu-id="3db8d-120">![Recoloring](../../../../docs/framework/winforms/advanced/media/recoloring01.gif "recoloring01")</span></span>  
  
 <span data-ttu-id="3db8d-121">색 매트릭스의 요소는 행과 열으로 (0부터 시작) 인덱싱됩니다.</span><span class="sxs-lookup"><span data-stu-id="3db8d-121">The elements of a color matrix are indexed (zero-based) by row and then column.</span></span> <span data-ttu-id="3db8d-122">예를 들어 다섯 번째 행과 M 행렬의 세 번째 열에 있는 항목은 M [2] [4]로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3db8d-122">For example, the entry in the fifth row and third column of matrix M is denoted by M[4][2].</span></span>  
  
 <span data-ttu-id="3db8d-123">(다음 그림에 표시) 5 × 5 항등 매트릭스 대각선 1 및 0으로 다른 곳에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3db8d-123">The 5×5 identity matrix (shown in the following illustration) has 1s on the diagonal and 0s everywhere else.</span></span> <span data-ttu-id="3db8d-124">색 벡터 항등 매트릭스를 곱하면 색 벡터 변경 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3db8d-124">If you multiply a color vector by the identity matrix, the color vector does not change.</span></span> <span data-ttu-id="3db8d-125">색 변환 매트릭스를 형성 하는 편리한 방법은 항등 매트릭스로 시작 하 고 원하는 변환에서 생성 하는 약간만 변경 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="3db8d-125">A convenient way to form the matrix of a color transformation is to start with the identity matrix and make a small change that produces the desired transformation.</span></span>  
  
 <span data-ttu-id="3db8d-126">![다시 칠하기](../../../../docs/framework/winforms/advanced/media/recoloring02.gif "recoloring02")</span><span class="sxs-lookup"><span data-stu-id="3db8d-126">![Recoloring](../../../../docs/framework/winforms/advanced/media/recoloring02.gif "recoloring02")</span></span>  
  
 <span data-ttu-id="3db8d-127">행렬 및 변환의 자세한 논의 알려면 [좌표계 및 변형](../../../../docs/framework/winforms/advanced/coordinate-systems-and-transformations.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3db8d-127">For a more detailed discussion of matrices and transformations, see [Coordinate Systems and Transformations](../../../../docs/framework/winforms/advanced/coordinate-systems-and-transformations.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3db8d-128">예제</span><span class="sxs-lookup"><span data-stu-id="3db8d-128">Example</span></span>  
 <span data-ttu-id="3db8d-129">다음 예제에서는 모두 한 가지 색상 (0.2, 0.0, 0.4, 1.0) 및 이전 단락에 설명 된 변환을 적용 하는 이미지입니다.</span><span class="sxs-lookup"><span data-stu-id="3db8d-129">The following example takes an image that is all one color (0.2, 0.0, 0.4, 1.0) and applies the transformation described in the preceding paragraphs.</span></span>  
  
 <span data-ttu-id="3db8d-130">다음 그림에서는 오른쪽에서 왼쪽의 원래 이미지 및 변형 된 이미지를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3db8d-130">The following illustration shows the original image on the left and the transformed image on the right.</span></span>  
  
 <span data-ttu-id="3db8d-131">![색](../../../../docs/framework/winforms/advanced/media/colortrans1.png "colortrans1")</span><span class="sxs-lookup"><span data-stu-id="3db8d-131">![Colors](../../../../docs/framework/winforms/advanced/media/colortrans1.png "colortrans1")</span></span>  
  
 <span data-ttu-id="3db8d-132">다음 예제에서 코드는 다음 단계를 사용 하 여 다시 칠하기는 수행:</span><span class="sxs-lookup"><span data-stu-id="3db8d-132">The code in the following example uses the following steps to perform the recoloring:</span></span>  
  
1.  <span data-ttu-id="3db8d-133">초기화는 <xref:System.Drawing.Imaging.ColorMatrix> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="3db8d-133">Initialize a <xref:System.Drawing.Imaging.ColorMatrix> object.</span></span>  
  
2.  <span data-ttu-id="3db8d-134">만들기는 <xref:System.Drawing.Imaging.ImageAttributes> 개체를 전달는 <xref:System.Drawing.Imaging.ColorMatrix> 개체는 <xref:System.Drawing.Imaging.ImageAttributes.SetColorMatrix%2A> 의 메서드는 <xref:System.Drawing.Imaging.ImageAttributes> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="3db8d-134">Create an <xref:System.Drawing.Imaging.ImageAttributes> object and pass the <xref:System.Drawing.Imaging.ColorMatrix> object to the <xref:System.Drawing.Imaging.ImageAttributes.SetColorMatrix%2A> method of the <xref:System.Drawing.Imaging.ImageAttributes> object.</span></span>  
  
3.  <span data-ttu-id="3db8d-135">전달 된 <xref:System.Drawing.Imaging.ImageAttributes> 개체를 <xref:System.Drawing.Graphics.DrawImage%2A> 의 메서드는 <xref:System.Drawing.Graphics> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="3db8d-135">Pass the <xref:System.Drawing.Imaging.ImageAttributes> object to the <xref:System.Drawing.Graphics.DrawImage%2A> method of a <xref:System.Drawing.Graphics> object.</span></span>  
  
 [!code-csharp[System.Drawing.RecoloringImages#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.RecoloringImages#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="3db8d-136">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="3db8d-136">Compiling the Code</span></span>  
 <span data-ttu-id="3db8d-137">앞의 예제는 Windows forms에서 사용하도록 설계되었으며 <xref:System.Windows.Forms.Control.Paint> 이벤트 처리기의 매개 변수인 <xref:System.Windows.Forms.PaintEventArgs> `e`가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="3db8d-137">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3db8d-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3db8d-138">See Also</span></span>  
 [<span data-ttu-id="3db8d-139">이미지 다시 칠하기</span><span class="sxs-lookup"><span data-stu-id="3db8d-139">Recoloring Images</span></span>](../../../../docs/framework/winforms/advanced/recoloring-images.md)  
 [<span data-ttu-id="3db8d-140">좌표계 및 변형</span><span class="sxs-lookup"><span data-stu-id="3db8d-140">Coordinate Systems and Transformations</span></span>](../../../../docs/framework/winforms/advanced/coordinate-systems-and-transformations.md)
