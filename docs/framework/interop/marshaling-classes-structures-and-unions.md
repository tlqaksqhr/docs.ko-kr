---
title: 클래스, 구조체 및 공용 구조체 마샬링
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data marshaling, classes
- marshaling, unions
- marshaling, structures
- marshaling, samples
- data marshaling, structures
- platform invoke, marshaling data
- marshaling, classes
- data marshaling, unions
- data marshaling, samples
- data marshaling, platform invoke
- marshaling, platform invoke
ms.assetid: 027832a2-9b43-4fd9-9b45-7f4196261a4e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: be4c15f1093f359eeb9e742464b9d9e1dd5c756e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33393395"
---
# <a name="marshaling-classes-structures-and-unions"></a><span data-ttu-id="299ec-102">클래스, 구조체 및 공용 구조체 마샬링</span><span class="sxs-lookup"><span data-stu-id="299ec-102">Marshaling Classes, Structures, and Unions</span></span>
<span data-ttu-id="299ec-103">.NET Framework에서는 클래스와 구조체가 서로 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="299ec-103">Classes and structures are similar in the .NET Framework.</span></span> <span data-ttu-id="299ec-104">둘 다 필드, 속성 및 이벤트를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="299ec-104">Both can have fields, properties, and events.</span></span> <span data-ttu-id="299ec-105">또한 정적 및 비정적 메서드를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="299ec-105">They can also have static and nonstatic methods.</span></span> <span data-ttu-id="299ec-106">한 가지 주목할 만한 차이점은 구조체는 값 형식이고 클래스는 참조 형식이라는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="299ec-106">One notable difference is that structures are value types and classes are reference types.</span></span>  
  
 <span data-ttu-id="299ec-107">다음 표에서는 클래스, 구조체 및 공용 구조체에 대한 마샬링 옵션을 나열하고 용도를 설명하며 해당하는 플랫폼 호출 샘플에 대한 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="299ec-107">The following table lists marshaling options for classes, structures, and unions; describes their usage; and provides a link to the corresponding platform invoke sample.</span></span>  
  
|<span data-ttu-id="299ec-108">형식</span><span class="sxs-lookup"><span data-stu-id="299ec-108">Type</span></span>|<span data-ttu-id="299ec-109">설명</span><span class="sxs-lookup"><span data-stu-id="299ec-109">Description</span></span>|<span data-ttu-id="299ec-110">샘플</span><span class="sxs-lookup"><span data-stu-id="299ec-110">Sample</span></span>|  
|----------|-----------------|------------|  
|<span data-ttu-id="299ec-111">값 방식 클래스.</span><span class="sxs-lookup"><span data-stu-id="299ec-111">Class by value.</span></span>|<span data-ttu-id="299ec-112">관리되는 사례와 같이 정수 멤버를 In/Out 매개 변수로 사용하여 클래스를 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="299ec-112">Passes a class with integer members as an In/Out parameter, like the managed case.</span></span>|<span data-ttu-id="299ec-113">SysTime 샘플</span><span class="sxs-lookup"><span data-stu-id="299ec-113">SysTime sample</span></span>|  
|<span data-ttu-id="299ec-114">값 방식 구조체.</span><span class="sxs-lookup"><span data-stu-id="299ec-114">Structure by value.</span></span>|<span data-ttu-id="299ec-115">구조체를 In 매개 변수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="299ec-115">Passes structures as In parameters.</span></span>|<span data-ttu-id="299ec-116">Structures 샘플</span><span class="sxs-lookup"><span data-stu-id="299ec-116">Structures sample</span></span>|  
|<span data-ttu-id="299ec-117">참조 방식 구조체.</span><span class="sxs-lookup"><span data-stu-id="299ec-117">Structure by reference.</span></span>|<span data-ttu-id="299ec-118">구조체를 In/Out 매개 변수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="299ec-118">Passes structures as In/Out parameters.</span></span>|<span data-ttu-id="299ec-119">OSInfo 샘플</span><span class="sxs-lookup"><span data-stu-id="299ec-119">OSInfo sample</span></span>|  
|<span data-ttu-id="299ec-120">중첩 구조체를 포함하는 구조체(결합).</span><span class="sxs-lookup"><span data-stu-id="299ec-120">Structure with nested structures (flattened).</span></span>|<span data-ttu-id="299ec-121">관리되지 않는 함수에서 중첩 구조체를 포함하는 구조체를 나타내는 클래스를 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="299ec-121">Passes a class that represents a structure with nested structures in the unmanaged function.</span></span> <span data-ttu-id="299ec-122">관리되는 프로토타입에서는 구조체가 하나의 큰 구조체로 결합됩니다.</span><span class="sxs-lookup"><span data-stu-id="299ec-122">The structure is flattened to one big structure in the managed prototype.</span></span>|<span data-ttu-id="299ec-123">FindFile 샘플</span><span class="sxs-lookup"><span data-stu-id="299ec-123">FindFile sample</span></span>|  
|<span data-ttu-id="299ec-124">다른 구조체에 대한 포인터를 포함하는 구조체.</span><span class="sxs-lookup"><span data-stu-id="299ec-124">Structure with a pointer to another structure.</span></span>|<span data-ttu-id="299ec-125">두 번째 구조체에 대한 포인터를 멤버로 포함하는 구조체를 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="299ec-125">Passes a structure that contains a pointer to a second structure as a member.</span></span>|<span data-ttu-id="299ec-126">구조체 샘플</span><span class="sxs-lookup"><span data-stu-id="299ec-126">Structures Sample</span></span>|  
|<span data-ttu-id="299ec-127">값 형식 정수를 포함하는 구조체 배열.</span><span class="sxs-lookup"><span data-stu-id="299ec-127">Array of structures with integers by value.</span></span>|<span data-ttu-id="299ec-128">정수만 포함하는 구조체 배열을 In/Out 매개 변수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="299ec-128">Passes an array of structures that contain only integers as an In/Out parameter.</span></span> <span data-ttu-id="299ec-129">배열의 멤버를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="299ec-129">Members of the array can be changed.</span></span>|<span data-ttu-id="299ec-130">배열 샘플</span><span class="sxs-lookup"><span data-stu-id="299ec-130">Arrays Sample</span></span>|  
|<span data-ttu-id="299ec-131">참조 형식 정수 및 문자열을 포함하는 구조체 배열.</span><span class="sxs-lookup"><span data-stu-id="299ec-131">Array of structures with integers and strings by reference.</span></span>|<span data-ttu-id="299ec-132">정수 및 문자열을 포함하는 구조체 배열을 Out 매개 변수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="299ec-132">Passes an array of structures that contain integers and strings as an Out parameter.</span></span> <span data-ttu-id="299ec-133">호출된 함수가 배열에 대한 메모리를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="299ec-133">The called function allocates memory for the array.</span></span>|<span data-ttu-id="299ec-134">OutArrayOfStructs 샘플</span><span class="sxs-lookup"><span data-stu-id="299ec-134">OutArrayOfStructs Sample</span></span>|  
|<span data-ttu-id="299ec-135">값 형식을 포함하는 공용 구조체.</span><span class="sxs-lookup"><span data-stu-id="299ec-135">Unions with value types.</span></span>|<span data-ttu-id="299ec-136">값 형식(정수 및 double)을 포함하는 공용 구조체를 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="299ec-136">Passes unions with value types (integer and double).</span></span>|<span data-ttu-id="299ec-137">Unions 샘플</span><span class="sxs-lookup"><span data-stu-id="299ec-137">Unions sample</span></span>|  
|<span data-ttu-id="299ec-138">혼합된 형식을 포함하는 공용 구조체.</span><span class="sxs-lookup"><span data-stu-id="299ec-138">Unions with mixed types.</span></span>|<span data-ttu-id="299ec-139">혼합된 형식(정수 및 문자열)을 포함하는 공용 구조체를 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="299ec-139">Passes unions with mixed types (integer and string).</span></span>|<span data-ttu-id="299ec-140">Unions 샘플</span><span class="sxs-lookup"><span data-stu-id="299ec-140">Unions sample</span></span>|  
|<span data-ttu-id="299ec-141">구조체의 null 값.</span><span class="sxs-lookup"><span data-stu-id="299ec-141">Null values in structure.</span></span>|<span data-ttu-id="299ec-142">값 형식에 대한 참조 대신 null 참조(Visual Basic에서는 **Nothing**)를 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="299ec-142">Passes a null reference (**Nothing** in Visual Basic) instead of a reference to a value type.</span></span>|<span data-ttu-id="299ec-143">HandleRef 샘플</span><span class="sxs-lookup"><span data-stu-id="299ec-143">HandleRef sample</span></span>|  
  
