---
title: ".NET에서 형식 변환 표"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- widening conversions
- narrowing conversions
- type conversion, table
- converting types, narrowing conversions
- converting types, widening conversions
- base types, converting
- tables [.NET Framework], type conversions
- data types [.NET Framework], converting
ms.assetid: 0ea65c59-85eb-4a52-94ca-c36d3bd13058
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 327469f9a151b6ef7e1c42f6669c0a9dae7016fd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="type-conversion-tables-in-net"></a><span data-ttu-id="6afd6-102">.NET에서 형식 변환 표</span><span class="sxs-lookup"><span data-stu-id="6afd6-102">Type Conversion Tables in .NET</span></span>
<span data-ttu-id="6afd6-103">확대 변환은 한 형식의 값을 크기가 같거나 더 큰 다른 형식으로 변환할 때 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="6afd6-103">Widening conversion occurs when a value of one type is converted to another type that is of equal or greater size.</span></span> <span data-ttu-id="6afd6-104">축소 변환은 한 형식의 값을 크기가 더 작은 다른 형식의 값으로 변환할 때 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="6afd6-104">A narrowing conversion occurs when a value of one type is converted to a value of another type that is of a smaller size.</span></span> <span data-ttu-id="6afd6-105">이 항목의 표에서는 두 가지 유형의 변환에서 모두 나타나는 동작을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6afd6-105">The tables in this topic illustrate the behaviors exhibited by both types of conversions.</span></span>  
  
## <a name="widening-conversions"></a><span data-ttu-id="6afd6-106">확대 변환</span><span class="sxs-lookup"><span data-stu-id="6afd6-106">Widening Conversions</span></span>  
 <span data-ttu-id="6afd6-107">다음 표에서 정보의 손실 없이 수행할 수 있는 확대 변환에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="6afd6-107">The following table describes the widening conversions that can be performed without the loss of information.</span></span>  
  
