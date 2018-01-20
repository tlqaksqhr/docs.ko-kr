---
title: "배열에 대한 기본 마샬링"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- interop marshaling, arrays
- arrays, interop marshaling
ms.assetid: 8a3cca8b-dd94-4e3d-ad9a-9ee7590654bc
caps.latest.revision: "19"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 91df17448a57f7495dc95fb2b4ab1fa63dd8a27f
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="default-marshaling-for-arrays"></a><span data-ttu-id="286c7-102">배열에 대한 기본 마샬링</span><span class="sxs-lookup"><span data-stu-id="286c7-102">Default Marshaling for Arrays</span></span>
<span data-ttu-id="286c7-103">전체적으로 관리 코드로 구성된 응용 프로그램에서는 공용 언어 런타임이 배열 형식을 In/Out 매개 변수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="286c7-103">In an application consisting entirely of managed code, the common language runtime passes array types as In/Out parameters.</span></span> <span data-ttu-id="286c7-104">반면 interop 마샬러는 기본적으로 배열을 In 매개 변수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="286c7-104">In contrast, the interop marshaler passes an array as In parameters by default.</span></span>  
  
 <span data-ttu-id="286c7-105">[고정 최적화](../../../docs/framework/interop/copying-and-pinning.md)를 통해 blittable 배열은 같은 아파트의 개체와 상호 작용할 때 In/Out 매개 변수로 사용되는 것으로 보일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="286c7-105">With [pinning optimization](../../../docs/framework/interop/copying-and-pinning.md), a blittable array can appear to operate as an In/Out parameter when interacting with objects in the same apartment.</span></span> <span data-ttu-id="286c7-106">그러나 나중에 컴퓨터 간 프록시를 생성하는 데 사용되는 형식 라이브러리에 코드를 내보내고 해당 라이브러리를 사용하여 아파트 간에 호출을 마샬링할 경우 호출은 실제 In 매개 변수 동작으로 되돌아갈 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="286c7-106">However, if you later export the code to a type library used to generate the cross-machine proxy, and that library is used to marshal your calls across apartments, the calls can revert to true In parameter behavior.</span></span>  
  
 <span data-ttu-id="286c7-107">배열은 본질적으로 복잡하고 관리되는 배열과 관리되지 않는 배열을 구별하면 다른 비 blittable 형식보다 더 많은 정보를 보장합니다.</span><span class="sxs-lookup"><span data-stu-id="286c7-107">Arrays are complex by nature, and the distinctions between managed and unmanaged arrays warrant more information than other non-blittable types.</span></span> <span data-ttu-id="286c7-108">이 항목에서는 배열 마샬링에 대한 다음 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="286c7-108">This topic provides the following information on marshaling arrays:</span></span>  
  
