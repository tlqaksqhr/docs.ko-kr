---
title: "방법: 바이트 배열을 정수로 변환(C# 프로그래밍 가이드)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- conversions [C#], byte array to int
- byte arrays [C#], converting to int
ms.assetid: d6ac20e2-448e-4aea-99b9-faf04c6f1e79
caps.latest.revision: 18
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 86ecfe95ab6fb5ce60e7568050cdf974d0dc3d88
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-convert-a-byte-array-to-an-int-c-programming-guide"></a><span data-ttu-id="415b7-102">방법: 바이트 배열을 정수로 변환(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="415b7-102">How to: Convert a byte Array to an int (C# Programming Guide)</span></span>
<span data-ttu-id="415b7-103">이 예제에서는 <xref:System.BitConverter> 클래스를 사용하여 바이트 배열을 [int](../../../csharp/language-reference/keywords/int.md)로 변환하고 다시 바이트 배열로 변환하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="415b7-103">This example shows you how to use the <xref:System.BitConverter> class to convert an array of bytes to an [int](../../../csharp/language-reference/keywords/int.md) and back to an array of bytes.</span></span> <span data-ttu-id="415b7-104">예를 들어 네트워크에 바이트를 읽은 후 바이트에서 기본 제공 데이터 형식으로 변환해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="415b7-104">You may have to convert from bytes to a built-in data type after you read bytes off the network, for example.</span></span> <span data-ttu-id="415b7-105">예제의 [ToInt32(Byte\[\], Int32)](xref:System.BitConverter.ToInt32(System.Byte[],System.Int32)) 메서드 외에도 다음 표에서는 바이트(바이트 배열)를 다른 기본 제공 형식으로 변환하는 <xref:System.BitConverter> 클래스의 메서드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="415b7-105">In addition to the [ToInt32(Byte\[\], Int32)](xref:System.BitConverter.ToInt32(System.Byte[],System.Int32)) method in the example, the following table lists methods in the <xref:System.BitConverter> class that convert bytes (from an array of bytes) to other built-in types.</span></span>  
  
|<span data-ttu-id="415b7-106">반환되는 형식</span><span class="sxs-lookup"><span data-stu-id="415b7-106">Type returned</span></span>|<span data-ttu-id="415b7-107">메서드</span><span class="sxs-lookup"><span data-stu-id="415b7-107">Method</span></span>|  
|-------------------|------------|  
|`bool`|<span data-ttu-id="415b7-108">[ToBoolean(Byte\[\], Int32)](xref:System.BitConverter.ToBoolean(System.Byte[],System.Int32))</span><span class="sxs-lookup"><span data-stu-id="415b7-108">[ToBoolean(Byte\[\], Int32)](xref:System.BitConverter.ToBoolean(System.Byte[],System.Int32))</span></span>|  
|`char`|<span data-ttu-id="415b7-109">[ToChar(Byte\[\], Int32)](xref:System.BitConverter.ToChar(System.Byte[],System.Int32))</span><span class="sxs-lookup"><span data-stu-id="415b7-109">[ToChar(Byte\[\], Int32)](xref:System.BitConverter.ToChar(System.Byte[],System.Int32))</span></span>|  
|`double`|<span data-ttu-id="415b7-110">[ToDouble(Byte\[\], Int32)](xref:System.BitConverter.ToDouble(System.Byte[],System.Int32))</span><span class="sxs-lookup"><span data-stu-id="415b7-110">[ToDouble(Byte\[\], Int32)](xref:System.BitConverter.ToDouble(System.Byte[],System.Int32))</span></span>|  
|`short`|<span data-ttu-id="415b7-111">[ToInt16(Byte\[\], Int32)](xref:System.BitConverter.ToInt16(System.Byte[],System.Int32))</span><span class="sxs-lookup"><span data-stu-id="415b7-111">[ToInt16(Byte\[\], Int32)](xref:System.BitConverter.ToInt16(System.Byte[],System.Int32))</span></span>|  
|`int`|<span data-ttu-id="415b7-112">[ToInt32(Byte\[\], Int32)](xref:System.BitConverter.ToInt32(System.Byte[],System.Int32))</span><span class="sxs-lookup"><span data-stu-id="415b7-112">[ToInt32(Byte\[\], Int32)](xref:System.BitConverter.ToInt32(System.Byte[],System.Int32))</span></span>|  
|`long`|<span data-ttu-id="415b7-113">[ToInt64(Byte\[\], Int32)](xref:System.BitConverter.ToInt64(System.Byte[],System.Int32))</span><span class="sxs-lookup"><span data-stu-id="415b7-113">[ToInt64(Byte\[\], Int32)](xref:System.BitConverter.ToInt64(System.Byte[],System.Int32))</span></span>|  
|`float`|<span data-ttu-id="415b7-114">[ToSingle(Byte\[\], Int32)](xref:System.BitConverter.ToSingle(System.Byte[],System.Int32))</span><span class="sxs-lookup"><span data-stu-id="415b7-114">[ToSingle(Byte\[\], Int32)](xref:System.BitConverter.ToSingle(System.Byte[],System.Int32))</span></span>|  
|`ushort`|<span data-ttu-id="415b7-115">[ToUInt16(Byte\[\], Int32)](xref:System.BitConverter.ToUInt16(System.Byte[],System.Int32))</span><span class="sxs-lookup"><span data-stu-id="415b7-115">[ToUInt16(Byte\[\], Int32)](xref:System.BitConverter.ToUInt16(System.Byte[],System.Int32))</span></span>|  
|`uint`|<span data-ttu-id="415b7-116">[ToUInt32(Byte\[\], Int32)](xref:System.BitConverter.ToUInt32(System.Byte[],System.Int32))</span><span class="sxs-lookup"><span data-stu-id="415b7-116">[ToUInt32(Byte\[\], Int32)](xref:System.BitConverter.ToUInt32(System.Byte[],System.Int32))</span></span>|  
|`ulong`|<span data-ttu-id="415b7-117">[ToUInt64(Byte\[\], Int32)](xref:System.BitConverter.ToUInt64(System.Byte[],System.Int32))</span><span class="sxs-lookup"><span data-stu-id="415b7-117">[ToUInt64(Byte\[\], Int32)](xref:System.BitConverter.ToUInt64(System.Byte[],System.Int32))</span></span>|  
  
## <a name="example"></a><span data-ttu-id="415b7-118">예제</span><span class="sxs-lookup"><span data-stu-id="415b7-118">Example</span></span>  
 <span data-ttu-id="415b7-119">이 예제에서는 바이트 배열을 초기화하고, 컴퓨터 아키텍처가 little-endian이면 배열을 반전한 다음(즉, 최하위 바이트가 먼저 저장됨) [ToInt32(Byte\[\], Int32)](xref:System.BitConverter.ToInt32(System.Byte[],System.Int32)) 메서드를 호출하여 배열의 4바이트를 `int`로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="415b7-119">This example initializes an array of bytes, reverses the array if the computer architecture is little-endian (that is, the least significant byte is stored first), and then calls the [ToInt32(Byte\[\], Int32)](xref:System.BitConverter.ToInt32(System.Byte[],System.Int32)) method to convert four bytes in the array to an `int`.</span></span> <span data-ttu-id="415b7-120">[ToInt32(Byte\[\], Int32)](xref:System.BitConverter.ToInt32(System.Byte[],System.Int32))에 대한 두 번째 인수는 바이트 배열의 시작 인덱스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="415b7-120">The second argument to [ToInt32(Byte\[\], Int32)](xref:System.BitConverter.ToInt32(System.Byte[],System.Int32)) specifies the start index of the array of bytes.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="415b7-121">출력은 컴퓨터 아키텍처의 endianess에 따라 달라질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="415b7-121">The output may differ depending on the endianess of your computer's architecture.</span></span>  
  
 <span data-ttu-id="415b7-122">[!code-cs[csProgGuideTypes#22](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-byte-array-to-an-int_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="415b7-122">[!code-cs[csProgGuideTypes#22](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-byte-array-to-an-int_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="415b7-123">예제</span><span class="sxs-lookup"><span data-stu-id="415b7-123">Example</span></span>  
 <span data-ttu-id="415b7-124">이 예제에서는 <xref:System.BitConverter> 클래스의 <xref:System.BitConverter.GetBytes%28System.Int32%29> 메서드를 호출하여 `int`를 바이트 배열로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="415b7-124">In this example, the <xref:System.BitConverter.GetBytes%28System.Int32%29> method of the <xref:System.BitConverter> class is called to convert an `int` to an array of bytes.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="415b7-125">출력은 컴퓨터 아키텍처의 endianess에 따라 달라질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="415b7-125">The output may differ depending on the endianess of your computer's architecture.</span></span>  
  
 <span data-ttu-id="415b7-126">[!code-cs[csProgGuideTypes#23](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-byte-array-to-an-int_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="415b7-126">[!code-cs[csProgGuideTypes#23](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-byte-array-to-an-int_2.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="415b7-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="415b7-127">See Also</span></span>  
 <span data-ttu-id="415b7-128"><xref:System.BitConverter></span><span class="sxs-lookup"><span data-stu-id="415b7-128"><xref:System.BitConverter></span></span>   
 <span data-ttu-id="415b7-129"><xref:System.BitConverter.IsLittleEndian></span><span class="sxs-lookup"><span data-stu-id="415b7-129"><xref:System.BitConverter.IsLittleEndian></span></span>   
 [<span data-ttu-id="415b7-130">유형</span><span class="sxs-lookup"><span data-stu-id="415b7-130">Types</span></span>](../../../csharp/programming-guide/types/index.md)