|<span data-ttu-id="6afd6-108">형식</span><span class="sxs-lookup"><span data-stu-id="6afd6-108">Type</span></span>|<span data-ttu-id="6afd6-109">데이터 손실 없이 다음 형식으로 변환할 수 있음</span><span class="sxs-lookup"><span data-stu-id="6afd6-109">Can be converted without data loss to</span></span>|  
|----------|-------------------------------------------|  
|<xref:System.Byte>|<span data-ttu-id="6afd6-110"><xref:System.UInt16>, <xref:System.Int16>, <xref:System.UInt32>, <xref:System.Int32>, <xref:System.UInt64>, <xref:System.Int64>, <xref:System.Single>, <xref:System.Double>, <xref:System.Decimal></span><span class="sxs-lookup"><span data-stu-id="6afd6-110"><xref:System.UInt16>, <xref:System.Int16>, <xref:System.UInt32>, <xref:System.Int32>, <xref:System.UInt64>, <xref:System.Int64>, <xref:System.Single>, <xref:System.Double>, <xref:System.Decimal></span></span>|  
|<xref:System.SByte>|<span data-ttu-id="6afd6-111"><xref:System.Int16>, <xref:System.Int32>, <xref:System.Int64>, <xref:System.Single>, <xref:System.Double>, <xref:System.Decimal></span><span class="sxs-lookup"><span data-stu-id="6afd6-111"><xref:System.Int16>, <xref:System.Int32>, <xref:System.Int64>, <xref:System.Single>, <xref:System.Double>, <xref:System.Decimal></span></span>|  
|<xref:System.Int16>|<span data-ttu-id="6afd6-112"><xref:System.Int32>, <xref:System.Int64>, <xref:System.Single>, <xref:System.Double>, <xref:System.Decimal></span><span class="sxs-lookup"><span data-stu-id="6afd6-112"><xref:System.Int32>, <xref:System.Int64>, <xref:System.Single>, <xref:System.Double>, <xref:System.Decimal></span></span>|  
|<xref:System.UInt16>|<span data-ttu-id="6afd6-113"><xref:System.UInt32>, <xref:System.Int32>, <xref:System.UInt64>, <xref:System.Int64>, <xref:System.Single>, <xref:System.Double>, <xref:System.Decimal></span><span class="sxs-lookup"><span data-stu-id="6afd6-113"><xref:System.UInt32>, <xref:System.Int32>, <xref:System.UInt64>, <xref:System.Int64>, <xref:System.Single>, <xref:System.Double>, <xref:System.Decimal></span></span>|  
|<xref:System.Char>|<span data-ttu-id="6afd6-114"><xref:System.UInt16>, <xref:System.UInt32>, <xref:System.Int32>, <xref:System.UInt64>, <xref:System.Int64>, <xref:System.Single>, <xref:System.Double>, <xref:System.Decimal></span><span class="sxs-lookup"><span data-stu-id="6afd6-114"><xref:System.UInt16>, <xref:System.UInt32>, <xref:System.Int32>, <xref:System.UInt64>, <xref:System.Int64>, <xref:System.Single>, <xref:System.Double>, <xref:System.Decimal></span></span>|  
|<xref:System.Int32>|<span data-ttu-id="6afd6-115"><xref:System.Int64>, <xref:System.Double>, <xref:System.Decimal></span><span class="sxs-lookup"><span data-stu-id="6afd6-115"><xref:System.Int64>, <xref:System.Double>, <xref:System.Decimal></span></span>|  
|<xref:System.UInt32>|<span data-ttu-id="6afd6-116"><xref:System.Int64>, <xref:System.UInt64>, <xref:System.Double>, <xref:System.Decimal></span><span class="sxs-lookup"><span data-stu-id="6afd6-116"><xref:System.Int64>, <xref:System.UInt64>, <xref:System.Double>, <xref:System.Decimal></span></span>|  
|<xref:System.Int64>|<xref:System.Decimal>|  
|<xref:System.UInt64>|<xref:System.Decimal>|  
|<xref:System.Single>|<xref:System.Double>|  
  
 <span data-ttu-id="6afd6-117">일부 확장을 변환 <xref:System.Single> 또는 <xref:System.Double> 정밀도의 손실 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6afd6-117">Some widening conversions to <xref:System.Single> or <xref:System.Double> can cause a loss of precision.</span></span> <span data-ttu-id="6afd6-118">다음 표에서는 때때로 정보 손실이 발생할 수 있는 확대 변환에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6afd6-118">The following table describes the widening conversions that sometimes result in a loss of information.</span></span>  
  
|<span data-ttu-id="6afd6-119">형식</span><span class="sxs-lookup"><span data-stu-id="6afd6-119">Type</span></span>|<span data-ttu-id="6afd6-120">다음 형식으로 변환할 수 있음</span><span class="sxs-lookup"><span data-stu-id="6afd6-120">Can be converted to</span></span>|  
|----------|-------------------------|  
|<xref:System.Int32>|<xref:System.Single>|  
|<xref:System.UInt32>|<xref:System.Single>|  
|<xref:System.Int64>|<span data-ttu-id="6afd6-121"><xref:System.Single>, <xref:System.Double></span><span class="sxs-lookup"><span data-stu-id="6afd6-121"><xref:System.Single>, <xref:System.Double></span></span>|  
|<xref:System.UInt64>|<span data-ttu-id="6afd6-122"><xref:System.Single>, <xref:System.Double></span><span class="sxs-lookup"><span data-stu-id="6afd6-122"><xref:System.Single>, <xref:System.Double></span></span>|  
|<xref:System.Decimal>|<span data-ttu-id="6afd6-123"><xref:System.Single>, <xref:System.Double></span><span class="sxs-lookup"><span data-stu-id="6afd6-123"><xref:System.Single>, <xref:System.Double></span></span>|  
  
