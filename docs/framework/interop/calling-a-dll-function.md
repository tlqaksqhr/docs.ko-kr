---
title: DLL 함수 호출
ms.date: 03/30/2017
helpviewer_keywords:
- unmanaged functions, calling
- unmanaged functions
- COM interop, platform invoke
- platform invoke, calling unmanaged functions
- interoperation with unmanaged code, platform invoke
- DLL functions
ms.assetid: 113646de-7ea0-4f0e-8df0-c46dab3e8733
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 98d363b6c0838ff1211d969391f04ce8ccddd003
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33387135"
---
# <a name="calling-a-dll-function"></a><span data-ttu-id="4bdd7-102">DLL 함수 호출</span><span class="sxs-lookup"><span data-stu-id="4bdd7-102">Calling a DLL Function</span></span>
<span data-ttu-id="4bdd7-103">관리되지 않는 DLL 함수 호출은 다른 관리 코드 호출과 거의 동일하지만 처음에 DLL 함수를 혼동하게 만드는 차이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bdd7-103">Although calling unmanaged DLL functions is nearly identical to calling other managed code, there are differences that can make DLL functions seem confusing at first.</span></span> <span data-ttu-id="4bdd7-104">이 섹션에서는 몇 가지 비정상적인 호출 관련 문제를 설명하는 항목을 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="4bdd7-104">This section introduces topics that describe some of the unusual calling-related issues.</span></span>  
  
 <span data-ttu-id="4bdd7-105">플랫폼 호출에서 반환되는 구조는 관리 코드와 비관리 코드에 동일한 표현이 있는 데이터 형식이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bdd7-105">Structures that are returned from platform invoke calls must be data types that have the same representation in managed and unmanaged code.</span></span> <span data-ttu-id="4bdd7-106">이러한 형식은 변환이 필요하지 않으므로 *blittable 형식*이라고 합니다([blittable 형식 및 비 Blittable 형식](../../../docs/framework/interop/blittable-and-non-blittable-types.md) 참조).</span><span class="sxs-lookup"><span data-stu-id="4bdd7-106">Such types are called *blittable types* because they do not require conversion (see [Blittable and Non-Blittable Types](../../../docs/framework/interop/blittable-and-non-blittable-types.md)).</span></span> <span data-ttu-id="4bdd7-107">비 blittable 구조를 반환 형식으로 사용하는 함수를 호출하려면 비 blittable 형식과 동일한 크기의 blittable 도우미 형식을 정의하고 함수가 반환된 후 데이터를 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="4bdd7-107">To call a function that has a non-blittable structure as its return type, you can define a blittable helper type of the same size as the non-blittable type and convert the data after the function returns.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4bdd7-108">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="4bdd7-108">In This Section</span></span>  
 [<span data-ttu-id="4bdd7-109">구조체 전달</span><span class="sxs-lookup"><span data-stu-id="4bdd7-109">Passing Structures</span></span>](../../../docs/framework/interop/passing-structures.md)  
 <span data-ttu-id="4bdd7-110">미리 정의된 레이아웃으로 데이터 구조를 전달하는 문제를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="4bdd7-110">Identifies the issues of passing data structures with a predefined layout.</span></span>  
  
 [<span data-ttu-id="4bdd7-111">콜백 함수</span><span class="sxs-lookup"><span data-stu-id="4bdd7-111">Callback Functions</span></span>](../../../docs/framework/interop/callback-functions.md)  
 <span data-ttu-id="4bdd7-112">콜백 함수에 대한 기본 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4bdd7-112">Provides basic information about callback functions.</span></span>  
  
 [<span data-ttu-id="4bdd7-113">방법: 콜백 함수 구현</span><span class="sxs-lookup"><span data-stu-id="4bdd7-113">How to: Implement Callback Functions</span></span>](../../../docs/framework/interop/how-to-implement-callback-functions.md)  
 <span data-ttu-id="4bdd7-114">관리 코드에서 콜백 함수를 구현하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4bdd7-114">Describes how to implement callback functions in managed code.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="4bdd7-115">관련 단원</span><span class="sxs-lookup"><span data-stu-id="4bdd7-115">Related Sections</span></span>  
 [<span data-ttu-id="4bdd7-116">관리되지 않는 DLL 함수 사용</span><span class="sxs-lookup"><span data-stu-id="4bdd7-116">Consuming Unmanaged DLL Functions</span></span>](../../../docs/framework/interop/consuming-unmanaged-dll-functions.md)  
 <span data-ttu-id="4bdd7-117">플랫폼 호출을 사용하여 관리되지 않는 DLL 함수를 호출하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4bdd7-117">Describes how to call unmanaged DLL functions using platform invoke.</span></span>  
  
 [<span data-ttu-id="4bdd7-118">플랫폼 호출을 사용하여 데이터 마샬링</span><span class="sxs-lookup"><span data-stu-id="4bdd7-118">Marshaling Data with Platform Invoke</span></span>](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md)  
 <span data-ttu-id="4bdd7-119">메서드 매개 변수를 선언하고 관리되지 않는 라이브러리에서 내보낸 함수에 인수를 전달하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4bdd7-119">Describes how to declare method parameters and pass arguments to functions exported by unmanaged libraries.</span></span>
