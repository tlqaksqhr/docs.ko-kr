---
title: "문자열 마샬링"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- marshaling, samples
- platform invoke, marshaling data
- data marshaling, strings
- data marshaling, samples
- data marshaling, platform invoke
- marshaling. strings
- marshaling, platform invoke
- sample applications [.NET Framework], marshaling strings
ms.assetid: e21b078b-70fb-4905-be26-c097ab2433ff
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 750f4e6852cd5aa52d03f884edcbfbf80ed5fab5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="marshaling-strings"></a><span data-ttu-id="e4cb7-102">문자열 마샬링</span><span class="sxs-lookup"><span data-stu-id="e4cb7-102">Marshaling Strings</span></span>
<span data-ttu-id="e4cb7-103">플랫폼 호출은 문자열 매개 변수를 복사하고 필요한 경우 .NET Framework 형식(유니코드)을 관리되지 않는 형식(ANSI)으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="e4cb7-103">Platform invoke copies string parameters, converting them from the .NET Framework format (Unicode) to the unmanaged format (ANSI), if needed.</span></span> <span data-ttu-id="e4cb7-104">관리되는 문자열은 변경할 수 없으므로 함수가 반환할 때 플랫폼 호출을 통해 해당 문자열을 관리되지 않는 메모리에서 관리되는 메모리로 다시 복사하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e4cb7-104">Because managed strings are immutable, platform invoke does not copy them back from unmanaged memory to managed memory when the function returns.</span></span>  
  
 <span data-ttu-id="e4cb7-105">다음 표에서는 문자열에 대한 마샬링 옵션을 나열하고 용도를 설명하며 해당하는 .NET Framework 샘플에 대한 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e4cb7-105">The following table lists marshaling options for strings, describes their usage, and provides a link to the corresponding .NET Framework sample.</span></span>  
  