## <a name="narrowing-conversions"></a><span data-ttu-id="6afd6-124">축소 변환</span><span class="sxs-lookup"><span data-stu-id="6afd6-124">Narrowing Conversions</span></span>  
 <span data-ttu-id="6afd6-125">범위가 좁은 <xref:System.Single> 또는 <xref:System.Double> 정보의 손실 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6afd6-125">A narrowing conversion to <xref:System.Single> or <xref:System.Double> can cause a loss of information.</span></span> <span data-ttu-id="6afd6-126">대상 형식이 소스 크기를 제대로 표시할 수 없는 경우 결과 형식이 상수 `PositiveInfinity` 또는 `NegativeInfinity`로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="6afd6-126">If the target type cannot properly express the magnitude of the source, the resulting type is set to the constant `PositiveInfinity` or `NegativeInfinity`.</span></span> <span data-ttu-id="6afd6-127">`PositiveInfinity`양의 숫자를 0으로 나눈 결과 및 경우에 반환 됩니다의 값을 <xref:System.Single> 또는 <xref:System.Double> 의 값을 초과 `MaxValue` 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="6afd6-127">`PositiveInfinity` results from dividing a positive number by zero and is also returned when the value of a <xref:System.Single> or <xref:System.Double> exceeds the value of the `MaxValue` field.</span></span> <span data-ttu-id="6afd6-128">`NegativeInfinity`음수 0으로 나눈 결과 및 경우에 반환 됩니다의 값을 <xref:System.Single> 또는 <xref:System.Double> 의 값 보다 작으면는 `MinValue` 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="6afd6-128">`NegativeInfinity` results from dividing a negative number by zero and is also returned when the value of a <xref:System.Single> or <xref:System.Double> falls below the value of the `MinValue` field.</span></span> <span data-ttu-id="6afd6-129">변환 된 <xref:System.Double> 에 <xref:System.Single> 발생할 수 있습니다 `PositiveInfinity` 또는 `NegativeInfinity`합니다.</span><span class="sxs-lookup"><span data-stu-id="6afd6-129">A conversion from a <xref:System.Double> to a <xref:System.Single> might result in `PositiveInfinity` or `NegativeInfinity`.</span></span>  
  
 <span data-ttu-id="6afd6-130">축소 변환 시 다른 데이터 형식에 대한 정보 손실도 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6afd6-130">A narrowing conversion can also result in a loss of information for other data types.</span></span> <span data-ttu-id="6afd6-131">그러나는 <xref:System.OverflowException> 변환 되는 형식의 값이 있는 대상 유형으로 지정 된 범위를 벗어나는 경우 throw 되 `MaxValue` 및 `MinValue` 필드 및 변환 하는 대상의 값을 확인 하기 위해 런타임에서 확인란이 형식 초과 하지 않는 해당 `MaxValue` 또는 `MinValue`합니다.</span><span class="sxs-lookup"><span data-stu-id="6afd6-131">However, an <xref:System.OverflowException> is thrown if the value of a type that is being converted falls outside of the range specified by the target type's `MaxValue` and `MinValue` fields, and the conversion is checked by the runtime to ensure that the value of the target type does not exceed its `MaxValue` or `MinValue`.</span></span> <span data-ttu-id="6afd6-132">변환에 의해 수행 되는 <xref:System.Convert?displayProperty=nameWithType> 클래스는 항상 이런이 방식으로 확인 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6afd6-132">Conversions that are performed with the <xref:System.Convert?displayProperty=nameWithType> class are always checked in this manner.</span></span>  
  
 <span data-ttu-id="6afd6-133">다음 표에서 throw 하는 변환은 <xref:System.OverflowException> 를 사용 하 여 <xref:System.Convert?displayProperty=nameWithType> 또는 변환 되는 형식 값의 결과 형식이 정의 된 범위를 벗어나는 경우 검사 된 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="6afd6-133">The following table lists conversions that throw an <xref:System.OverflowException> using <xref:System.Convert?displayProperty=nameWithType> or any checked conversion if the value of the type being converted is outside the defined range of the resulting type.</span></span>  
  