-   [<span data-ttu-id="286c7-109">관리되는 배열</span><span class="sxs-lookup"><span data-stu-id="286c7-109">Managed Arrays</span></span>](#cpcondefaultmarshalingforarraysanchor1)  
  
-   [<span data-ttu-id="286c7-110">관리되지 않는 배열</span><span class="sxs-lookup"><span data-stu-id="286c7-110">Unmanaged Arrays</span></span>](#cpcondefaultmarshalingforarraysanchor2)  
  
-   [<span data-ttu-id="286c7-111">.NET 코드에 배열 매개 변수 전달</span><span class="sxs-lookup"><span data-stu-id="286c7-111">Passing Array Parameters to .NET Code</span></span>](#cpcondefaultmarshalingforarraysanchor3)  
  
-   [<span data-ttu-id="286c7-112">COM에 배열 전달</span><span class="sxs-lookup"><span data-stu-id="286c7-112">Passing Arrays to COM</span></span>](#cpcondefaultmarshalingforarraysanchor4)  
  
<a name="cpcondefaultmarshalingforarraysanchor1"></a>   
## <a name="managed-arrays"></a><span data-ttu-id="286c7-113">관리되는 배열</span><span class="sxs-lookup"><span data-stu-id="286c7-113">Managed Arrays</span></span>  
 <span data-ttu-id="286c7-114">관리되는 배열 형식은 달라질 수 있지만 <xref:System.Array?displayProperty=nameWithType> 클래스는 모든 배열 형식의 기본 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="286c7-114">Managed array types can vary; however, the <xref:System.Array?displayProperty=nameWithType> class is the base class of all array types.</span></span> <span data-ttu-id="286c7-115">**System.Array** 클래스에는 배열의 순위, 길이 및 하한/상한을 결정하기 위한 속성과 배열을 액세스, 정렬, 검색, 복사, 생성하기 위한 메서드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="286c7-115">The **System.Array** class has properties for determining the rank, length, and lower and upper bounds of an array, as well as methods for accessing, sorting, searching, copying, and creating arrays.</span></span>  
  
 <span data-ttu-id="286c7-116">이러한 배열 형식의 경우 동적이고 기본 클래스 라이브러리에서 정의된 해당 정적 형식이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="286c7-116">These array types are dynamic and do not have a corresponding static type defined in the base class library.</span></span> <span data-ttu-id="286c7-117">각 요소 형식 및 순위의 조합을 개별 배열 형식으로 생각하면 편리합니다.</span><span class="sxs-lookup"><span data-stu-id="286c7-117">It is convenient to think of each combination of element type and rank as a distinct type of array.</span></span> <span data-ttu-id="286c7-118">따라서 정수의 1차원 배열은 double 형식의 1차원 배열과 형식이 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="286c7-118">Therefore, a one-dimensional array of integers is of a different type than a one-dimensional array of double types.</span></span> <span data-ttu-id="286c7-119">마찬가지로 정수의 2차원 배열은 정수의 1차원 배열과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="286c7-119">Similarly a two-dimensional array of integers is different from a one-dimensional array of integers.</span></span> <span data-ttu-id="286c7-120">형식을 비교할 경우 배열의 경계를 고려하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="286c7-120">The bounds of the array are not considered when comparing types.</span></span>  
  
 <span data-ttu-id="286c7-121">다음 표와 같이 관리되는 배열의 인스턴스에는 특수 요소 형식, 순위 및 하한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="286c7-121">As the following table shows, any instance of a managed array must be of a specific element type, rank, and lower bound.</span></span>  
  
|<span data-ttu-id="286c7-122">관리되는 배열 형식</span><span class="sxs-lookup"><span data-stu-id="286c7-122">Managed array type</span></span>|<span data-ttu-id="286c7-123">요소 형식</span><span class="sxs-lookup"><span data-stu-id="286c7-123">Element type</span></span>|<span data-ttu-id="286c7-124">순위</span><span class="sxs-lookup"><span data-stu-id="286c7-124">Rank</span></span>|<span data-ttu-id="286c7-125">하한</span><span class="sxs-lookup"><span data-stu-id="286c7-125">Lower bound</span></span>|<span data-ttu-id="286c7-126">시그니처 표기법</span><span class="sxs-lookup"><span data-stu-id="286c7-126">Signature notation</span></span>|  
|------------------------|------------------|----------|-----------------|------------------------|  
|<span data-ttu-id="286c7-127">**ELEMENT_TYPE_ARRAY**</span><span class="sxs-lookup"><span data-stu-id="286c7-127">**ELEMENT_TYPE_ARRAY**</span></span>|<span data-ttu-id="286c7-128">형식으로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="286c7-128">Specified by type.</span></span>|<span data-ttu-id="286c7-129">순위로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="286c7-129">Specified by rank.</span></span>|<span data-ttu-id="286c7-130">필요한 경우 경계로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="286c7-130">Optionally specified by bounds.</span></span>|<span data-ttu-id="286c7-131">*type* **[** *n*,*m* **]**</span><span class="sxs-lookup"><span data-stu-id="286c7-131">*type* **[** *n*,*m* **]**</span></span>|  
|<span data-ttu-id="286c7-132">**ELEMENT_TYPE_CLASS**</span><span class="sxs-lookup"><span data-stu-id="286c7-132">**ELEMENT_TYPE_CLASS**</span></span>|<span data-ttu-id="286c7-133">알 수 없음</span><span class="sxs-lookup"><span data-stu-id="286c7-133">Unknown</span></span>|<span data-ttu-id="286c7-134">알 수 없음</span><span class="sxs-lookup"><span data-stu-id="286c7-134">Unknown</span></span>|<span data-ttu-id="286c7-135">알 수 없음</span><span class="sxs-lookup"><span data-stu-id="286c7-135">Unknown</span></span>|<span data-ttu-id="286c7-136">**System.Array**</span><span class="sxs-lookup"><span data-stu-id="286c7-136">**System.Array**</span></span>|  
|<span data-ttu-id="286c7-137">**ELEMENT_TYPE_SZARRAY**</span><span class="sxs-lookup"><span data-stu-id="286c7-137">**ELEMENT_TYPE_SZARRAY**</span></span>|<span data-ttu-id="286c7-138">형식으로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="286c7-138">Specified by type.</span></span>|<span data-ttu-id="286c7-139">1</span><span class="sxs-lookup"><span data-stu-id="286c7-139">1</span></span>|<span data-ttu-id="286c7-140">0</span><span class="sxs-lookup"><span data-stu-id="286c7-140">0</span></span>|<span data-ttu-id="286c7-141">*type* **[** *n* **]**</span><span class="sxs-lookup"><span data-stu-id="286c7-141">*type* **[** *n* **]**</span></span>|  
  
<a name="cpcondefaultmarshalingforarraysanchor2"></a>   
## <a name="unmanaged-arrays"></a><span data-ttu-id="286c7-142">관리되지 않는 배열</span><span class="sxs-lookup"><span data-stu-id="286c7-142">Unmanaged Arrays</span></span>  
 <span data-ttu-id="286c7-143">관리되지 않는 배열은 고정 또는 가변 길이가 포함된 COM 스타일 안전 배열 또는 C 스타일 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="286c7-143">Unmanaged arrays are either COM-style safe arrays or C-style arrays with fixed or variable length.</span></span> <span data-ttu-id="286c7-144">안전 배열은 연결된 배열 데이터의 형식, 순위 및 경계를 제공하는 자체 설명 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="286c7-144">Safe arrays are self-describing arrays that carry the type, rank, and bounds of the associated array data.</span></span> <span data-ttu-id="286c7-145">C 스타일 배열은 고정 하한이 0인 1차원 형식 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="286c7-145">C-style arrays are one-dimensional typed arrays with a fixed lower bound of 0.</span></span> <span data-ttu-id="286c7-146">마샬링 서비스는 두 가지 배열 형식에 대한 지원을 모두 제한했습니다.</span><span class="sxs-lookup"><span data-stu-id="286c7-146">The marshaling service has limited support for both types of arrays.</span></span>  
  
<a name="cpcondefaultmarshalingforarraysanchor3"></a>   
## <a name="passing-array-parameters-to-net-code"></a><span data-ttu-id="286c7-147">.NET 코드에 배열 매개 변수 전달</span><span class="sxs-lookup"><span data-stu-id="286c7-147">Passing Array Parameters to .NET Code</span></span>  
 <span data-ttu-id="286c7-148">C 스타일 배열 및 안전 배열은 둘 다 비관리 코드에서 안전 배열 또는 C 스타일 배열로 .NET 코드에 전달될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="286c7-148">Both C-style arrays and safe arrays can be passed to .NET code from unmanaged code as either a safe array or a C-style array.</span></span> <span data-ttu-id="286c7-149">다음 표에서는 관리되지 않는 형식 값과 가져온 형식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="286c7-149">The following table shows the unmanaged type value and the imported type.</span></span>  
  
|<span data-ttu-id="286c7-150">관리되지 않는 형식</span><span class="sxs-lookup"><span data-stu-id="286c7-150">Unmanaged type</span></span>|<span data-ttu-id="286c7-151">가져온 형식</span><span class="sxs-lookup"><span data-stu-id="286c7-151">Imported type</span></span>|  
|--------------------|-------------------|  
|<span data-ttu-id="286c7-152">**SafeArray(** *Type* **)**</span><span class="sxs-lookup"><span data-stu-id="286c7-152">**SafeArray(** *Type* **)**</span></span>|<span data-ttu-id="286c7-153">**ELEMENT_TYPE_SZARRAY** **\<** *ConvertedType* **>**</span><span class="sxs-lookup"><span data-stu-id="286c7-153">**ELEMENT_TYPE_SZARRAY** **\<** *ConvertedType* **>**</span></span><br /><br /> <span data-ttu-id="286c7-154">순위 = 1, 하한 = 0.</span><span class="sxs-lookup"><span data-stu-id="286c7-154">Rank = 1, lower bound = 0.</span></span> <span data-ttu-id="286c7-155">관리되는 시그니처에서 제공된 경우에만 크기가 알려집니다.</span><span class="sxs-lookup"><span data-stu-id="286c7-155">Size is known only if provided in the managed signature.</span></span> <span data-ttu-id="286c7-156">순위 = 1 또는 하한 = 0이 아닌 안전 배열은 **SZARRAY**로 마샬링될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="286c7-156">Safe arrays that are not rank = 1 or lower bound = 0 cannot be marshaled as **SZARRAY**.</span></span>|  
|<span data-ttu-id="286c7-157">*Type*  **[]**</span><span class="sxs-lookup"><span data-stu-id="286c7-157">*Type*  **[]**</span></span>|<span data-ttu-id="286c7-158">**ELEMENT_TYPE_SZARRAY** **\<** *ConvertedType* **>**</span><span class="sxs-lookup"><span data-stu-id="286c7-158">**ELEMENT_TYPE_SZARRAY** **\<** *ConvertedType* **>**</span></span><br /><br /> <span data-ttu-id="286c7-159">순위 = 1, 하한 = 0.</span><span class="sxs-lookup"><span data-stu-id="286c7-159">Rank = 1, lower bound = 0.</span></span> <span data-ttu-id="286c7-160">관리되는 시그니처에서 제공된 경우에만 크기가 알려집니다.</span><span class="sxs-lookup"><span data-stu-id="286c7-160">Size is known only if provided in the managed signature.</span></span>|  
  
### <a name="safe-arrays"></a><span data-ttu-id="286c7-161">안전 배열</span><span class="sxs-lookup"><span data-stu-id="286c7-161">Safe Arrays</span></span>  
 <span data-ttu-id="286c7-162">안전 배열을 형식 라이브러리에서 .NET 어셈블리로 가져온 경우 배열은 알려진 형식(예: **int**)의 1차원 배열로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="286c7-162">When a safe array is imported from a type library to a .NET assembly, the array is converted to a one-dimensional array of a known type (such as **int**).</span></span> <span data-ttu-id="286c7-163">매개 변수에 적용되는 같은 형식 변환 규칙이 배열 요소에도 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="286c7-163">The same type conversion rules that apply to parameters also apply to array elements.</span></span> <span data-ttu-id="286c7-164">예를 들어 **BSTR** 형식의 안전 배열은 문자열의 관리되는 배열이 되고 변형의 안전 배열은 개체의 관리되는 배열이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="286c7-164">For example, a safe array of **BSTR** types becomes a managed array of strings and a safe array of variants becomes a managed array of objects.</span></span> <span data-ttu-id="286c7-165">**SAFEARRAY** 요소 형식은 형식 라이브러리에서 캡처되고 <xref:System.Runtime.InteropServices.UnmanagedType> 열거형의 **SAFEARRAY** 값에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="286c7-165">The **SAFEARRAY** element type is captured from the type library and saved in the **SAFEARRAY** value of the <xref:System.Runtime.InteropServices.UnmanagedType> enumeration.</span></span>  
  
 <span data-ttu-id="286c7-166">형식 라이브러리에서 안전 배열의 순위와 범위를 확인할 수 없으므로 순위는 1로, 하한은 0으로 가정됩니다.</span><span class="sxs-lookup"><span data-stu-id="286c7-166">Because the rank and bounds of the safe array cannot be determined from the type library, the rank is assumed to equal 1 and the lower bound is assumed to equal 0.</span></span> <span data-ttu-id="286c7-167">[형식 라이브러리 가져오기(Tlbimp.exe)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md)에서 생성하는 관리되는 시그니처에 순위와 범위를 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="286c7-167">The rank and bounds must be defined in the managed signature produced by the [Type Library Importer (Tlbimp.exe)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md).</span></span> <span data-ttu-id="286c7-168">런타임에 메서드에 전달되는 순위가 다른 경우 <xref:System.Runtime.InteropServices.SafeArrayRankMismatchException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="286c7-168">If the rank passed to the method at run time differs, a <xref:System.Runtime.InteropServices.SafeArrayRankMismatchException> is thrown.</span></span> <span data-ttu-id="286c7-169">런타임에 전달되는 배열 형식이 다른 경우 <xref:System.Runtime.InteropServices.SafeArrayTypeMismatchException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="286c7-169">If the type of the array passed at run time differs, a <xref:System.Runtime.InteropServices.SafeArrayTypeMismatchException> is thrown.</span></span> <span data-ttu-id="286c7-170">다음 예제에서는 관리 및 비관리 코드의 안전 배열을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="286c7-170">The following example shows safe arrays in managed and unmanaged code.</span></span>  
  
 <span data-ttu-id="286c7-171">**관리되지 않는 시그니처**</span><span class="sxs-lookup"><span data-stu-id="286c7-171">**Unmanaged signature**</span></span>  
  
```  
HRESULT New1([in] SAFEARRAY( int ) ar);  
HRESULT New2([in] SAFEARRAY( DATE ) ar);  
HRESULT New3([in, out] SAFEARRAY( BSTR ) *ar);  
```  
  
 <span data-ttu-id="286c7-172">**관리되는 시그니처**</span><span class="sxs-lookup"><span data-stu-id="286c7-172">**Managed signature**</span></span>  
  
```vb  
Sub New1(<MarshalAs(UnmanagedType.SafeArray, SafeArraySubType:=VT_I4)> _  
   ar() As Integer)  
Sub New2(<MarshalAs(UnmanagedType.SafeArray, SafeArraySubType:=VT_DATE)> _   
   ar() As DateTime)  
Sub New3(ByRef <MarshalAs(UnmanagedType.SafeArray, SafeArraySubType:=VT_BSTR)> _   
   ar() As String)  
```  
  
```csharp  
void New1([MarshalAs(UnmanagedType.SafeArray, SafeArraySubType=VT_I4)] int[] ar) ;  
void New2([MarshalAs(UnmanagedType.SafeArray, SafeArraySubType=VT_DATE)]   
   DateTime[] ar);  
void New3([MarshalAs(UnmanagedType.SafeArray, SafeArraySubType=VT_BSTR)]   
   ref String[] ar);  
```  
  
 <span data-ttu-id="286c7-173">Tlbimp.exe에서 생성된 메서드 시그니처가 **ELEMENT_TYPE_SZARRAY** 대신 **ELEMENT_TYPE_ARRAY**의 요소 형식을 나타내도록 수정될 경우 다차원 또는 0이 아닌 경계 안전 배열은 관리 코드로 마샬링될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="286c7-173">Multidimensional, or nonzero-bound safe arrays, can be marshaled into managed code if the method signature produced by Tlbimp.exe is modified to indicate an element type of **ELEMENT_TYPE_ARRAY** instead of **ELEMENT_TYPE_SZARRAY**.</span></span> <span data-ttu-id="286c7-174">또는 Tlbimp.exe에서 **/sysarray** 스위치를 사용하여 모든 배열을 <xref:System.Array?displayProperty=nameWithType> 개체로 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="286c7-174">Alternatively, you can use the **/sysarray** switch with Tlbimp.exe to import all arrays as <xref:System.Array?displayProperty=nameWithType> objects.</span></span> <span data-ttu-id="286c7-175">전달되는 배열이 다차원으로 알려진 경우에는 Tlbimp.exe에서 생성된 MSIL(Microsoft Intermediate Language) 코드를 편집하고 다시 컴파일할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="286c7-175">In cases where the array being passed is known to be multidimensional, you can edit the Microsoft intermediate language (MSIL) code produced by Tlbimp.exe and then recompile it.</span></span> <span data-ttu-id="286c7-176">MSIL 코드를 수정하는 방법에 대한 자세한 내용은 [런타임 호출 가능 래퍼 사용자 지정](http://msdn.microsoft.com/library/4652beaf-77d0-4f37-9687-ca193288c0be)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="286c7-176">For details about how to modify MSIL code, see [Customizing Runtime Callable Wrappers](http://msdn.microsoft.com/library/4652beaf-77d0-4f37-9687-ca193288c0be).</span></span>  
  
### <a name="c-style-arrays"></a><span data-ttu-id="286c7-177">C 스타일 배열</span><span class="sxs-lookup"><span data-stu-id="286c7-177">C-Style Arrays</span></span>  
 <span data-ttu-id="286c7-178">C 스타일 배열을 형식 라이브러리에서 .NET 어셈블리로 가져온 경우 배열은 **ELEMENT_TYPE_SZARRAY**로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="286c7-178">When a C-style array is imported from a type library to a .NET assembly, the array is converted to **ELEMENT_TYPE_SZARRAY**.</span></span>  
  
 <span data-ttu-id="286c7-179">배열 요소 형식은 형식 라이브러리에서 결정되고 가져오는 동안 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="286c7-179">The array element type is determined from the type library and preserved during the import.</span></span> <span data-ttu-id="286c7-180">매개 변수에 적용되는 같은 변환 규칙이 배열 요소에도 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="286c7-180">The same conversion rules that apply to parameters also apply to array elements.</span></span> <span data-ttu-id="286c7-181">예를 들어 **LPStr** 형식 배열은 **String** 형식 배열이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="286c7-181">For example, an array of **LPStr** types becomes an array of **String** types.</span></span> <span data-ttu-id="286c7-182">Tlbimp.exe는 배열 형식을 캡처하고 <xref:System.Runtime.InteropServices.MarshalAsAttribute> 특성을 매개 변수에 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="286c7-182">Tlbimp.exe captures the array element type and applies the <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute to the parameter.</span></span>  
  
 <span data-ttu-id="286c7-183">배열 순위는 1과 같은 것으로 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="286c7-183">The array rank is assumed to equal 1.</span></span> <span data-ttu-id="286c7-184">순위가 1보다 크면 배열은 열 중심 순서에서 1차원 배열로 마샬링됩니다.</span><span class="sxs-lookup"><span data-stu-id="286c7-184">If the rank is greater than 1, the array is marshaled as a one-dimensional array in column-major order.</span></span> <span data-ttu-id="286c7-185">하한은 항상 0과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="286c7-185">The lower bound always equals 0.</span></span>  
  
 <span data-ttu-id="286c7-186">형식 라이브러리에는 고정 또는 가변 길이의 배열이 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="286c7-186">Type libraries can contain arrays of fixed or variable length.</span></span> <span data-ttu-id="286c7-187">형식 라이브러리에는 가변 길이 배열을 마샬링하는 데 필요한 정보가 없으므로 Tlbimp.exe는 형식 라이브러리에서 고정 길이 배열만 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="286c7-187">Tlbimp.exe can import only fixed-length arrays from type libraries because type libraries lack the information needed to marshal variable-length arrays.</span></span> <span data-ttu-id="286c7-188">고정 길이 배열에서 크기는 형식 라이브러리에서 가져오고 매개 변수에 적용되는 **MarshalAsAttribute**에서 캡처합니다.</span><span class="sxs-lookup"><span data-stu-id="286c7-188">With fixed-length arrays, the size is imported from the type library and captured in the **MarshalAsAttribute** that is applied to the parameter.</span></span>  
  
 <span data-ttu-id="286c7-189">다음 예제와 같이 가변 길이 배열이 포함된 형식 라이브러리를 수동으로 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="286c7-189">You must manually define type libraries containing variable-length arrays, as shown in the following example.</span></span>  
  
 <span data-ttu-id="286c7-190">**관리되지 않는 시그니처**</span><span class="sxs-lookup"><span data-stu-id="286c7-190">**Unmanaged signature**</span></span>  
  
```  
HRESULT New1(int ar[10]);  
HRESULT New2(double ar[10][20]);  
HRESULT New3(LPWStr ar[10]);  
```  
  
 <span data-ttu-id="286c7-191">**관리되는 시그니처**</span><span class="sxs-lookup"><span data-stu-id="286c7-191">**Managed signature**</span></span>  
  
```vb  
Sub New1(<MarshalAs(UnmanagedType.LPArray, SizeConst=10)> _  
   ar() As Integer)  
Sub New2(<MarshalAs(UnmanagedType.LPArray, SizeConst=200)> _  
   ar() As Double)  
Sub New2(<MarshalAs(UnmanagedType.LPArray, _  
   ArraySubType=UnmanagedType.LPWStr, SizeConst=10)> _  
   ar() As String)  
```  
  
```csharp  
void New1([MarshalAs(UnmanagedType.LPArray, SizeConst=10)] int[] ar);  
void New2([MarshalAs(UnmanagedType.LPArray, SizeConst=200)] double[] ar);  
void New2([MarshalAs(UnmanagedType.LPArray,   
   ArraySubType=UnmanagedType.LPWStr, SizeConst=10)] String[] ar);  
```  
  
 <span data-ttu-id="286c7-192">IDL(Interface Definition Language) 소스의 배열에 **size_is** 또는 **length_is** 특성을 적용하여 클라이언트에 크기를 전달할 수 있지만 MIDL(Microsoft 인터페이스 정의 언어) 컴파일러는 해당 정보를 형식 라이브러리에 전파하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="286c7-192">Although you can apply the **size_is** or **length_is** attributes to an array in Interface Definition Language (IDL) source to convey the size to a client, the Microsoft Interface Definition Language (MIDL) compiler does not propagate that information to the type library.</span></span> <span data-ttu-id="286c7-193">크기를 모르면 interop 마샬링 서비스가 배열 요소를 마샬링할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="286c7-193">Without knowing the size, the interop marshaling service cannot marshal the array elements.</span></span> <span data-ttu-id="286c7-194">따라서 가변 길이 배열은 참조 인수로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="286c7-194">Consequently, variable-length arrays are imported as reference arguments.</span></span> <span data-ttu-id="286c7-195">예:</span><span class="sxs-lookup"><span data-stu-id="286c7-195">For example:</span></span>  
  
 <span data-ttu-id="286c7-196">**관리되지 않는 시그니처**</span><span class="sxs-lookup"><span data-stu-id="286c7-196">**Unmanaged signature**</span></span>  
  
```  
HRESULT New1(int ar[]);  
HRESULT New2(int ArSize, [size_is(ArSize)] double ar[]);  
HRESULT New3(int ElemCnt, [length_is(ElemCnt)] LPStr ar[]);  
```  
  
 <span data-ttu-id="286c7-197">**관리되는 시그니처**</span><span class="sxs-lookup"><span data-stu-id="286c7-197">**Managed signature**</span></span>  
  
```vb  
Sub New1(ByRef ar As Integer)  
Sub New2(ByRef ar As Double)  
Sub New3(ByRef ar As String)  
```  
  
```csharp  
void New1(ref int ar);    
void New2(ref double ar);    
void New3(ref String ar);   
```  
  
 <span data-ttu-id="286c7-198">Tlbimp.exe에서 생성된 MSIL(Microsoft Intermediate Language) 코드를 편집하고 다시 컴파일하여 마샬러에 배열을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="286c7-198">You can provide the marshaler with the array size by editing the Microsoft intermediate language (MSIL) code produced by Tlbimp.exe and then recompiling it.</span></span> <span data-ttu-id="286c7-199">MSIL 코드를 수정하는 방법에 대한 자세한 내용은 [런타임 호출 가능 래퍼 사용자 지정](http://msdn.microsoft.com/library/4652beaf-77d0-4f37-9687-ca193288c0be)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="286c7-199">For details about how to modify MSIL code, see [Customizing Runtime Callable Wrappers](http://msdn.microsoft.com/library/4652beaf-77d0-4f37-9687-ca193288c0be).</span></span> <span data-ttu-id="286c7-200">배열의 요소 수를 지정하려면 다음 방법 중 하나로 <xref:System.Runtime.InteropServices.MarshalAsAttribute> 형식을 관리되는 메서드 정의의 배열 매개 변수에 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="286c7-200">To indicate the number of elements in the array, apply the <xref:System.Runtime.InteropServices.MarshalAsAttribute> type to the array parameter of the managed method definition in one of the following ways:</span></span>  
  
-   <span data-ttu-id="286c7-201">배열의 요소 수가 포함된 또 다른 매개 변수를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="286c7-201">Identify another parameter that contains the number of elements in the array.</span></span> <span data-ttu-id="286c7-202">매개 변수는 위치로 식별되고 첫 번째 매개 변수는 0입니다.</span><span class="sxs-lookup"><span data-stu-id="286c7-202">The parameters are identified by position, starting with the first parameter as number 0.</span></span>     
  
    ```vb  
    Sub [New](ElemCnt As Integer, _  
       \<MarshalAs(UnmanagedType.LPArray, SizeParamIndex:=1)> _  
       ar() As Integer)  
    ```  
  
    ```csharp  
    void New(  
       int ElemCnt,   
       [MarshalAs(UnmanagedType.LPArray, SizeParamIndex=0)] int[] ar );  
    ```  
  
-   <span data-ttu-id="286c7-203">배열 크기를 상수로 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="286c7-203">Define the size of the array as a constant.</span></span> <span data-ttu-id="286c7-204">예:</span><span class="sxs-lookup"><span data-stu-id="286c7-204">For example:</span></span>  
  
    ```vb  
    Sub [New](\<MarshalAs(UnmanagedType.LPArray, SizeConst:=128)> _  
       ar() As Integer)  
    ```  
  
    ```csharp  
    void New(  
       [MarshalAs(UnmanagedType.LPArray, SizeConst=128)] int[] ar );  
    ```  
  
 <span data-ttu-id="286c7-205">비관리 코드에서 관리 코드로 배열을 마샬링할 경우 마샬러는 매개 변수와 연결된 **MarshalAsAttribute**를 확인하여 배열 크기를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="286c7-205">When marshaling arrays from unmanaged code to managed code, the marshaler checks the **MarshalAsAttribute** associated with the parameter to determine the array size.</span></span> <span data-ttu-id="286c7-206">배열 크기를 지정하지 않으면 하나의 요소만 마샬링됩니다.</span><span class="sxs-lookup"><span data-stu-id="286c7-206">If the array size is not specified, only one element is marshaled.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="286c7-207">**MarshalAsAttribute**는 관리 배열을 비관리 코드에 마샬링하는 작업에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="286c7-207">The **MarshalAsAttribute** has no effect on marshaling managed arrays to unmanaged code.</span></span> <span data-ttu-id="286c7-208">해당 방향의 배열 크기는 검사에 의해 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="286c7-208">In that direction, the array size is determined by examination.</span></span> <span data-ttu-id="286c7-209">관리되는 배열의 하위 집합을 마샬링할 방법은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="286c7-209">There is no way to marshal a subset of a managed array.</span></span>  
  
 <span data-ttu-id="286c7-210">interop 마샬러는 **CoTaskMemAlloc** 및 **CoTaskMemFree** 메서드를 사용하여 메모리를 할당 및 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="286c7-210">The interop marshaler uses the **CoTaskMemAlloc** and **CoTaskMemFree** methods to allocate and retrieve memory.</span></span> <span data-ttu-id="286c7-211">비관리 코드에서 수행되는 메모리 할당에는 이러한 메서드도 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="286c7-211">Memory allocation performed by unmanaged code must also use these methods.</span></span>  
  
<a name="cpcondefaultmarshalingforarraysanchor4"></a>   
## <a name="passing-arrays-to-com"></a><span data-ttu-id="286c7-212">COM에 배열 전달</span><span class="sxs-lookup"><span data-stu-id="286c7-212">Passing Arrays to COM</span></span>  
 <span data-ttu-id="286c7-213">모든 관리되는 배열 형식은 관리 코드에서 비관리 코드로 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="286c7-213">All managed array types can be passed to unmanaged code from managed code.</span></span> <span data-ttu-id="286c7-214">다음 표와 같이 관리되는 형식과 이 형식에 적용되는 특성에 따라 배열에는 안전 배열 또는 C 스타일 배열로 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="286c7-214">Depending on the managed type and the attributes applied to it, the array can be accessed as a safe array or a C-style array, as shown in the following table.</span></span>  
  
|<span data-ttu-id="286c7-215">관리되는 배열 형식</span><span class="sxs-lookup"><span data-stu-id="286c7-215">Managed array type</span></span>|<span data-ttu-id="286c7-216">내보내기 형식</span><span class="sxs-lookup"><span data-stu-id="286c7-216">Exported as</span></span>|  
|------------------------|-----------------|  
|<span data-ttu-id="286c7-217">**ELEMENT_TYPE_SZARRAY** **\<** *type* **>**</span><span class="sxs-lookup"><span data-stu-id="286c7-217">**ELEMENT_TYPE_SZARRAY** **\<** *type* **>**</span></span>|<span data-ttu-id="286c7-218"><xref:System.Runtime.InteropServices.UnmanagedType> **.SafeArray(** *type* **)**</span><span class="sxs-lookup"><span data-stu-id="286c7-218"><xref:System.Runtime.InteropServices.UnmanagedType> **.SafeArray(** *type* **)**</span></span><br /><br /> <span data-ttu-id="286c7-219">**UnmanagedType.LPArray**</span><span class="sxs-lookup"><span data-stu-id="286c7-219">**UnmanagedType.LPArray**</span></span><br /><br /> <span data-ttu-id="286c7-220">형식은 시그니처로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="286c7-220">Type is provided in the signature.</span></span> <span data-ttu-id="286c7-221">순위는 항상 1이고 하한은 항상 0입니다.</span><span class="sxs-lookup"><span data-stu-id="286c7-221">Rank is always 1, lower bound is always 0.</span></span> <span data-ttu-id="286c7-222">크기는 항상 런타임에 알려집니다.</span><span class="sxs-lookup"><span data-stu-id="286c7-222">Size is always known at run time.</span></span>|  
|<span data-ttu-id="286c7-223">**ELEMENT_TYPE_ARRAY** **\<** *type* **>** **\<** *rank* **>**[**\<** *bounds* **>**]</span><span class="sxs-lookup"><span data-stu-id="286c7-223">**ELEMENT_TYPE_ARRAY** **\<** *type* **>** **\<** *rank* **>**[**\<** *bounds* **>**]</span></span>|<span data-ttu-id="286c7-224">**UnmanagedType.SafeArray(** *type* **)**</span><span class="sxs-lookup"><span data-stu-id="286c7-224">**UnmanagedType.SafeArray(** *type* **)**</span></span><br /><br /> <span data-ttu-id="286c7-225">**UnmanagedType.LPArray**</span><span class="sxs-lookup"><span data-stu-id="286c7-225">**UnmanagedType.LPArray**</span></span><br /><br /> <span data-ttu-id="286c7-226">형식, 순위, 경계는 시그니처로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="286c7-226">Type, rank, bounds are provided in the signature.</span></span> <span data-ttu-id="286c7-227">크기는 항상 런타임에 알려집니다.</span><span class="sxs-lookup"><span data-stu-id="286c7-227">Size is always known at run time.</span></span>|  
|<span data-ttu-id="286c7-228">**ELEMENT_TYPE_CLASS** **\<**<xref:System.Array?displayProperty=nameWithType>**>**</span><span class="sxs-lookup"><span data-stu-id="286c7-228">**ELEMENT_TYPE_CLASS** **\<**<xref:System.Array?displayProperty=nameWithType>**>**</span></span>|<span data-ttu-id="286c7-229">**UT_Interface**</span><span class="sxs-lookup"><span data-stu-id="286c7-229">**UT_Interface**</span></span><br /><br /> <span data-ttu-id="286c7-230">**UnmanagedType.SafeArray(** *type* **)**</span><span class="sxs-lookup"><span data-stu-id="286c7-230">**UnmanagedType.SafeArray(** *type* **)**</span></span><br /><br /> <span data-ttu-id="286c7-231">형식, 순위, 경계 및 크기는 항상 런타임에 알려집니다.</span><span class="sxs-lookup"><span data-stu-id="286c7-231">Type, rank, bounds, and size are always known at run time.</span></span>|  
  
 <span data-ttu-id="286c7-232">LPSTR 또는 LPWSTR이 포함된 구조체 배열에 관련된 OLE 자동화에는 제한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="286c7-232">There is a limitation in OLE Automation relating to arrays of structures that contain LPSTR or LPWSTR.</span></span>  <span data-ttu-id="286c7-233">따라서 **String** 필드는 **UnmanagedType.BSTR**로 마샬링되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="286c7-233">Therefore, **String** fields have to be marshaled as **UnmanagedType.BSTR**.</span></span> <span data-ttu-id="286c7-234">그렇지 않으면 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="286c7-234">Otherwise, an exception will be thrown.</span></span>  
  
### <a name="elementtypeszarray"></a><span data-ttu-id="286c7-235">ELEMENT_TYPE_SZARRAY</span><span class="sxs-lookup"><span data-stu-id="286c7-235">ELEMENT_TYPE_SZARRAY</span></span>  
 <span data-ttu-id="286c7-236">**ELEMENT_TYPE_SZARRAY** 매개 변수(1차원 배열)가 포함된 메서드를 .NET 어셈블리에서 형식 라이브러리로 내보내면 배열 매개 변수가 지정된 형식의 **SAFEARRAY**로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="286c7-236">When a method containing an **ELEMENT_TYPE_SZARRAY** parameter (one-dimensional array) is exported from a .NET assembly to a type library, the array parameter is converted to a **SAFEARRAY** of a given type.</span></span> <span data-ttu-id="286c7-237">같은 변환 규칙이 배열 요소 형식에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="286c7-237">The same conversion rules apply to the array element types.</span></span> <span data-ttu-id="286c7-238">관리되는 배열의 콘텐츠는 관리되는 메모리에서 **SAFEARRAY**로 자동으로 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="286c7-238">The contents of the managed array are automatically copied from managed memory into the **SAFEARRAY**.</span></span> <span data-ttu-id="286c7-239">예:</span><span class="sxs-lookup"><span data-stu-id="286c7-239">For example:</span></span>  
  
#### <a name="managed-signature"></a><span data-ttu-id="286c7-240">관리되는 시그니처</span><span class="sxs-lookup"><span data-stu-id="286c7-240">Managed signature</span></span>  
  
```vb  
Sub [New](ar() As Long)  
Sub [New](ar() As String)  
```  
  
```csharp  
void New(long[] ar );  
void New(String[] ar );  
```  
  
#### <a name="unmanaged-signature"></a><span data-ttu-id="286c7-241">관리되지 않는 서명</span><span class="sxs-lookup"><span data-stu-id="286c7-241">Unmanaged signature</span></span>  
  
```  
HRESULT New([in] SAFEARRAY( long ) ar);   
HRESULT New([in] SAFEARRAY( BSTR ) ar);  
```  
  
 <span data-ttu-id="286c7-242">안전 배열의 순위는 항상 1이고 하한은 항상 0입니다.</span><span class="sxs-lookup"><span data-stu-id="286c7-242">The rank of the safe arrays is always 1 and the lower bound is always 0.</span></span> <span data-ttu-id="286c7-243">크기는 런타임에 전달 중인 관리되는 배열 크기에 따라 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="286c7-243">The size is determined at run time by the size of the managed array being passed.</span></span>  
  
 <span data-ttu-id="286c7-244"><xref:System.Runtime.InteropServices.MarshalAsAttribute> 특성을 사용하여 배열을 C 스타일 배열로 마샬링할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="286c7-244">The array can also be marshaled as a C-style array by using the <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute.</span></span> <span data-ttu-id="286c7-245">예:</span><span class="sxs-lookup"><span data-stu-id="286c7-245">For example:</span></span>  
  
#### <a name="managed-signature"></a><span data-ttu-id="286c7-246">관리되는 시그니처</span><span class="sxs-lookup"><span data-stu-id="286c7-246">Managed signature</span></span>  
  
```vb  
Sub [New](<MarshalAs(UnmanagedType.LPArray, SizeParamIndex:=1)> _  
   ar() As Long, size as Integer)  
Sub [New](<MarshalAs(UnmanagedType.LPArray, SizeParamIndex:=1)> _  
   ar() As String, size as Integer)  
Sub [New](<MarshalAs(UnmanagedType.LPArray, _  
   ArraySubType= UnmanagedType.LPStr, SizeParamIndex:=1)> _  
   ar() As String, size as Integer)  
```  
  
```csharp  
void New([MarshalAs(UnmanagedType.LPArray, SizeParamIndex=1)]   
   long [] ar, int size );  
void New([MarshalAs(UnmanagedType.LPArray, SizeParamIndex=1)]   
   String [] ar, int size );  
void New([MarshalAs(UnmanagedType.LPArray, ArraySubType=   
   UnmanagedType.LPStr, SizeParamIndex=1)]   
   String [] ar, int size );  
```  
  
#### <a name="unmanaged-signature"></a><span data-ttu-id="286c7-247">관리되지 않는 서명</span><span class="sxs-lookup"><span data-stu-id="286c7-247">Unmanaged signature</span></span>  
  
```  
HRESULT New(long ar[]);   
HRESULT New(BSTR ar[]);   
HRESULT New(LPStr ar[]);  
```  
  
 <span data-ttu-id="286c7-248">마샬러에는 배열을 마샬링하는 데 필요한 길이 정보가 있지만 배열 길이는 대개 호출 수신자에게 길이를 전달하기 위한 개별 인수로 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="286c7-248">Although the marshaler has the length information needed to marshal the array, the array length is usually passed as a separate argument to convey the length to the callee.</span></span>  
  
### <a name="elementtypearray"></a><span data-ttu-id="286c7-249">ELEMENT_TYPE_ARRAY</span><span class="sxs-lookup"><span data-stu-id="286c7-249">ELEMENT_TYPE_ARRAY</span></span>  
 <span data-ttu-id="286c7-250">**ELEMENT_TYPE_ARRAY** 매개 변수가 포함된 메서드를 .NET 어셈블리에서 형식 라이브러리로 내보내면 배열 매개 변수가 지정된 형식의 **SAFEARRAY**로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="286c7-250">When a method containing an **ELEMENT_TYPE_ARRAY** parameter is exported from a .NET assembly to a type library, the array parameter is converted to a **SAFEARRAY** of a given type.</span></span> <span data-ttu-id="286c7-251">관리되는 배열의 콘텐츠는 관리되는 메모리에서 **SAFEARRAY**로 자동으로 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="286c7-251">The contents of the managed array are automatically copied from managed memory into the **SAFEARRAY**.</span></span> <span data-ttu-id="286c7-252">예:</span><span class="sxs-lookup"><span data-stu-id="286c7-252">For example:</span></span>  
  
#### <a name="managed-signature"></a><span data-ttu-id="286c7-253">관리되는 시그니처</span><span class="sxs-lookup"><span data-stu-id="286c7-253">Managed signature</span></span>  
  
```vb  
Sub [New](ar(,) As Long)  
Sub [New](ar(,) As String)  
```  
  
```csharp  
void New( long [,] ar );  
void New( String [,] ar );  
```  
  
#### <a name="unmanaged-signature"></a><span data-ttu-id="286c7-254">관리되지 않는 서명</span><span class="sxs-lookup"><span data-stu-id="286c7-254">Unmanaged signature</span></span>  
  
```  
HRESULT New([in] SAFEARRAY( long ) ar);   
HRESULT New([in] SAFEARRAY( BSTR ) ar);  
```  
  
 <span data-ttu-id="286c7-255">안전 배열의 순위, 크기 및 경계는 런타임에 관리되는 배열의 특징에 따라 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="286c7-255">The rank, size, and bounds of the safe arrays are determined at run time by the characteristics of the managed array.</span></span>  
  
 <span data-ttu-id="286c7-256"><xref:System.Runtime.InteropServices.MarshalAsAttribute> 특성을 적용하여 배열을 C 스타일 배열로 마샬링할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="286c7-256">The array can also be marshaled as a C-style array by applying the <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute.</span></span> <span data-ttu-id="286c7-257">예:</span><span class="sxs-lookup"><span data-stu-id="286c7-257">For example:</span></span>  
  
#### <a name="managed-signature"></a><span data-ttu-id="286c7-258">관리되는 시그니처</span><span class="sxs-lookup"><span data-stu-id="286c7-258">Managed signature</span></span>  
  
```vb  
Sub [New](<MarshalAs(UnmanagedType.LPARRAY, SizeParamIndex:=1)> _  
   ar(,) As Long, size As Integer)  
Sub [New](<MarshalAs(UnmanagedType.LPARRAY, _  
   ArraySubType:=UnmanagedType.LPStr, SizeParamIndex:=1)> _  
   ar(,) As String, size As Integer)  
```  
  
```csharp  
void New([MarshalAs(UnmanagedType.LPARRAY, SizeParamIndex=1)]   
   long [,] ar, int size );  
void New([MarshalAs(UnmanagedType.LPARRAY,   
   ArraySubType= UnmanagedType.LPStr, SizeParamIndex=1)]   
   String [,] ar, int size );  
```  
  
#### <a name="unmanaged-signature"></a><span data-ttu-id="286c7-259">관리되지 않는 서명</span><span class="sxs-lookup"><span data-stu-id="286c7-259">Unmanaged signature</span></span>  
  
```  
HRESULT New(long ar[]);   
HRESULT New(LPStr ar[]);  
```  
  
 <span data-ttu-id="286c7-260">중첩 배열은 마샬링할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="286c7-260">Nested arrays cannot be marshaled.</span></span> <span data-ttu-id="286c7-261">예를 들어 다음 시그니처는 [형식 라이브러리 내보내기(Tlbexp.exe)](../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md)를 통해 내보낼 경우 오류를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="286c7-261">For example, the following signature generates an error when exported with the [Type Library Exporter (Tlbexp.exe)](../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md).</span></span>  
  
#### <a name="managed-signature"></a><span data-ttu-id="286c7-262">관리되는 시그니처</span><span class="sxs-lookup"><span data-stu-id="286c7-262">Managed signature</span></span>  
  
```vb  
Sub [New](ar()()() As Long)  
```  
  
```csharp  
void New(long [][][] ar );  
```  
  
### <a name="elementtypeclass-systemarray"></a><span data-ttu-id="286c7-263">ELEMENT_TYPE_CLASS \<System.Array></span><span class="sxs-lookup"><span data-stu-id="286c7-263">ELEMENT_TYPE_CLASS \<System.Array></span></span>  
 <span data-ttu-id="286c7-264"><xref:System.Array?displayProperty=nameWithType> 매개 변수가 포함된 메서드를 .NET 어셈블리에서 형식 라이브러리로 내보내면 배열 매개 변수가 **_Array** 인터페이스로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="286c7-264">When a method containing a <xref:System.Array?displayProperty=nameWithType> parameter is exported from a .NET assembly to a type library, the array parameter is converted to an **_Array** interface.</span></span> <span data-ttu-id="286c7-265">관리되는 배열의 콘텐츠는 **_Array** 인터페이스의 메서드 및 속성을 통해서만 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="286c7-265">The contents of the managed array are accessible only through the methods and properties of the **_Array** interface.</span></span> <span data-ttu-id="286c7-266"><xref:System.Runtime.InteropServices.MarshalAsAttribute> 특성을 사용하여 **System.Array**를 **SAFEARRAY**로 마샬링할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="286c7-266">**System.Array** can also be marshaled as a **SAFEARRAY** by using the <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute.</span></span> <span data-ttu-id="286c7-267">안전 배열로 마샬링될 경우 배열 요소는 변형으로 마샬링됩니다.</span><span class="sxs-lookup"><span data-stu-id="286c7-267">When marshaled as a safe array, the array elements are marshaled as variants.</span></span> <span data-ttu-id="286c7-268">예:</span><span class="sxs-lookup"><span data-stu-id="286c7-268">For example:</span></span>  
  
#### <a name="managed-signature"></a><span data-ttu-id="286c7-269">관리되는 시그니처</span><span class="sxs-lookup"><span data-stu-id="286c7-269">Managed signature</span></span>  
  
```vb  
Sub New1( ar As System.Array )  
Sub New2( <MarshalAs(UnmanagedType.Safe array)> ar As System.Array )  
```  
  
```csharp  
void New1( System.Array ar );  
void New2( [MarshalAs(UnmanagedType.Safe array)] System.Array ar );  
```  
  
#### <a name="unmanaged-signature"></a><span data-ttu-id="286c7-270">관리되지 않는 서명</span><span class="sxs-lookup"><span data-stu-id="286c7-270">Unmanaged signature</span></span>  
  
```  
HRESULT New([in] _Array *ar);   
HRESULT New([in] SAFEARRAY(VARIANT) ar);  
```  
  
### <a name="arrays-within-structures"></a><span data-ttu-id="286c7-271">구조체가 있는 배열</span><span class="sxs-lookup"><span data-stu-id="286c7-271">Arrays within Structures</span></span>  
 <span data-ttu-id="286c7-272">관리되지 않는 구조체에는 포함된 배열이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="286c7-272">Unmanaged structures can contain embedded arrays.</span></span> <span data-ttu-id="286c7-273">기본적으로 이러한 포함된 배열 필드는 SAFEARRAY로 마샬링됩니다.</span><span class="sxs-lookup"><span data-stu-id="286c7-273">By default, these embedded array fields are marshaled as a SAFEARRAY.</span></span> <span data-ttu-id="286c7-274">다음 예제에서 `s1`은 구조체 자체 내에서 직접 할당되는 포함된 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="286c7-274">In the following example, `s1` is an embedded array that is allocated directly within the structure itself.</span></span>  
  
#### <a name="unmanaged-representation"></a><span data-ttu-id="286c7-275">관리되지 않는 표현</span><span class="sxs-lookup"><span data-stu-id="286c7-275">Unmanaged representation</span></span>  
  
```  
struct MyStruct {  
    short s1[128];  
}  
```  
  
 <span data-ttu-id="286c7-276">배열은 <xref:System.Runtime.InteropServices.MarshalAsAttribute> 필드를 설정해야 하는 <xref:System.Runtime.InteropServices.UnmanagedType>으로 마샬링될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="286c7-276">Arrays can be marshaled as <xref:System.Runtime.InteropServices.UnmanagedType>, which requires you to set the <xref:System.Runtime.InteropServices.MarshalAsAttribute> field.</span></span> <span data-ttu-id="286c7-277">크기는 상수로만 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="286c7-277">The size can be set only as a constant.</span></span> <span data-ttu-id="286c7-278">다음 코드에서는 `MyStruct`의 해당 관리되는 정의를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="286c7-278">The following code shows the corresponding managed definition of `MyStruct`.</span></span>  
  
```vb  
Public Structure <StructLayout(LayoutKind.Sequential)> MyStruct  
   Public <MarshalAs(UnmanagedType.ByValArray, SizeConst := 128)> _  
     s1() As Short  
End Structure  
```  
  
```csharp  
[StructLayout(LayoutKind.Sequential)]  
public struct MyStruct {  
   [MarshalAs(UnmanagedType.ByValArray, SizeConst=128)] public short[] s1;  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="286c7-279">참고 항목</span><span class="sxs-lookup"><span data-stu-id="286c7-279">See Also</span></span>  
 [<span data-ttu-id="286c7-280">기본 마샬링 동작</span><span class="sxs-lookup"><span data-stu-id="286c7-280">Default Marshaling Behavior</span></span>](../../../docs/framework/interop/default-marshaling-behavior.md)  
 [<span data-ttu-id="286c7-281">Blittable 형식 및 비 Blittable 형식</span><span class="sxs-lookup"><span data-stu-id="286c7-281">Blittable and Non-Blittable Types</span></span>](../../../docs/framework/interop/blittable-and-non-blittable-types.md)  
 [<span data-ttu-id="286c7-282">방향 특성</span><span class="sxs-lookup"><span data-stu-id="286c7-282">Directional Attributes</span></span>](http://msdn.microsoft.com/library/241ac5b5-928e-4969-8f58-1dbc048f9ea2)  
 [<span data-ttu-id="286c7-283">복사 및 고정</span><span class="sxs-lookup"><span data-stu-id="286c7-283">Copying and Pinning</span></span>](../../../docs/framework/interop/copying-and-pinning.md)