|<span data-ttu-id="e4cb7-106">문자열</span><span class="sxs-lookup"><span data-stu-id="e4cb7-106">String</span></span>|<span data-ttu-id="e4cb7-107">설명</span><span class="sxs-lookup"><span data-stu-id="e4cb7-107">Description</span></span>|<span data-ttu-id="e4cb7-108">샘플</span><span class="sxs-lookup"><span data-stu-id="e4cb7-108">Sample</span></span>|  
|------------|-----------------|------------|  
|<span data-ttu-id="e4cb7-109">값.</span><span class="sxs-lookup"><span data-stu-id="e4cb7-109">By value.</span></span>|<span data-ttu-id="e4cb7-110">문자열을 In 매개 변수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="e4cb7-110">Passes strings as In parameters.</span></span>|[<span data-ttu-id="e4cb7-111">MsgBox</span><span class="sxs-lookup"><span data-stu-id="e4cb7-111">MsgBox</span></span>](../../../docs/framework/interop/msgbox-sample.md)|  
|<span data-ttu-id="e4cb7-112">결과.</span><span class="sxs-lookup"><span data-stu-id="e4cb7-112">As result.</span></span>|<span data-ttu-id="e4cb7-113">비관리 코드에서 문자열을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="e4cb7-113">Returns strings from unmanaged code.</span></span>|[<span data-ttu-id="e4cb7-114">문자열</span><span class="sxs-lookup"><span data-stu-id="e4cb7-114">Strings</span></span>](http://msdn.microsoft.com/en-us/be9e82a3-dc95-4aaa-9396-61b66e467e02)|  
|<span data-ttu-id="e4cb7-115">참조.</span><span class="sxs-lookup"><span data-stu-id="e4cb7-115">By reference.</span></span>|<span data-ttu-id="e4cb7-116"><xref:System.Text.StringBuilder>를 사용하여 In/Out 매개 변수로 문자열을 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="e4cb7-116">Passes strings as In/Out parameters using <xref:System.Text.StringBuilder>.</span></span>|[<span data-ttu-id="e4cb7-117">버퍼</span><span class="sxs-lookup"><span data-stu-id="e4cb7-117">Buffers</span></span>](http://msdn.microsoft.com/en-us/e30d36e8-d7c4-4936-916a-8fdbe4d9ffd5)|  
|<span data-ttu-id="e4cb7-118">값 방식 구조체.</span><span class="sxs-lookup"><span data-stu-id="e4cb7-118">In a structure by value.</span></span>|<span data-ttu-id="e4cb7-119">In 매개 변수에 있는 구조체에 문자열을 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="e4cb7-119">Passes strings in a structure that is an In parameter.</span></span>|[<span data-ttu-id="e4cb7-120">구조체</span><span class="sxs-lookup"><span data-stu-id="e4cb7-120">Structs</span></span>](http://msdn.microsoft.com/en-us/96a62265-dcf9-4608-bc0a-1f762ab9f48e)|  
|<span data-ttu-id="e4cb7-121">참조 방식 구조체**(char\*)**.</span><span class="sxs-lookup"><span data-stu-id="e4cb7-121">In a structure by reference **(char\*)**.</span></span>|<span data-ttu-id="e4cb7-122">In/Out 매개 변수에 있는 구조체에 문자열을 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="e4cb7-122">Passes strings in a structure that is an In/Out parameter.</span></span> <span data-ttu-id="e4cb7-123">관리되지 않는 함수에는 문자 버퍼에 대한 포인터가 필요하며 버퍼 크기는 구조체의 멤버입니다.</span><span class="sxs-lookup"><span data-stu-id="e4cb7-123">The unmanaged function expects a pointer to a character buffer and the buffer size is a member of the structure.</span></span>|[<span data-ttu-id="e4cb7-124">문자열</span><span class="sxs-lookup"><span data-stu-id="e4cb7-124">Strings</span></span>](http://msdn.microsoft.com/en-us/be9e82a3-dc95-4aaa-9396-61b66e467e02)|  
|<span data-ttu-id="e4cb7-125">참조 방식 구조체**(char[])**.</span><span class="sxs-lookup"><span data-stu-id="e4cb7-125">In a structure by reference **(char[])**.</span></span>|<span data-ttu-id="e4cb7-126">In/Out 매개 변수에 있는 구조체에 문자열을 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="e4cb7-126">Passes strings in a structure that is an In/Out parameter.</span></span> <span data-ttu-id="e4cb7-127">관리되지 않는 함수에는 포함된 문자 버퍼가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4cb7-127">The unmanaged function expects an embedded character buffer.</span></span>|[<span data-ttu-id="e4cb7-128">OSInfo</span><span class="sxs-lookup"><span data-stu-id="e4cb7-128">OSInfo</span></span>](http://msdn.microsoft.com/en-us/69d89067-507b-41fe-859d-30bf3ff29455)|  
|<span data-ttu-id="e4cb7-129">값 방식 클래스**(char\*)**.</span><span class="sxs-lookup"><span data-stu-id="e4cb7-129">In a class by value **(char\*)**.</span></span>|<span data-ttu-id="e4cb7-130">클래스에 문자열을 전달합니다(클래스는 In/Out 매개 변수임).</span><span class="sxs-lookup"><span data-stu-id="e4cb7-130">Passes strings in a class (a class is an In/Out parameter).</span></span> <span data-ttu-id="e4cb7-131">관리되지 않는 함수에는 문자 버퍼에 대한 포인터가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4cb7-131">The unmanaged function expects a pointer to a character buffer.</span></span>|[<span data-ttu-id="e4cb7-132">OpenFileDlg</span><span class="sxs-lookup"><span data-stu-id="e4cb7-132">OpenFileDlg</span></span>](http://msdn.microsoft.com/en-us/b7dea792-cb92-4baf-ac7b-6a24803e6c75)|  
|<span data-ttu-id="e4cb7-133">값 방식 클래스**(char[])**.</span><span class="sxs-lookup"><span data-stu-id="e4cb7-133">In a class by value **(char[])**.</span></span>|<span data-ttu-id="e4cb7-134">클래스에 문자열을 전달합니다(클래스는 In/Out 매개 변수임).</span><span class="sxs-lookup"><span data-stu-id="e4cb7-134">Passes strings in a class (a class is an In/Out parameter).</span></span> <span data-ttu-id="e4cb7-135">관리되지 않는 함수에는 포함된 문자 버퍼가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4cb7-135">The unmanaged function expects an embedded character buffer.</span></span>|[<span data-ttu-id="e4cb7-136">OSInfo</span><span class="sxs-lookup"><span data-stu-id="e4cb7-136">OSInfo</span></span>](http://msdn.microsoft.com/en-us/69d89067-507b-41fe-859d-30bf3ff29455)|  
|<span data-ttu-id="e4cb7-137">값 형식 문자열 배열.</span><span class="sxs-lookup"><span data-stu-id="e4cb7-137">As an array of strings by value.</span></span>|<span data-ttu-id="e4cb7-138">값으로 전달되는 문자열의 배열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e4cb7-138">Creates an array of strings that is passed by value.</span></span>|[<span data-ttu-id="e4cb7-139">배열</span><span class="sxs-lookup"><span data-stu-id="e4cb7-139">Arrays</span></span>](../../../docs/framework/interop/marshaling-different-types-of-arrays.md)|  
|<span data-ttu-id="e4cb7-140">값 형식 문자열을 포함하는 구조체의 배열.</span><span class="sxs-lookup"><span data-stu-id="e4cb7-140">As an array of structures that contain strings by value.</span></span>|<span data-ttu-id="e4cb7-141">문자열을 포함하는 구조체의 배열을 만들고 배열을 값으로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="e4cb7-141">Creates an array of structures that contain strings and the array is passed by value.</span></span>|[<span data-ttu-id="e4cb7-142">배열</span><span class="sxs-lookup"><span data-stu-id="e4cb7-142">Arrays</span></span>](../../../docs/framework/interop/marshaling-different-types-of-arrays.md)|  
  
## <a name="see-also"></a><span data-ttu-id="e4cb7-143">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e4cb7-143">See Also</span></span>  
 [<span data-ttu-id="e4cb7-144">플랫폼 호출을 사용하여 데이터 마샬링</span><span class="sxs-lookup"><span data-stu-id="e4cb7-144">Marshaling Data with Platform Invoke</span></span>](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md)  
 [<span data-ttu-id="e4cb7-145">플랫폼 호출 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="e4cb7-145">Platform Invoke Data Types</span></span>](http://msdn.microsoft.com/en-us/16014d9f-d6bd-481e-83f0-df11377c550f)  
 [<span data-ttu-id="e4cb7-146">클래스, 구조체 및 공용 구조체 마샬링</span><span class="sxs-lookup"><span data-stu-id="e4cb7-146">Marshaling Classes, Structures, and Unions</span></span>](../../../docs/framework/interop/marshaling-classes-structures-and-unions.md)  
 [<span data-ttu-id="e4cb7-147">형식 배열 마샬링</span><span class="sxs-lookup"><span data-stu-id="e4cb7-147">Marshaling Arrays of Types</span></span>](http://msdn.microsoft.com/en-us/049b1c1b-228f-4445-88ec-91bc7fd4b1e8)  
 [<span data-ttu-id="e4cb7-148">기타 마샬링 샘플</span><span class="sxs-lookup"><span data-stu-id="e4cb7-148">Miscellaneous Marshaling Samples</span></span>](http://msdn.microsoft.com/en-us/a915c948-54e9-4d0f-a525-95a77fd8ed70)
