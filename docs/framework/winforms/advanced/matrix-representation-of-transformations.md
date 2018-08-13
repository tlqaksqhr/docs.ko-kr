---
title: 매트릭스에 의한 변형 표시
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- composite transformations
- transformations [Windows Forms], linear
- matrices
- translations in matrix representation
- transformations [Windows Forms], composite
- vectors
- linear transformations
- transformations [Windows Forms], matrix representation of
- transformations [Windows Forms], translation
- affine transformations
ms.assetid: 0659fe00-9e0c-41c4-9118-016f2404c905
ms.openlocfilehash: 4c840d8a5abc89493bc684526ce76d34307f4ba1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33527286"
---
# <a name="matrix-representation-of-transformations"></a><span data-ttu-id="eb541-102">매트릭스에 의한 변형 표시</span><span class="sxs-lookup"><span data-stu-id="eb541-102">Matrix Representation of Transformations</span></span>
<span data-ttu-id="eb541-103">m × n 행렬은 행 m과 n 개의 열으로 정렬 하는 숫자 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="eb541-103">An m×n matrix is a set of numbers arranged in m rows and n columns.</span></span> <span data-ttu-id="eb541-104">다음 그림에서는 몇 가지 매트릭스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="eb541-104">The following illustration shows several matrices.</span></span>  
  
 <span data-ttu-id="eb541-105">![변환](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art04.gif "AboutGdip05_art04")</span><span class="sxs-lookup"><span data-stu-id="eb541-105">![Transformations](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art04.gif "AboutGdip05_art04")</span></span>  
  
 <span data-ttu-id="eb541-106">개별 요소를 추가 하 여 동일한 크기의 두 행렬을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb541-106">You can add two matrices of the same size by adding individual elements.</span></span> <span data-ttu-id="eb541-107">다음은 매트릭스 더하기는 두 가지 예입니다.</span><span class="sxs-lookup"><span data-stu-id="eb541-107">The following illustration shows two examples of matrix addition.</span></span>  
  
 <span data-ttu-id="eb541-108">![변환](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art05.gif "AboutGdip05_art05")</span><span class="sxs-lookup"><span data-stu-id="eb541-108">![Transformations](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art05.gif "AboutGdip05_art05")</span></span>  
  
 <span data-ttu-id="eb541-109">결과 m × p 매트릭스를 m × n 매트릭스 n × p 매트릭스는 곱하고 수 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb541-109">An m×n matrix can be multiplied by an n×p matrix, and the result is an m×p matrix.</span></span> <span data-ttu-id="eb541-110">첫 번째 행렬의 열 수가 두 번째 행렬의 행 수와 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb541-110">The number of columns in the first matrix must be the same as the number of rows in the second matrix.</span></span> <span data-ttu-id="eb541-111">예를 들어 4 × 2 매트릭스 4 × 3 매트릭스를 생성 하기 위해 2 × 3 매트릭스를 곱한 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb541-111">For example, a 4×2 matrix can be multiplied by a 2×3 matrix to produce a 4×3 matrix.</span></span>  
  
 <span data-ttu-id="eb541-112">행렬의 열 및 행 평면에서 점 벡터도 생각할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb541-112">Points in the plane and rows and columns of a matrix can be thought of as vectors.</span></span> <span data-ttu-id="eb541-113">예를 들어, (2, 5)는 두 가지 구성 요소를 사용 하 여 벡터 및 (3, 7, 1) 세 요소로 구성 된 벡터입니다.</span><span class="sxs-lookup"><span data-stu-id="eb541-113">For example, (2, 5) is a vector with two components, and (3, 7, 1) is a vector with three components.</span></span> <span data-ttu-id="eb541-114">두 벡터의 내적을 다음과 같이 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb541-114">The dot product of two vectors is defined as follows:</span></span>  
  
 <span data-ttu-id="eb541-115">(a, b) \* (c, d) = ac + bd</span><span class="sxs-lookup"><span data-stu-id="eb541-115">(a, b) • (c, d) = ac + bd</span></span>  
  
 <span data-ttu-id="eb541-116">(a, b, c) (d, e, f) \* + = ad + cf</span><span class="sxs-lookup"><span data-stu-id="eb541-116">(a, b, c) • (d, e, f) = ad + be + cf</span></span>  
  
 <span data-ttu-id="eb541-117">예를 들어 내적 (2, 3) 및 (5, 4)는 (2)(5) + (3)(4) = 22입니다.</span><span class="sxs-lookup"><span data-stu-id="eb541-117">For example, the dot product of (2, 3) and (5, 4) is (2)(5) + (3)(4) = 22.</span></span> <span data-ttu-id="eb541-118">(2, 5, 1)의 내적 및 (4, 3, 1)은 (2)(4) + (5)(3) + (1)(1) = 24입니다.</span><span class="sxs-lookup"><span data-stu-id="eb541-118">The dot product of (2, 5, 1) and (4, 3, 1) is (2)(4) + (5)(3) + (1)(1) = 24.</span></span> <span data-ttu-id="eb541-119">참고 두 벡터의 내적은 숫자를 다른 벡터입니다.</span><span class="sxs-lookup"><span data-stu-id="eb541-119">Note that the dot product of two vectors is a number, not another vector.</span></span> <span data-ttu-id="eb541-120">또한 참고가 두 벡터 동일한 구성 요소 수를 포함 하는 경우에 내적을 계산할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb541-120">Also note that you can calculate the dot product only if the two vectors have the same number of components.</span></span>  
  
 <span data-ttu-id="eb541-121">Let A(i, j) i 번째 행과 열에 있는 엔트리입니다 매트릭스 A에에서 있는 항목 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb541-121">Let A(i, j) be the entry in matrix A in the ith row and the jth column.</span></span> <span data-ttu-id="eb541-122">예를 들어 A (3, 2)는 세 번째 행과 두 번째 열에는 행렬에 대 한 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="eb541-122">For example A(3, 2) is the entry in matrix A in the 3rd row and the 2nd column.</span></span> <span data-ttu-id="eb541-123">A, B 및 C는 행렬 및 AB 가정가 됩니다. C의 항목은 다음과 같이 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb541-123">Suppose A, B, and C are matrices, and AB = C. The entries of C are calculated as follows:</span></span>  
  
 <span data-ttu-id="eb541-124">C (i, j) = (i/A 행) • (B 열의 j)</span><span class="sxs-lookup"><span data-stu-id="eb541-124">C(i, j) = (row i of A) • (column j of B)</span></span>  
  
 <span data-ttu-id="eb541-125">다음은 매트릭스 곱의 몇 가지 예입니다.</span><span class="sxs-lookup"><span data-stu-id="eb541-125">The following illustration shows several examples of matrix multiplication.</span></span>  
  
 <span data-ttu-id="eb541-126">![변환](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art06.gif "AboutGdip05_art06")</span><span class="sxs-lookup"><span data-stu-id="eb541-126">![Transformations](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art06.gif "AboutGdip05_art06")</span></span>  
  
 <span data-ttu-id="eb541-127">1 × 2 행렬으로 평면에 있는 점의 생각 되 면 해당 지점 2 × 2 매트릭스를 곱하여 변형할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb541-127">If you think of a point in a plane as a 1×2 matrix, you can transform that point by multiplying it by a 2×2 matrix.</span></span> <span data-ttu-id="eb541-128">다음 그림에서는 점 (2, 1)에 적용 하는 몇몇 변환이 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="eb541-128">The following illustration shows several transformations applied to the point (2, 1).</span></span>  
  
 <span data-ttu-id="eb541-129">![변환](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art07.gif "AboutGdip05_art07")</span><span class="sxs-lookup"><span data-stu-id="eb541-129">![Transformations](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art07.gif "AboutGdip05_art07")</span></span>  
  
 <span data-ttu-id="eb541-130">위 그림에 나타난 모두 선형 변환 하십시오.</span><span class="sxs-lookup"><span data-stu-id="eb541-130">All of the transformations shown in the preceding figure are linear transformations.</span></span> <span data-ttu-id="eb541-131">같은 다른 변환은 특정 선형이 아니므로 하 고 2 × 2 매트릭스 곱으로 표현 될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="eb541-131">Certain other transformations, such as translation, are not linear, and cannot be expressed as multiplication by a 2×2 matrix.</span></span> <span data-ttu-id="eb541-132">한다고 가정 시작 하 여 점 (2, 1), 90도 회전, x 방향의 3 단위 및 4 단위 y 방향으로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb541-132">Suppose you want to start with the point (2, 1), rotate it 90 degrees, translate it 3 units in the x direction, and translate it 4 units in the y direction.</span></span> <span data-ttu-id="eb541-133">뒤에 여는 행렬 곱하기를 사용 하 여이 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb541-133">You can accomplish this by using a matrix multiplication followed by a matrix addition.</span></span>  
  
 <span data-ttu-id="eb541-134">![변환](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art08.gif "AboutGdip05_art08")</span><span class="sxs-lookup"><span data-stu-id="eb541-134">![Transformations](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art08.gif "AboutGdip05_art08")</span></span>  
  
 <span data-ttu-id="eb541-135">선형 변환 (2 × 2 행렬에서 곱하기) (1 × 2 매트릭스 더하기) 번역 다음 3x3 유사 변환을 이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb541-135">A linear transformation (multiplication by a 2×2 matrix) followed by a translation (addition of a 1×2 matrix) is called an affine transformation.</span></span> <span data-ttu-id="eb541-136">3x3 유사 변형 행렬 (선형 부분에 대 한 1) 및 변환에 대 한 쌍에 저장 하는 대신 3 × 3 행렬의 전체 변환을 저장 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="eb541-136">An alternative to storing an affine transformation in a pair of matrices (one for the linear part and one for the translation) is to store the entire transformation in a 3×3 matrix.</span></span> <span data-ttu-id="eb541-137">이 작업을 하려면 평면에서 점은 세 번째 좌표가 더미와 1 × 3 행렬에 저장 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb541-137">To make this work, a point in the plane must be stored in a 1×3 matrix with a dummy 3rd coordinate.</span></span> <span data-ttu-id="eb541-138">일반적으로 모든 세 번째 좌표를 1로 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb541-138">The usual technique is to make all 3rd coordinates equal to 1.</span></span> <span data-ttu-id="eb541-139">예를 들어 점 (2, 1) 행렬 [2 1 1]로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb541-139">For example, the point (2, 1) is represented by the matrix [2 1 1].</span></span> <span data-ttu-id="eb541-140">다음 그림과 유사 변환 (90도 회전, 3 방향으로에서 단위 x, y 방향의 4 단위 변환) 단일 3 × 3 매트릭스 곱으로 표현 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb541-140">The following illustration shows an affine transformation (rotate 90 degrees; translate 3 units in the x direction, 4 units in the y direction) expressed as multiplication by a single 3×3 matrix.</span></span>  
  
 <span data-ttu-id="eb541-141">![변환](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art09.gif "AboutGdip05_art09")</span><span class="sxs-lookup"><span data-stu-id="eb541-141">![Transformations](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art09.gif "AboutGdip05_art09")</span></span>  
  
 <span data-ttu-id="eb541-142">앞의 예제에서 점 (2, 1) 점 (2, 6)에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb541-142">In the preceding example, the point (2, 1) is mapped to the point (2, 6).</span></span> <span data-ttu-id="eb541-143">Note 숫자 0, 0, 1 3 × 3 행렬의 세 번째 열에 포함 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb541-143">Note that the third column of the 3×3 matrix contains the numbers 0, 0, 1.</span></span> <span data-ttu-id="eb541-144">이 3x3 유사 변환의 3 × 3 행렬의 경우 항상 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb541-144">This will always be the case for the 3×3 matrix of an affine transformation.</span></span> <span data-ttu-id="eb541-145">중요 한 번호는 1과 2 열에 6 개의 숫자입니다.</span><span class="sxs-lookup"><span data-stu-id="eb541-145">The important numbers are the six numbers in columns 1 and 2.</span></span> <span data-ttu-id="eb541-146">행렬의 왼쪽 위 2 × 2 부분은 변환의 선형 부분을 나타내고, 세 번째 행의 처음 두 항목 번역을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="eb541-146">The upper-left 2×2 portion of the matrix represents the linear part of the transformation, and the first two entries in the 3rd row represent the translation.</span></span>  
  
 <span data-ttu-id="eb541-147">![변환](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art10.gif "AboutGdip05_art10")</span><span class="sxs-lookup"><span data-stu-id="eb541-147">![Transformations](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art10.gif "AboutGdip05_art10")</span></span>  
  
 <span data-ttu-id="eb541-148">[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 는 3x3 유사 변형에 저장할 수 있습니다는 <xref:System.Drawing.Drawing2D.Matrix> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="eb541-148">In [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] you can store an affine transformation in a <xref:System.Drawing.Drawing2D.Matrix> object.</span></span> <span data-ttu-id="eb541-149">나타내는 3x3 유사 변형 매트릭스의 세 번째 열은 항상 때문에 (0, 0, 1)을 만들 때 처음 두 열에 있는 6 개의 숫자만 지정는 <xref:System.Drawing.Drawing2D.Matrix> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="eb541-149">Because the third column of a matrix that represents an affine transformation is always (0, 0, 1), you specify only the six numbers in the first two columns when you construct a <xref:System.Drawing.Drawing2D.Matrix> object.</span></span> <span data-ttu-id="eb541-150">문이 `Matrix myMatrix = new Matrix(0, 1, -1, 0, 3, 4)` 앞의 그림에 표시 된 매트릭스를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb541-150">The statement `Matrix myMatrix = new Matrix(0, 1, -1, 0, 3, 4)` constructs the matrix shown in the preceding figure.</span></span>  
  
## <a name="composite-transformations"></a><span data-ttu-id="eb541-151">합성 변형</span><span class="sxs-lookup"><span data-stu-id="eb541-151">Composite Transformations</span></span>  
 <span data-ttu-id="eb541-152">복합 변환에는 다른 뒤에 오는 단일 변환의 시퀀스입니다.</span><span class="sxs-lookup"><span data-stu-id="eb541-152">A composite transformation is a sequence of transformations, one followed by the other.</span></span> <span data-ttu-id="eb541-153">매트릭스 및 다음 목록에는 변환을 고려 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb541-153">Consider the matrices and transformations in the following list:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="eb541-154">매트릭스 A</span><span class="sxs-lookup"><span data-stu-id="eb541-154">Matrix A</span></span>|<span data-ttu-id="eb541-155">90도 회전</span><span class="sxs-lookup"><span data-stu-id="eb541-155">Rotate 90 degrees</span></span>|  
|<span data-ttu-id="eb541-156">매트릭스 B</span><span class="sxs-lookup"><span data-stu-id="eb541-156">Matrix B</span></span>|<span data-ttu-id="eb541-157">X 방향으로 2의 비율로 크기 조정</span><span class="sxs-lookup"><span data-stu-id="eb541-157">Scale by a factor of 2 in the x direction</span></span>|  
|<span data-ttu-id="eb541-158">C 매트릭스</span><span class="sxs-lookup"><span data-stu-id="eb541-158">Matrix C</span></span>|<span data-ttu-id="eb541-159">Y 방향의 3 단위</span><span class="sxs-lookup"><span data-stu-id="eb541-159">Translate 3 units in the y direction</span></span>|  
  
 <span data-ttu-id="eb541-160">점 (2, 1)으로 시작 하는 경우-행렬 [2 1 1]로 표시-A, B, C, 점 (2, 1)에 나열 된 순서로 세 가지 변환 될 예정 다음 곱하면 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb541-160">If we start with the point (2, 1) — represented by the matrix [2 1 1] — and multiply by A, then B, then C, the point (2, 1) will undergo the three transformations in the order listed.</span></span>  
  
 <span data-ttu-id="eb541-161">[2 1 1]ABC = [-2 5 1]</span><span class="sxs-lookup"><span data-stu-id="eb541-161">[2 1 1]ABC = [-2 5 1]</span></span>  
  
 <span data-ttu-id="eb541-162">대신 세 개의 별도 행렬에 복합 변환의 세 부분을 저장, A, 곱하기 수 B 및 C 함께 전체 복합 변환을 저장 하는 단일 3 × 3 행렬을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="eb541-162">Rather than store the three parts of the composite transformation in three separate matrices, you can multiply A, B, and C together to get a single 3×3 matrix that stores the entire composite transformation.</span></span> <span data-ttu-id="eb541-163">ABC 가정 = D D를 곱하면 A, B, C 곱하면와 동일한 결과 제공 하는 다음</span><span class="sxs-lookup"><span data-stu-id="eb541-163">Suppose ABC = D. Then a point multiplied by D gives the same result as a point multiplied by A, then B, then C.</span></span>  
  
 <span data-ttu-id="eb541-164">[2 1 1]D = [-2 5 1]</span><span class="sxs-lookup"><span data-stu-id="eb541-164">[2 1 1]D = [-2 5 1]</span></span>  
  
 <span data-ttu-id="eb541-165">다음 그림 A "," B "," C "및" 4. 매트릭스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="eb541-165">The following illustration shows the matrices A, B, C, and D.</span></span>  
  
 <span data-ttu-id="eb541-166">![변환](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art12.gif "AboutGdip05_art12")</span><span class="sxs-lookup"><span data-stu-id="eb541-166">![Transformations](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art12.gif "AboutGdip05_art12")</span></span>  
  
 <span data-ttu-id="eb541-167">개별 변형 매트릭스를 곱하여 복합 변환 매트릭스를 만들 수 있습니다 팩트 관계 변환 시퀀스는 단일에 저장할 수 있습니다 의미 <xref:System.Drawing.Drawing2D.Matrix> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="eb541-167">The fact that the matrix of a composite transformation can be formed by multiplying the individual transformation matrices means that any sequence of affine transformations can be stored in a single <xref:System.Drawing.Drawing2D.Matrix> object.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="eb541-168">복합 변환의 순서가 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb541-168">The order of a composite transformation is important.</span></span> <span data-ttu-id="eb541-169">일반적으로, 다음 크기 조정, 이동을 차례로 동일 하지는 않습니다 눈금으로 한 후를 회전 하 고 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb541-169">In general, rotate, then scale, then translate is not the same as scale, then rotate, then translate.</span></span> <span data-ttu-id="eb541-170">마찬가지로, 매트릭스 곱의 순서는 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb541-170">Similarly, the order of matrix multiplication is important.</span></span> <span data-ttu-id="eb541-171">일반적으로 ABC는 하지 하기와 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb541-171">In general, ABC is not the same as BAC.</span></span>  
  
 <span data-ttu-id="eb541-172"><xref:System.Drawing.Drawing2D.Matrix> 클래스 복합 변환을 구성 하는 여러 가지 방법을 제공: <xref:System.Drawing.Drawing2D.Matrix.Multiply%2A>, <xref:System.Drawing.Drawing2D.Matrix.Rotate%2A>, <xref:System.Drawing.Drawing2D.Matrix.RotateAt%2A>, <xref:System.Drawing.Drawing2D.Matrix.Scale%2A>, <xref:System.Drawing.Drawing2D.Matrix.Shear%2A>, 및 <xref:System.Drawing.Drawing2D.Matrix.Translate%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="eb541-172">The <xref:System.Drawing.Drawing2D.Matrix> class provides several methods for building a composite transformation: <xref:System.Drawing.Drawing2D.Matrix.Multiply%2A>, <xref:System.Drawing.Drawing2D.Matrix.Rotate%2A>, <xref:System.Drawing.Drawing2D.Matrix.RotateAt%2A>, <xref:System.Drawing.Drawing2D.Matrix.Scale%2A>, <xref:System.Drawing.Drawing2D.Matrix.Shear%2A>, and <xref:System.Drawing.Drawing2D.Matrix.Translate%2A>.</span></span> <span data-ttu-id="eb541-173">다음 예제에서는 30도 회전 다음 y 방향으로 2 배 하 여 확장 한 다음 x 방향의 5 단위를 변환 하는 복합 변환 행렬을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="eb541-173">The following example creates the matrix of a composite transformation that first rotates 30 degrees, then scales by a factor of 2 in the y direction, and then translates 5 units in the x direction:</span></span>  
  
 [!code-csharp[System.Drawing.CoordinateSystems#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.CoordinateSystems#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#11)]  
  
 <span data-ttu-id="eb541-174">다음은 행렬입니다.</span><span class="sxs-lookup"><span data-stu-id="eb541-174">The following illustration shows the matrix.</span></span>  
  
 <span data-ttu-id="eb541-175">![변환](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art13.gif "AboutGdip05_art13")</span><span class="sxs-lookup"><span data-stu-id="eb541-175">![Transformations](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art13.gif "AboutGdip05_art13")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb541-176">참고 항목</span><span class="sxs-lookup"><span data-stu-id="eb541-176">See Also</span></span>  
 [<span data-ttu-id="eb541-177">좌표계 및 변형</span><span class="sxs-lookup"><span data-stu-id="eb541-177">Coordinate Systems and Transformations</span></span>](../../../../docs/framework/winforms/advanced/coordinate-systems-and-transformations.md)  
 [<span data-ttu-id="eb541-178">관리 GDI+에서 변형 사용</span><span class="sxs-lookup"><span data-stu-id="eb541-178">Using Transformations in Managed GDI+</span></span>](../../../../docs/framework/winforms/advanced/using-transformations-in-managed-gdi.md)