## <a name="structures-sample"></a><span data-ttu-id="299ec-144">Structures 샘플</span><span class="sxs-lookup"><span data-stu-id="299ec-144">Structures sample</span></span>  
 <span data-ttu-id="299ec-145">이 샘플에서는 두 번째 구조체를 가리키는 구조체, 포함된 구조체가 있는 구조체 및 포함된 배열이 있는 구조체를 전달하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="299ec-145">This sample demonstrates how to pass a structure that points to a second structure, pass a structure with an embedded structure, and pass a structure with an embedded array.</span></span>  
  
 <span data-ttu-id="299ec-146">Structs 샘플에서는 원래 함수 선언과 함께 표시되는 다음과 같은 관리되지 않는 함수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="299ec-146">The Structs sample uses the following unmanaged functions, shown with their original function declaration:</span></span>  
  
-   <span data-ttu-id="299ec-147">PinvokeLib.dll에서 내보낸 **TestStructInStruct**.</span><span class="sxs-lookup"><span data-stu-id="299ec-147">**TestStructInStruct** exported from PinvokeLib.dll.</span></span>  
  
    ```  
    int TestStructInStruct(MYPERSON2* pPerson2);  
    ```  
  
-   <span data-ttu-id="299ec-148">PinvokeLib.dll에서 내보낸 **TestStructInStruct3**.</span><span class="sxs-lookup"><span data-stu-id="299ec-148">**TestStructInStruct3** exported from PinvokeLib.dll.</span></span>  
  
    ```  
    void TestStructInStruct3(MYPERSON3 person3);  
    ```  
  
