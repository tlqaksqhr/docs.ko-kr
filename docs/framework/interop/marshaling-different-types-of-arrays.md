---
title: 여러 형식의 배열 마샬링
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- marshaling, Arrays sample
- data marshaling, Arrays sample
ms.assetid: c5ac9920-5b6e-4dc9-bf2d-1f6f8ad3b0bf
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ed2a4b91608306021ce510098eaf044520cbb089
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33391458"
---
# <a name="marshaling-different-types-of-arrays"></a><span data-ttu-id="cf0a4-102">여러 형식의 배열 마샬링</span><span class="sxs-lookup"><span data-stu-id="cf0a4-102">Marshaling Different Types of Arrays</span></span>
<span data-ttu-id="cf0a4-103">배열은 동일한 형식의 요소를 하나 이상 포함하는 관리 코드의 참조 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="cf0a4-103">An array is a reference type in managed code that contains one or more elements of the same type.</span></span> <span data-ttu-id="cf0a4-104">배열은 참조 형식이지만 관리되지 않는 함수에 In 매개 변수로 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf0a4-104">Although arrays are reference types, they are passed as In parameters to unmanaged functions.</span></span> <span data-ttu-id="cf0a4-105">이 동작은 관리되는 배열이 관리되는 개체에 전달되는 방식(In/Out 매개 변수로)과 일치하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cf0a4-105">This behavior is inconsistent with way managed arrays are passed to managed objects, which is as In/Out parameters.</span></span> <span data-ttu-id="cf0a4-106">자세한 내용은 [복사 및 고정](copying-and-pinning.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cf0a4-106">For additional details, see [Copying and Pinning](copying-and-pinning.md).</span></span>  
  
 <span data-ttu-id="cf0a4-107">다음 표에서는 배열에 대한 마샬링 옵션을 나열하고 사용법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0a4-107">The following table lists marshaling options for arrays and describes their usage.</span></span>  
  
|<span data-ttu-id="cf0a4-108">배열</span><span class="sxs-lookup"><span data-stu-id="cf0a4-108">Array</span></span>|<span data-ttu-id="cf0a4-109">설명</span><span class="sxs-lookup"><span data-stu-id="cf0a4-109">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="cf0a4-110">값 형식 정수.</span><span class="sxs-lookup"><span data-stu-id="cf0a4-110">Of integers by value.</span></span>|<span data-ttu-id="cf0a4-111">정수 배열을 In 매개 변수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0a4-111">Passes an array of integers as an In parameter.</span></span>|  
|<span data-ttu-id="cf0a4-112">참조 형식 정수.</span><span class="sxs-lookup"><span data-stu-id="cf0a4-112">Of integers by reference.</span></span>|<span data-ttu-id="cf0a4-113">정수 배열을 In/Out 매개 변수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0a4-113">Passes an array of integers as an In/Out parameter.</span></span>|  
|<span data-ttu-id="cf0a4-114">값 형식 정수(2차원).</span><span class="sxs-lookup"><span data-stu-id="cf0a4-114">Of integers by value (two-dimensional).</span></span>|<span data-ttu-id="cf0a4-115">정수 행렬을 In 매개 변수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0a4-115">Passes a matrix of integers as an In parameter.</span></span>|  
|<span data-ttu-id="cf0a4-116">값 형식 문자열.</span><span class="sxs-lookup"><span data-stu-id="cf0a4-116">Of strings by value.</span></span>|<span data-ttu-id="cf0a4-117">문자열 배열을 In 매개 변수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0a4-117">Passes an array of strings as an In parameter.</span></span>|  
|<span data-ttu-id="cf0a4-118">정수를 포함하는 구조체.</span><span class="sxs-lookup"><span data-stu-id="cf0a4-118">Of structures with integers.</span></span>|<span data-ttu-id="cf0a4-119">정수를 포함하는 구조체 배열을 In 매개 변수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0a4-119">Passes an array of structures that contain integers as an In parameter.</span></span>|  
|<span data-ttu-id="cf0a4-120">문자열을 포함하는 구조체.</span><span class="sxs-lookup"><span data-stu-id="cf0a4-120">Of structures with strings.</span></span>|<span data-ttu-id="cf0a4-121">정수만 포함하는 구조체 배열을 In/Out 매개 변수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0a4-121">Passes an array of structures that contain only integers as an In/Out parameter.</span></span> <span data-ttu-id="cf0a4-122">배열의 멤버를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf0a4-122">Members of the array can be changed.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="cf0a4-123">예</span><span class="sxs-lookup"><span data-stu-id="cf0a4-123">Example</span></span>  
 <span data-ttu-id="cf0a4-124">이 샘플에서는 다음 형식의 배열을 전달하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cf0a4-124">This sample demonstrates how to pass the following types of arrays:</span></span>  
  
-   <span data-ttu-id="cf0a4-125">값 형식 정수 배열</span><span class="sxs-lookup"><span data-stu-id="cf0a4-125">Array of integers by value.</span></span>  
  
-   <span data-ttu-id="cf0a4-126">크기를 조정할 수 있는 참조 형식 정수 배열</span><span class="sxs-lookup"><span data-stu-id="cf0a4-126">Array of integers by reference, which can be resized.</span></span>  
  
-   <span data-ttu-id="cf0a4-127">값 형식 정수의 다차원 배열(행렬)</span><span class="sxs-lookup"><span data-stu-id="cf0a4-127">Multidimensional array (matrix) of integers by value.</span></span>  
  
-   <span data-ttu-id="cf0a4-128">값 형식 문자열 배열</span><span class="sxs-lookup"><span data-stu-id="cf0a4-128">Array of strings by value.</span></span>  
  
-   <span data-ttu-id="cf0a4-129">정수를 포함하는 구조체 배열</span><span class="sxs-lookup"><span data-stu-id="cf0a4-129">Array of structures with integers.</span></span>  
  
-   <span data-ttu-id="cf0a4-130">문자열을 포함하는 구조체 배열</span><span class="sxs-lookup"><span data-stu-id="cf0a4-130">Array of structures with strings.</span></span>  
  
 <span data-ttu-id="cf0a4-131">배열이 참조에 의해 명시적으로 마샬링되지 않은 한 기본 동작은 배열을 In 매개 변수로 마샬링합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0a4-131">Unless an array is explicitly marshaled by reference, the default behavior marshals the array as an In parameter.</span></span> <span data-ttu-id="cf0a4-132"><xref:System.Runtime.InteropServices.InAttribute> 및 <xref:System.Runtime.InteropServices.OutAttribute> 특성을 명시적으로 적용하면 이 동작을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf0a4-132">You can change this behavior by applying the <xref:System.Runtime.InteropServices.InAttribute> and <xref:System.Runtime.InteropServices.OutAttribute> attributes explicitly.</span></span>  
  
 <span data-ttu-id="cf0a4-133">Arrays 샘플에서는 원래 함수 선언과 함께 표시되는 다음과 같은 관리되지 않는 함수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0a4-133">The Arrays sample uses the following unmanaged functions, shown with their original function declaration:</span></span>  
  
-   <span data-ttu-id="cf0a4-134">PinvokeLib.dll에서 내보낸**TestArrayOfInts** </span><span class="sxs-lookup"><span data-stu-id="cf0a4-134">**TestArrayOfInts** exported from PinvokeLib.dll.</span></span>  
  
    ```  
    int TestArrayOfInts(int* pArray, int pSize);  
    ```  
  
-   <span data-ttu-id="cf0a4-135">PinvokeLib.dll에서 내보낸**TestRefArrayOfInts** </span><span class="sxs-lookup"><span data-stu-id="cf0a4-135">**TestRefArrayOfInts** exported from PinvokeLib.dll.</span></span>  
  
    ```  
    int TestRefArrayOfInts(int** ppArray, int* pSize);  
    ```  
  
-   <span data-ttu-id="cf0a4-136">PinvokeLib.dll에서 내보낸**TestMatrixOfInts** </span><span class="sxs-lookup"><span data-stu-id="cf0a4-136">**TestMatrixOfInts** exported from PinvokeLib.dll.</span></span>  
  
    ```  
    int TestMatrixOfInts(int pMatrix[][COL_DIM], int row);  
    ```  
  
-   <span data-ttu-id="cf0a4-137">PinvokeLib.dll에서 내보낸**TestArrayOfStrings** </span><span class="sxs-lookup"><span data-stu-id="cf0a4-137">**TestArrayOfStrings** exported from PinvokeLib.dll.</span></span>  
  
    ```  
    int TestArrayOfStrings(char** ppStrArray, int size);  
    ```  
  
-   <span data-ttu-id="cf0a4-138">PinvokeLib.dll에서 내보낸**TestArrayOfStructs** </span><span class="sxs-lookup"><span data-stu-id="cf0a4-138">**TestArrayOfStructs** exported from PinvokeLib.dll.</span></span>  
  
    ```  
    int TestArrayOfStructs(MYPOINT* pPointArray, int size);  
    ```  
  
-   <span data-ttu-id="cf0a4-139">PinvokeLib.dll에서 내보낸**TestArrayOfStructs2** </span><span class="sxs-lookup"><span data-stu-id="cf0a4-139">**TestArrayOfStructs2** exported from PinvokeLib.dll.</span></span>  
  
    ```  
    int TestArrayOfStructs2 (MYPERSON* pPersonArray, int size);  
    ```  
  
 <span data-ttu-id="cf0a4-140">[PinvokeLib.dll](https://msdn.microsoft.com/library/5d1438d7-9946-489d-8ede-6c694a08f614(v=vs.100))은 앞에 나열된 함수 및 2개의 구조체 변수 **MYPOINT** 및 **MYPERSON**에 대한 구현을 포함하는 관리되지 않는 사용자 지정 라이브러리입니다.</span><span class="sxs-lookup"><span data-stu-id="cf0a4-140">[PinvokeLib.dll](https://msdn.microsoft.com/library/5d1438d7-9946-489d-8ede-6c694a08f614(v=vs.100)) is a custom unmanaged library that contains implementations for the previously listed functions and two structure variables, **MYPOINT** and **MYPERSON**.</span></span> <span data-ttu-id="cf0a4-141">구조체에는 다음과 같은 요소가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf0a4-141">The structures contain the following elements:</span></span>  
  
```  
typedef struct _MYPOINT  
{  
   int x;   
   int y;   
} MYPOINT;  
  
typedef struct _MYPERSON  
{  
   char* first;   
   char* last;   
} MYPERSON;  
```  
  
 <span data-ttu-id="cf0a4-142">이 샘플에서 `MyPoint` 및 `MyPerson` 구조체에는 포함된 형식이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf0a4-142">In this sample, the `MyPoint` and `MyPerson` structures contain embedded types.</span></span> <span data-ttu-id="cf0a4-143"><xref:System.Runtime.InteropServices.StructLayoutAttribute> 특성이 설정되어 멤버가 표시되는 순서대로 순차적으로 메모리에 정렬되게 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0a4-143">The <xref:System.Runtime.InteropServices.StructLayoutAttribute> attribute is set to ensure that the members are arranged in memory sequentially, in the order in which they appear.</span></span>  
  
 <span data-ttu-id="cf0a4-144">`LibWrap` 클래스에는 `App` 클래스가 호출하는 메서드 집합이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf0a4-144">The `LibWrap` class contains a set of methods called by the `App` class.</span></span> <span data-ttu-id="cf0a4-145">배열을 전달하는 방법에 대한 자세한 내용은 다음 샘플의 설명을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cf0a4-145">For specific details about passing arrays, see the comments in the following sample.</span></span> <span data-ttu-id="cf0a4-146">참조 형식인 배열은 기본적으로 In 매개 변수로 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf0a4-146">An array, which is a reference type, is passed as an In parameter by default.</span></span> <span data-ttu-id="cf0a4-147">호출자가 결과를 받으려면 배열을 포함하는 인수에 **InAttribute** 및 **OutAttribute** 를 명시적으로 적용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0a4-147">For the caller to receive the results, **InAttribute** and **OutAttribute** must be applied explicitly to the argument containing the array.</span></span>  
  
### <a name="declaring-prototypes"></a><span data-ttu-id="cf0a4-148">프로토타입 선언</span><span class="sxs-lookup"><span data-stu-id="cf0a4-148">Declaring Prototypes</span></span>  
 [!code-csharp[Conceptual.Interop.Marshaling#31](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/arrays.cs#31)]
 [!code-vb[Conceptual.Interop.Marshaling#31](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/arrays.vb#31)]  
  
### <a name="calling-functions"></a><span data-ttu-id="cf0a4-149">함수 호출</span><span class="sxs-lookup"><span data-stu-id="cf0a4-149">Calling Functions</span></span>  
 [!code-csharp[Conceptual.Interop.Marshaling#32](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/arrays.cs#32)]
 [!code-vb[Conceptual.Interop.Marshaling#32](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/arrays.vb#32)]  
  
## <a name="see-also"></a><span data-ttu-id="cf0a4-150">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cf0a4-150">See Also</span></span>  
 <span data-ttu-id="cf0a4-151">[형식 배열 마샬링](https://msdn.microsoft.com/library/049b1c1b-228f-4445-88ec-91bc7fd4b1e8(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="cf0a4-151">[Marshaling Arrays of Types](https://msdn.microsoft.com/library/049b1c1b-228f-4445-88ec-91bc7fd4b1e8(v=vs.100))</span></span>  
 <span data-ttu-id="cf0a4-152">[플랫폼 호출 데이터 형식](https://msdn.microsoft.com/library/16014d9f-d6bd-481e-83f0-df11377c550f(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="cf0a4-152">[Platform Invoke Data Types](https://msdn.microsoft.com/library/16014d9f-d6bd-481e-83f0-df11377c550f(v=vs.100))</span></span>  
 [<span data-ttu-id="cf0a4-153">관리 코드에서 프로토타입 만들기</span><span class="sxs-lookup"><span data-stu-id="cf0a4-153">Creating Prototypes in Managed Code</span></span>](creating-prototypes-in-managed-code.md)