|<span data-ttu-id="6afd6-134">형식</span><span class="sxs-lookup"><span data-stu-id="6afd6-134">Type</span></span>|<span data-ttu-id="6afd6-135">다음 형식으로 변환할 수 있음</span><span class="sxs-lookup"><span data-stu-id="6afd6-135">Can be converted to</span></span>|  
|----------|-------------------------|  
|<xref:System.Byte>|<xref:System.SByte>|  
|<xref:System.SByte>|<span data-ttu-id="6afd6-136"><xref:System.Byte>, <xref:System.UInt16>, <xref:System.UInt32>, <xref:System.UInt64></span><span class="sxs-lookup"><span data-stu-id="6afd6-136"><xref:System.Byte>, <xref:System.UInt16>, <xref:System.UInt32>, <xref:System.UInt64></span></span>|  
|<xref:System.Int16>|<span data-ttu-id="6afd6-137"><xref:System.Byte>, <xref:System.SByte>, <xref:System.UInt16></span><span class="sxs-lookup"><span data-stu-id="6afd6-137"><xref:System.Byte>, <xref:System.SByte>, <xref:System.UInt16></span></span>|  
|<xref:System.UInt16>|<span data-ttu-id="6afd6-138"><xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16></span><span class="sxs-lookup"><span data-stu-id="6afd6-138"><xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16></span></span>|  
|<xref:System.Int32>|<span data-ttu-id="6afd6-139"><xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>,<xref:System.UInt32></span><span class="sxs-lookup"><span data-stu-id="6afd6-139"><xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>,<xref:System.UInt32></span></span>|  
|<xref:System.UInt32>|<span data-ttu-id="6afd6-140"><xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>, <xref:System.Int32></span><span class="sxs-lookup"><span data-stu-id="6afd6-140"><xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>, <xref:System.Int32></span></span>|  
|<xref:System.Int64>|<span data-ttu-id="6afd6-141"><xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>, <xref:System.Int32>,<xref:System.UInt32>,<xref:System.UInt64></span><span class="sxs-lookup"><span data-stu-id="6afd6-141"><xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>, <xref:System.Int32>,<xref:System.UInt32>,<xref:System.UInt64></span></span>|  
|<xref:System.UInt64>|<span data-ttu-id="6afd6-142"><xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>, <xref:System.Int32>, <xref:System.UInt32>, <xref:System.Int64></span><span class="sxs-lookup"><span data-stu-id="6afd6-142"><xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>, <xref:System.Int32>, <xref:System.UInt32>, <xref:System.Int64></span></span>|  
|<xref:System.Decimal>|<span data-ttu-id="6afd6-143"><xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>, <xref:System.Int32>, <xref:System.UInt32>, <xref:System.Int64>, <xref:System.UInt64></span><span class="sxs-lookup"><span data-stu-id="6afd6-143"><xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>, <xref:System.Int32>, <xref:System.UInt32>, <xref:System.Int64>, <xref:System.UInt64></span></span>|  
|<xref:System.Single>|<span data-ttu-id="6afd6-144"><xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>, <xref:System.Int32>, <xref:System.UInt32>, <xref:System.Int64>, <xref:System.UInt64></span><span class="sxs-lookup"><span data-stu-id="6afd6-144"><xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>, <xref:System.Int32>, <xref:System.UInt32>, <xref:System.Int64>, <xref:System.UInt64></span></span>|  
|<xref:System.Double>|<span data-ttu-id="6afd6-145"><xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>, <xref:System.Int32>, <xref:System.UInt32>, <xref:System.Int64>, <xref:System.UInt64></span><span class="sxs-lookup"><span data-stu-id="6afd6-145"><xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>, <xref:System.Int32>, <xref:System.UInt32>, <xref:System.Int64>, <xref:System.UInt64></span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6afd6-146">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6afd6-146">See Also</span></span>  
 <xref:System.Convert?displayProperty=nameWithType>  
 [<span data-ttu-id="6afd6-147">.NET에서 형식 변환</span><span class="sxs-lookup"><span data-stu-id="6afd6-147">Type Conversion in .NET</span></span>](../../../docs/standard/base-types/type-conversion.md)