-   <span data-ttu-id="299ec-149">PinvokeLib.dll에서 내보낸 **TestArrayInStruct**.</span><span class="sxs-lookup"><span data-stu-id="299ec-149">**TestArrayInStruct** exported from PinvokeLib.dll.</span></span>  
  
    ```  
    void TestArrayInStruct( MYARRAYSTRUCT* pStruct );  
    ```  
  
 <span data-ttu-id="299ec-150">[PinvokeLib.dll](https://msdn.microsoft.com/library/5d1438d7-9946-489d-8ede-6c694a08f614(v=vs.100))은 앞에 나열된 함수 및 4개의 구조체(**MYPERSON**, **MYPERSON2**, **MYPERSON3** 및 **MYARRAYSTRUCT**)에 대한 구현을 포함하는 관리되지 않는 사용자 지정 라이브러리입니다.</span><span class="sxs-lookup"><span data-stu-id="299ec-150">[PinvokeLib.dll](https://msdn.microsoft.com/library/5d1438d7-9946-489d-8ede-6c694a08f614(v=vs.100)) is a custom unmanaged library that contains implementations for the previously listed functions and four structures: **MYPERSON**, **MYPERSON2**, **MYPERSON3**, and **MYARRAYSTRUCT**.</span></span> <span data-ttu-id="299ec-151">이러한 구조체에는 다음과 같은 요소가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="299ec-151">These structures contain the following elements:</span></span>  
  
```  
typedef struct _MYPERSON  
{  
   char* first;   
   char* last;   
} MYPERSON, *LP_MYPERSON;  
  
typedef struct _MYPERSON2  
{  
   MYPERSON* person;  
   int age;   
} MYPERSON2, *LP_MYPERSON2;  
  
typedef struct _MYPERSON3  
{  
   MYPERSON person;  
   int age;   
} MYPERSON3;  
  
typedef struct _MYARRAYSTRUCT  
{  
   bool flag;  
   int vals[ 3 ];   
} MYARRAYSTRUCT;  
```  
  
 <span data-ttu-id="299ec-152">관리되는 `MyPerson`, `MyPerson2`, `MyPerson3` 및 `MyArrayStruct` 구조체는 다음과 같은 특성을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="299ec-152">The managed `MyPerson`, `MyPerson2`, `MyPerson3`, and `MyArrayStruct` structures have the following characteristic:</span></span>  
  
-   <span data-ttu-id="299ec-153">`MyPerson`에는 문자열 멤버만 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="299ec-153">`MyPerson` contains only string members.</span></span> <span data-ttu-id="299ec-154">[CharSet](specifying-a-character-set.md) 필드는 관리되지 않는 함수에 전달되는 경우 문자열을 ANSI 형식으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="299ec-154">The [CharSet](specifying-a-character-set.md) field sets the strings to ANSI format when passed to the unmanaged function.</span></span>  
  
-   <span data-ttu-id="299ec-155">`MyPerson2`에는 `MyPerson` 구조체에 대한 **IntPtr**이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="299ec-155">`MyPerson2` contains an **IntPtr** to the `MyPerson` structure.</span></span> <span data-ttu-id="299ec-156">.NET Framework 응용 프로그램은 코드가 **안전하지 않은** 것으로 표시된 경우가 아니면 포인터를 사용하지 않으므로 **IntPtr** 형식이 관리되지 않는 구조체에 대한 원래 포인터를 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="299ec-156">The **IntPtr** type replaces the original pointer to the unmanaged structure because .NET Framework applications do not use pointers unless the code is marked **unsafe**.</span></span>  
  
-   <span data-ttu-id="299ec-157">`MyPerson3`에는 `MyPerson`이 포함된 구조체로 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="299ec-157">`MyPerson3` contains `MyPerson` as an embedded structure.</span></span> <span data-ttu-id="299ec-158">포함된 구조체의 요소를 기본 구조에 직접 배치하여 다른 구조체 내에 포함된 구조체를 결합하거나 이 샘플과 같이 포함된 구조체로 그대로 둘 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="299ec-158">A structure embedded within another structure can be flattened by placing the elements of the embedded structure directly into the main structure, or it can be left as an embedded structure, as is done in this sample.</span></span>  
  
-   <span data-ttu-id="299ec-159">`MyArrayStruct`에는 정수 배열이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="299ec-159">`MyArrayStruct` contains an array of integers.</span></span> <span data-ttu-id="299ec-160"><xref:System.Runtime.InteropServices.MarshalAsAttribute> 특성은 <xref:System.Runtime.InteropServices.UnmanagedType> 열거형 값을 배열의 요소 수를 나타내는 데 사용되는 **ByValArray**로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="299ec-160">The <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute sets the <xref:System.Runtime.InteropServices.UnmanagedType> enumeration value to **ByValArray**, which is used to indicate the number of elements in the array.</span></span>  
  
 <span data-ttu-id="299ec-161">이 샘플의 모든 구조체에는 <xref:System.Runtime.InteropServices.StructLayoutAttribute> 특성이 적용되어 멤버가 표시되는 순서대로 순차적으로 메모리에 정렬되게 합니다.</span><span class="sxs-lookup"><span data-stu-id="299ec-161">For all structures in this sample, the <xref:System.Runtime.InteropServices.StructLayoutAttribute> attribute is applied to ensure that the members are arranged in memory sequentially, in the order in which they appear.</span></span>  
  
 <span data-ttu-id="299ec-162">`LibWrap` 클래스에는 `App` 클래스가 호출하는 `TestStructInStruct`, `TestStructInStruct3` 및 `TestArrayInStruct` 메서드에 대한 관리되는 프로토타입이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="299ec-162">The `LibWrap` class contains managed prototypes for the `TestStructInStruct`, `TestStructInStruct3`, and `TestArrayInStruct` methods called by the `App` class.</span></span> <span data-ttu-id="299ec-163">각 프로토타입은 다음과 같이 단일 매개 변수를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="299ec-163">Each prototype declares a single parameter, as follows:</span></span>  
  
-   <span data-ttu-id="299ec-164">`TestStructInStruct`는 `MyPerson2` 형식에 대한 참조를 해당 매개 변수로 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="299ec-164">`TestStructInStruct` declares a reference to type `MyPerson2` as its parameter.</span></span>  
  
-   <span data-ttu-id="299ec-165">`TestStructInStruct3`은 `MyPerson3` 형식을 해당 매개 변수로 선언하고 매개 변수를 값으로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="299ec-165">`TestStructInStruct3` declares type `MyPerson3` as its parameter and passes the parameter by value.</span></span>  
  
-   <span data-ttu-id="299ec-166">`TestArrayInStruct`는 `MyArrayStruct` 형식에 대한 참조를 해당 매개 변수로 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="299ec-166">`TestArrayInStruct` declares a reference to type `MyArrayStruct` as its parameter.</span></span>  
  
 <span data-ttu-id="299ec-167">메서드에 대한 인수로서의 구조체는 매개 변수에 **ref**(Visual Basic에서는 **ByRef**) 키워드가 포함되지 않은 경우 값으로 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="299ec-167">Structures as arguments to methods are passed by value unless the parameter contains the **ref** (**ByRef** in Visual Basic) keyword.</span></span> <span data-ttu-id="299ec-168">예를 들어 `TestStructInStruct` 메서드는 `MyPerson2` 형식의 개체에 대한 참조(주소 값)를 비관리 코드에 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="299ec-168">For example, the `TestStructInStruct` method passes a reference (the value of an address) to an object of type `MyPerson2` to unmanaged code.</span></span> <span data-ttu-id="299ec-169">`MyPerson2`가 가리키는 구조체를 조작하기 위해 샘플에서는 지정된 크기의 버퍼를 만들고 <xref:System.Runtime.InteropServices.Marshal.AllocCoTaskMem%2A?displayProperty=nameWithType> 및 <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType> 메서드를 결합하여 해당 주소를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="299ec-169">To manipulate the structure that `MyPerson2` points to, the sample creates a buffer of a specified size and returns its address by combining the <xref:System.Runtime.InteropServices.Marshal.AllocCoTaskMem%2A?displayProperty=nameWithType> and <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="299ec-170">그런 다음 관리되는 구조체의 콘텐츠를 관리되지 않는 버퍼로 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="299ec-170">Next, the sample copies the content of the managed structure to the unmanaged buffer.</span></span> <span data-ttu-id="299ec-171">끝으로, <xref:System.Runtime.InteropServices.Marshal.PtrToStructure%2A?displayProperty=nameWithType> 메서드를 사용하여 관리되지 않는 버퍼의 데이터를 관리되는 개체로 마샬링하고 <xref:System.Runtime.InteropServices.Marshal.FreeCoTaskMem%2A?displayProperty=nameWithType> 메서드를 사용하여 관리되지 않는 메모리 블록을 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="299ec-171">Finally, the sample uses the <xref:System.Runtime.InteropServices.Marshal.PtrToStructure%2A?displayProperty=nameWithType> method to marshal data from the unmanaged buffer to a managed object and the <xref:System.Runtime.InteropServices.Marshal.FreeCoTaskMem%2A?displayProperty=nameWithType> method to free the unmanaged block of memory.</span></span>  
  
### <a name="declaring-prototypes"></a><span data-ttu-id="299ec-172">프로토타입 선언</span><span class="sxs-lookup"><span data-stu-id="299ec-172">Declaring Prototypes</span></span>  
 [!code-cpp[Conceptual.Interop.Marshaling#23](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/structures.cpp#23)]
 [!code-csharp[Conceptual.Interop.Marshaling#23](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/structures.cs#23)]
 [!code-vb[Conceptual.Interop.Marshaling#23](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/structures.vb#23)]  
  
### <a name="calling-functions"></a><span data-ttu-id="299ec-173">함수 호출</span><span class="sxs-lookup"><span data-stu-id="299ec-173">Calling Functions</span></span>  
 [!code-cpp[Conceptual.Interop.Marshaling#24](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/structures.cpp#24)]
 [!code-csharp[Conceptual.Interop.Marshaling#24](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/structures.cs#24)]
 [!code-vb[Conceptual.Interop.Marshaling#24](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/structures.vb#24)]  
  
## <a name="findfile-sample"></a><span data-ttu-id="299ec-174">FindFile 샘플</span><span class="sxs-lookup"><span data-stu-id="299ec-174">FindFile sample</span></span>  
 <span data-ttu-id="299ec-175">이 샘플에서는 포함된 두 번째 구조체를 포함하는 구조체를 관리되지 않는 함수에 전달하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="299ec-175">This sample demonstrates how to pass a structure that contains a second, embedded structure to an unmanaged function.</span></span> <span data-ttu-id="299ec-176">또한 <xref:System.Runtime.InteropServices.MarshalAsAttribute> 특성을 사용하여 구조체 내에서 고정 길이 배열을 선언하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="299ec-176">It also demonstrates how to use the <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute to declare a fixed-length array within the structure.</span></span> <span data-ttu-id="299ec-177">이 샘플에서는 포함된 구조체 요소가 부모 구조체에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="299ec-177">In this sample, the embedded structure elements are added to the parent structure.</span></span> <span data-ttu-id="299ec-178">결합되지 않는 포함된 구조체의 샘플은 [Structures 샘플](https://msdn.microsoft.com/library/96a62265-dcf9-4608-bc0a-1f762ab9f48e(v=vs.100))을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="299ec-178">For a sample of an embedded structure that is not flattened, see [Structures Sample](https://msdn.microsoft.com/library/96a62265-dcf9-4608-bc0a-1f762ab9f48e(v=vs.100)).</span></span>  
  
 <span data-ttu-id="299ec-179">FindFile 샘플에서는 원래 함수 선언과 함께 표시되는 다음과 같은 관리되지 않는 함수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="299ec-179">The FindFile sample uses the following unmanaged function, shown with its original function declaration:</span></span>  
  
-   <span data-ttu-id="299ec-180">Kernel32.dll에서 내보낸 **FindFirstFile**.</span><span class="sxs-lookup"><span data-stu-id="299ec-180">**FindFirstFile** exported from Kernel32.dll.</span></span>  
  
    ```  
    HANDLE FindFirstFile(LPCTSTR lpFileName, LPWIN32_FIND_DATA lpFindFileData);  
    ```  
  
 <span data-ttu-id="299ec-181">함수에 전달된 원래 구조체에는 다음과 같은 요소가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="299ec-181">The original structure passed to the function contains the following elements:</span></span>  
  
```  
typedef struct _WIN32_FIND_DATA   
{  
  DWORD    dwFileAttributes;   
  FILETIME ftCreationTime;   
  FILETIME ftLastAccessTime;   
  FILETIME ftLastWriteTime;   
  DWORD    nFileSizeHigh;   
  DWORD    nFileSizeLow;   
  DWORD    dwReserved0;   
  DWORD    dwReserved1;   
  TCHAR    cFileName[ MAX_PATH ];   
  TCHAR    cAlternateFileName[ 14 ];   
} WIN32_FIND_DATA, *PWIN32_FIND_DATA;  
```  
  
 <span data-ttu-id="299ec-182">이 샘플에서 `FindData` 클래스에는 원래 구조체 및 포함된 구조체의 각 요소에 해당하는 데이터 멤버가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="299ec-182">In this sample, the `FindData` class contains a corresponding data member for each element of the original structure and the embedded structure.</span></span> <span data-ttu-id="299ec-183">두 개의 원래 문자 버퍼 대신 이 클래스가 문자열을 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="299ec-183">In place of two original character buffers, the class substitutes strings.</span></span> <span data-ttu-id="299ec-184">**MarshalAsAttribute**는 <xref:System.Runtime.InteropServices.UnmanagedType> 열거형을 관리되지 않는 구조체 내에 표시되는 인라인 고정 길이 문자 배열을 식별하는 데 사용되는 **ByValTStr**로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="299ec-184">**MarshalAsAttribute** sets the <xref:System.Runtime.InteropServices.UnmanagedType> enumeration to **ByValTStr**, which is used to identify the inline, fixed-length character arrays that appear within the unmanaged structures.</span></span>  
  
 <span data-ttu-id="299ec-185">`LibWrap` 클래스에는 `FindData` 클래스를 매개 변수로 전달하는 `FindFirstFile` 메서드의 관리되는 프로토타입이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="299ec-185">The `LibWrap` class contains a managed prototype of the `FindFirstFile` method, which passes the `FindData` class as a parameter.</span></span> <span data-ttu-id="299ec-186">참조 형식인 클래스는 기본적으로 In 매개 변수로 전달되므로 <xref:System.Runtime.InteropServices.InAttribute> 및 <xref:System.Runtime.InteropServices.OutAttribute> 특성을 통해 매개 변수를 선언해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="299ec-186">The parameter must be declared with the <xref:System.Runtime.InteropServices.InAttribute> and <xref:System.Runtime.InteropServices.OutAttribute> attributes because classes, which are reference types, are passed as In parameters by default.</span></span>  
  
### <a name="declaring-prototypes"></a><span data-ttu-id="299ec-187">프로토타입 선언</span><span class="sxs-lookup"><span data-stu-id="299ec-187">Declaring Prototypes</span></span>  
 [!code-cpp[Conceptual.Interop.Marshaling#17](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/findfile.cpp#17)]
 [!code-csharp[Conceptual.Interop.Marshaling#17](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/findfile.cs#17)]
 [!code-vb[Conceptual.Interop.Marshaling#17](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/findfile.vb#17)]  
  
### <a name="calling-functions"></a><span data-ttu-id="299ec-188">함수 호출</span><span class="sxs-lookup"><span data-stu-id="299ec-188">Calling Functions</span></span>  
 [!code-cpp[Conceptual.Interop.Marshaling#18](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/findfile.cpp#18)]
 [!code-csharp[Conceptual.Interop.Marshaling#18](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/findfile.cs#18)]
 [!code-vb[Conceptual.Interop.Marshaling#18](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/findfile.vb#18)]  
  
## <a name="unions-sample"></a><span data-ttu-id="299ec-189">Unions 샘플</span><span class="sxs-lookup"><span data-stu-id="299ec-189">Unions sample</span></span>  
 <span data-ttu-id="299ec-190">이 샘플에서는 값 형식만 포함하는 구조체 및 값 형식과 문자열을 매개 변수로 포함하는 구조체를 공용 구조체가 필요한 관리되지 않는 함수에 전달하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="299ec-190">This sample demonstrates how to pass structures containing only value types, and structures containing a value type and a string as parameters to an unmanaged function expecting a union.</span></span> <span data-ttu-id="299ec-191">공용 구조체는 둘 이상의 변수가 공유할 수 있는 메모리 위치를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="299ec-191">A union represents a memory location that can be shared by two or more variables.</span></span>  
  
 <span data-ttu-id="299ec-192">Unions 샘플에서는 원래 함수 선언과 함께 표시되는 다음과 같은 관리되지 않는 함수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="299ec-192">The Unions sample uses the following unmanaged function, shown with its original function declaration:</span></span>  
  
-   <span data-ttu-id="299ec-193">PinvokeLib.dll에서 내보낸 **TestUnion**.</span><span class="sxs-lookup"><span data-stu-id="299ec-193">**TestUnion** exported from PinvokeLib.dll.</span></span>  
  
    ```  
    void TestUnion(MYUNION u, int type);  
    ```  
  
 <span data-ttu-id="299ec-194">[PinvokeLib.dll](https://msdn.microsoft.com/library/5d1438d7-9946-489d-8ede-6c694a08f614(v=vs.100))은 앞에 나열된 함수와 두 공용 구조체, **MYUNION** and **MYUNION2**에 대한 구현을 포함하는 관리되지 않는 사용자 지정 라이브러리입니다.</span><span class="sxs-lookup"><span data-stu-id="299ec-194">[PinvokeLib.dll](https://msdn.microsoft.com/library/5d1438d7-9946-489d-8ede-6c694a08f614(v=vs.100)) is a custom unmanaged library that contains an implementation for the previously listed function and two unions, **MYUNION** and **MYUNION2**.</span></span> <span data-ttu-id="299ec-195">공용 구조체에는 다음과 같은 요소가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="299ec-195">The unions contain the following elements:</span></span>  
  
```  
union MYUNION  
{  
    int number;  
    double d;  
}  
  
union MYUNION2  
{  
    int i;  
    char str[128];  
};  
```  
  
 <span data-ttu-id="299ec-196">관리 코드에서는 공용 구조체가 구조체로 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="299ec-196">In managed code, unions are defined as structures.</span></span> <span data-ttu-id="299ec-197">`MyUnion` 구조체에는 두 개의 값 형식(정수 및 double)이 해당 멤버로 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="299ec-197">The `MyUnion` structure contains two value types as its members: an integer and a double.</span></span> <span data-ttu-id="299ec-198"><xref:System.Runtime.InteropServices.StructLayoutAttribute> 특성은 각 데이터 멤버의 정확한 위치를 제어하기 위해 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="299ec-198">The <xref:System.Runtime.InteropServices.StructLayoutAttribute> attribute is set to control the precise position of each data member.</span></span> <span data-ttu-id="299ec-199"><xref:System.Runtime.InteropServices.FieldOffsetAttribute> 특성은 공용 구조체의 관리되지 않는 표현 내에서 필드의 실제 위치를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="299ec-199">The <xref:System.Runtime.InteropServices.FieldOffsetAttribute> attribute provides the physical position of fields within the unmanaged representation of a union.</span></span> <span data-ttu-id="299ec-200">두 멤버는 오프셋 값이 같으므로 동일한 메모리 부분을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="299ec-200">Notice that both members have the same offset values, so the members can define the same piece of memory.</span></span>  
  
 <span data-ttu-id="299ec-201">`MyUnion2_1` 및 `MyUnion2_2`에는 각각 값 형식(정수)과 문자열이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="299ec-201">`MyUnion2_1` and `MyUnion2_2` contain a value type (integer) and a string, respectively.</span></span> <span data-ttu-id="299ec-202">관리 코드에서는 값 형식과 참조 형식이 겹칠 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="299ec-202">In managed code, value types and reference types are not permitted to overlap.</span></span> <span data-ttu-id="299ec-203">이 샘플에서는 메서드 오버로드를 통해 호출자가 동일한 관리되지 않는 함수를 호출할 때 두 형식을 모두 사용할 수 있게 합니다.</span><span class="sxs-lookup"><span data-stu-id="299ec-203">This sample uses method overloading to enable the caller to use both types when calling the same unmanaged function.</span></span> <span data-ttu-id="299ec-204">`MyUnion2_1`의 레이아웃은 명시적이며 정확한 오프셋 값을 가집니다.</span><span class="sxs-lookup"><span data-stu-id="299ec-204">The layout of `MyUnion2_1` is explicit and has a precise offset value.</span></span> <span data-ttu-id="299ec-205">반면, 명시적 레이아웃은 참조 형식에 사용할 수 없으므로 `MyUnion2_2`에는 순차적 레이아웃이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="299ec-205">In contrast, `MyUnion2_2` has a sequential layout, because explicit layouts are not permitted with reference types.</span></span> <span data-ttu-id="299ec-206"><xref:System.Runtime.InteropServices.MarshalAsAttribute> 특성은 <xref:System.Runtime.InteropServices.UnmanagedType> 열거형을 공용 구조체의 관리되지 않는 표현 내에 표시되는 인라인 고정 길이 문자 배열을 식별하는 데 사용되는 **ByValTStr**로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="299ec-206">The <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute sets the <xref:System.Runtime.InteropServices.UnmanagedType> enumeration to **ByValTStr**, which is used to identify the inline, fixed-length character arrays that appear within the unmanaged representation of the union.</span></span>  
  
 <span data-ttu-id="299ec-207">`LibWrap` 클래스에는 `TestUnion` 및 `TestUnion2` 메서드에 대한 프로토타입이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="299ec-207">The `LibWrap` class contains the prototypes for the `TestUnion` and `TestUnion2` methods.</span></span> <span data-ttu-id="299ec-208">`TestUnion2`는 `MyUnion2_1` 또는 `MyUnion2_2`를 매개 변수로 선언하기 위해 오버로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="299ec-208">`TestUnion2` is overloaded to declare `MyUnion2_1` or `MyUnion2_2` as parameters.</span></span>  
  
### <a name="declaring-prototypes"></a><span data-ttu-id="299ec-209">프로토타입 선언</span><span class="sxs-lookup"><span data-stu-id="299ec-209">Declaring Prototypes</span></span>  
 [!code-cpp[Conceptual.Interop.Marshaling#28](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/unions.cpp#28)]
 [!code-csharp[Conceptual.Interop.Marshaling#28](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/unions.cs#28)]
 [!code-vb[Conceptual.Interop.Marshaling#28](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/unions.vb#28)]  
  
### <a name="calling-functions"></a><span data-ttu-id="299ec-210">함수 호출</span><span class="sxs-lookup"><span data-stu-id="299ec-210">Calling Functions</span></span>  
 [!code-cpp[Conceptual.Interop.Marshaling#29](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/unions.cpp#29)]
 [!code-csharp[Conceptual.Interop.Marshaling#29](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/unions.cs#29)]
 [!code-vb[Conceptual.Interop.Marshaling#29](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/unions.vb#29)]  
  
## <a name="systime-sample"></a><span data-ttu-id="299ec-211">SysTime 샘플</span><span class="sxs-lookup"><span data-stu-id="299ec-211">SysTime sample</span></span>  
 <span data-ttu-id="299ec-212">이 샘플에서는 구조체에 대한 포인터가 필요한 관리되지 않는 함수에 클래스에 대한 포인터를 전달하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="299ec-212">This sample demonstrates how to pass a pointer to a class to an unmanaged function that expects a pointer to a structure.</span></span>  
  
 <span data-ttu-id="299ec-213">SysTime 샘플에서는 원래 함수 선언과 함께 표시되는 다음과 같은 관리되지 않는 함수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="299ec-213">The SysTime sample uses the following unmanaged function, shown with its original function declaration:</span></span>  
  
-   <span data-ttu-id="299ec-214">Kernel32.dll에서 내보낸 **GetSystemTime**.</span><span class="sxs-lookup"><span data-stu-id="299ec-214">**GetSystemTime** exported from Kernel32.dll.</span></span>  
  
    ```  
    VOID GetSystemTime(LPSYSTEMTIME lpSystemTime);  
    ```  
  
 <span data-ttu-id="299ec-215">함수에 전달된 원래 구조체에는 다음과 같은 요소가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="299ec-215">The original structure passed to the function contains the following elements:</span></span>  
  
```  
typedef struct _SYSTEMTIME {   
    WORD wYear;   
    WORD wMonth;   
    WORD wDayOfWeek;   
    WORD wDay;   
    WORD wHour;   
    WORD wMinute;   
    WORD wSecond;   
    WORD wMilliseconds;   
} SYSTEMTIME, *PSYSTEMTIME;  
```  
  
 <span data-ttu-id="299ec-216">이 샘플에서 `SystemTime` 클래스에는 클래스 멤버로 표현된 원래 구조체의 요소가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="299ec-216">In this sample, the `SystemTime` class contains the elements of the original structure represented as class members.</span></span> <span data-ttu-id="299ec-217"><xref:System.Runtime.InteropServices.StructLayoutAttribute> 특성이 설정되어 멤버가 표시되는 순서대로 순차적으로 메모리에 정렬되게 합니다.</span><span class="sxs-lookup"><span data-stu-id="299ec-217">The <xref:System.Runtime.InteropServices.StructLayoutAttribute> attribute is set to ensure that the members are arranged in memory sequentially, in the order in which they appear.</span></span>  
  
 <span data-ttu-id="299ec-218">`LibWrap` 클래스에는 기본적으로 `SystemTime` 클래스를 In/Out 매개 변수로 전달하는 `GetSystemTime` 메서드의 관리되는 프로토타입이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="299ec-218">The `LibWrap` class contains a managed prototype of the `GetSystemTime` method, which passes the `SystemTime` class as an In/Out parameter by default.</span></span> <span data-ttu-id="299ec-219">참조 형식인 클래스는 기본적으로 In 매개 변수로 전달되므로 <xref:System.Runtime.InteropServices.InAttribute> 및 <xref:System.Runtime.InteropServices.OutAttribute> 특성을 통해 매개 변수를 선언해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="299ec-219">The parameter must be declared with the <xref:System.Runtime.InteropServices.InAttribute> and <xref:System.Runtime.InteropServices.OutAttribute> attributes because classes, which are reference types, are passed as In parameters by default.</span></span> <span data-ttu-id="299ec-220">호출자가 결과를 받으려면 이러한 [방향 특성](https://msdn.microsoft.com/library/241ac5b5-928e-4969-8f58-1dbc048f9ea2(v=vs.100))을 명시적으로 적용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="299ec-220">For the caller to receive the results, these [directional attributes](https://msdn.microsoft.com/library/241ac5b5-928e-4969-8f58-1dbc048f9ea2(v=vs.100)) must be applied explicitly.</span></span> <span data-ttu-id="299ec-221">`App` 클래스는 `SystemTime` 클래스의 새 인스턴스를 만들고 해당 데이터 필드에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="299ec-221">The `App` class creates a new instance of the `SystemTime` class and accesses its data fields.</span></span>  
  
### <a name="code-samples"></a><span data-ttu-id="299ec-222">코드 샘플</span><span class="sxs-lookup"><span data-stu-id="299ec-222">Code Samples</span></span>  
 [!code-cpp[Conceptual.Interop.Marshaling#25](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/systime.cpp#25)]
 [!code-csharp[Conceptual.Interop.Marshaling#25](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/systime.cs#25)]
 [!code-vb[Conceptual.Interop.Marshaling#25](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/systime.vb#25)]  
  
## <a name="outarrayofstructs-sample"></a><span data-ttu-id="299ec-223">OutArrayOfStructs 샘플</span><span class="sxs-lookup"><span data-stu-id="299ec-223">OutArrayOfStructs sample</span></span>  
 <span data-ttu-id="299ec-224">이 샘플에서는 정수 및 문자열을 Out 매개 변수로 포함하는 구조체의 배열을 관리되지 않는 함수에 전달하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="299ec-224">This sample shows how to pass an array of structures that contains integers and strings as Out parameters to an unmanaged function.</span></span>  
  
 <span data-ttu-id="299ec-225"><xref:System.Runtime.InteropServices.Marshal> 클래스 및 안전하지 않은 코드를 사용하여 네이티브 함수를 호출하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="299ec-225">This sample demonstrates how to call a native function by using the <xref:System.Runtime.InteropServices.Marshal> class and by using unsafe code.</span></span>  
  
 <span data-ttu-id="299ec-226">이 샘플에서는 [PinvokeLib.dll](https://msdn.microsoft.com/library/5d1438d7-9946-489d-8ede-6c694a08f614(v=vs.100))에서 정의된 래퍼 함수 및 플랫폼 호출을 사용합니다(소스 파일에도 제공됨).</span><span class="sxs-lookup"><span data-stu-id="299ec-226">This sample uses a wrapper functions and platform invokes defined in [PinvokeLib.dll](https://msdn.microsoft.com/library/5d1438d7-9946-489d-8ede-6c694a08f614(v=vs.100)), also provided in the source files.</span></span> <span data-ttu-id="299ec-227">`TestOutArrayOfStructs` 함수 및 `MYSTRSTRUCT2` 구조체를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="299ec-227">It uses the `TestOutArrayOfStructs` function and the `MYSTRSTRUCT2` structure.</span></span> <span data-ttu-id="299ec-228">이 구조체에는 다음과 같은 요소가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="299ec-228">The structure contains the following elements:</span></span>  
  
```  
typedef struct _MYSTRSTRUCT2  
{  
   char* buffer;  
   UINT size;   
} MYSTRSTRUCT2;  
```  
  
 <span data-ttu-id="299ec-229">`MyStruct` 클래스에는 ANSI 문자의 문자열 개체가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="299ec-229">The `MyStruct` class contains a string object of ANSI characters.</span></span> <span data-ttu-id="299ec-230"><xref:System.Runtime.InteropServices.DllImportAttribute.CharSet> 필드는 ANSI 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="299ec-230">The <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet> field specifies ANSI format.</span></span> <span data-ttu-id="299ec-231">`MyUnsafeStruct`는 문자열 대신 <xref:System.IntPtr> 형식을 포함하는 구조체입니다.</span><span class="sxs-lookup"><span data-stu-id="299ec-231">`MyUnsafeStruct`, is a structure containing an <xref:System.IntPtr> type instead of a string.</span></span>  
  
 <span data-ttu-id="299ec-232">`LibWrap` 클래스에는 오버로드된 `TestOutArrayOfStructs` 프로토타입 메서드가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="299ec-232">The `LibWrap` class contains the overloaded `TestOutArrayOfStructs` prototype method.</span></span> <span data-ttu-id="299ec-233">메서드가 포인터를 매개 변수로 선언하는 경우 클래스에 `unsafe` 키워드를 표시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="299ec-233">If a method declares a pointer as a parameter, the class should be marked with the `unsafe` keyword.</span></span> <span data-ttu-id="299ec-234">[!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)]는 안전하지 않은 코드를 사용할 수 없으므로 오버로드된 메서드, 안전하지 않은 한정자 및 `MyUnsafeStruct` 구조체는 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="299ec-234">Because [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)] cannot use unsafe code, the overloaded method, unsafe modifier, and the `MyUnsafeStruct` structure are unnecessary.</span></span>  
  
 <span data-ttu-id="299ec-235">`App` 클래스는 배열을 전달하는 데 필요한 모든 작업을 수행하는 `UsingMarshaling` 메서드를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="299ec-235">The `App` class implements the `UsingMarshaling` method, which performs all the tasks necessary to pass the array.</span></span> <span data-ttu-id="299ec-236">배열에 `out`(Visual Basic에서는 `ByRef`) 키워드가 표시되어 데이터가 호출 수신자에서 호출자로 전달됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="299ec-236">The array is marked with the `out` (`ByRef` in Visual Basic) keyword to indicate that data passes from callee to caller.</span></span> <span data-ttu-id="299ec-237">이 구현에서는 다음과 같은 <xref:System.Runtime.InteropServices.Marshal> 클래스 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="299ec-237">The implementation uses the following <xref:System.Runtime.InteropServices.Marshal> class methods:</span></span>  
  
-   <span data-ttu-id="299ec-238"><xref:System.Runtime.InteropServices.Marshal.PtrToStructure%2A> - 관리되지 않는 버퍼의 데이터를 관리되는 개체로 마샬링합니다.</span><span class="sxs-lookup"><span data-stu-id="299ec-238"><xref:System.Runtime.InteropServices.Marshal.PtrToStructure%2A> to marshal data from the unmanaged buffer to a managed object.</span></span>  
  
-   <span data-ttu-id="299ec-239"><xref:System.Runtime.InteropServices.Marshal.DestroyStructure%2A> - 구조체의 문자열에 예약된 메모리를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="299ec-239"><xref:System.Runtime.InteropServices.Marshal.DestroyStructure%2A> to release the memory reserved for strings in the structure.</span></span>  
  
-   <span data-ttu-id="299ec-240"><xref:System.Runtime.InteropServices.Marshal.FreeCoTaskMem%2A> - 배열에 예약된 메모리를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="299ec-240"><xref:System.Runtime.InteropServices.Marshal.FreeCoTaskMem%2A> to release the memory reserved for the array.</span></span>  
  
 <span data-ttu-id="299ec-241">앞서 설명한 것처럼, C#에서는 안전하지 않은 코드를 허용하고 [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)]에서는 허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="299ec-241">As previously mentioned, C# allows unsafe code and [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)] does not.</span></span> <span data-ttu-id="299ec-242">C# 샘플에서 `UsingUnsafePointer`는 <xref:System.Runtime.InteropServices.Marshal> 클래스 대신 포인터를 사용하여 `MyUnsafeStruct` 구조체가 포함된 배열을 다시 전달하는 대체 구현입니다.</span><span class="sxs-lookup"><span data-stu-id="299ec-242">In the C# sample, `UsingUnsafePointer` is an alternative method implementation that uses pointers instead of the <xref:System.Runtime.InteropServices.Marshal> class to pass back the array containing the `MyUnsafeStruct` structure.</span></span>  
  
### <a name="declaring-prototypes"></a><span data-ttu-id="299ec-243">프로토타입 선언</span><span class="sxs-lookup"><span data-stu-id="299ec-243">Declaring Prototypes</span></span>  
 [!code-cpp[Conceptual.Interop.Marshaling#20](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/outarrayofstructs.cpp#20)]
 [!code-csharp[Conceptual.Interop.Marshaling#20](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/outarrayofstructs.cs#20)]
 [!code-vb[Conceptual.Interop.Marshaling#20](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/outarrayofstructs.vb#20)]  
  
### <a name="calling-functions"></a><span data-ttu-id="299ec-244">함수 호출</span><span class="sxs-lookup"><span data-stu-id="299ec-244">Calling Functions</span></span>  
 [!code-cpp[Conceptual.Interop.Marshaling#21](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/outarrayofstructs.cpp#21)]
 [!code-csharp[Conceptual.Interop.Marshaling#21](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/outarrayofstructs.cs#21)]
 [!code-vb[Conceptual.Interop.Marshaling#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/outarrayofstructs.vb#21)]  
  
## <a name="see-also"></a><span data-ttu-id="299ec-245">참고 항목</span><span class="sxs-lookup"><span data-stu-id="299ec-245">See Also</span></span>  
 [<span data-ttu-id="299ec-246">플랫폼 호출을 사용하여 데이터 마샬링</span><span class="sxs-lookup"><span data-stu-id="299ec-246">Marshaling Data with Platform Invoke</span></span>](marshaling-data-with-platform-invoke.md)  
 <span data-ttu-id="299ec-247">[플랫폼 호출 데이터 형식](https://msdn.microsoft.com/library/16014d9f-d6bd-481e-83f0-df11377c550f(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="299ec-247">[Platform Invoke Data Types](https://msdn.microsoft.com/library/16014d9f-d6bd-481e-83f0-df11377c550f(v=vs.100))</span></span>  
 [<span data-ttu-id="299ec-248">문자열 마샬링</span><span class="sxs-lookup"><span data-stu-id="299ec-248">Marshaling Strings</span></span>](marshaling-strings.md)  
 <span data-ttu-id="299ec-249">[형식 배열 마샬링](https://msdn.microsoft.com/library/049b1c1b-228f-4445-88ec-91bc7fd4b1e8(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="299ec-249">[Marshaling Arrays of Types](https://msdn.microsoft.com/library/049b1c1b-228f-4445-88ec-91bc7fd4b1e8(v=vs.100))</span></span>
