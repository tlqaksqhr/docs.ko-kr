---
title: "데이터 계약의 열거형 형식"
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
helpviewer_keywords: data contracts [WCF], enumeration types
ms.assetid: b5d694da-68cb-4b74-a5fb-75108a68ec3b
caps.latest.revision: "13"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: ea76ae136695ce2dc9eca0a9c7660e4e1ffe547d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="enumeration-types-in-data-contracts"></a><span data-ttu-id="a6198-102">데이터 계약의 열거형 형식</span><span class="sxs-lookup"><span data-stu-id="a6198-102">Enumeration Types in Data Contracts</span></span>
<span data-ttu-id="a6198-103">데이터 계약 모델에 열거형을 표현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6198-103">Enumerations can be expressed in the data contract model.</span></span> <span data-ttu-id="a6198-104">이 항목에서는 프로그래밍 모델을 설명하는 여러 예를 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="a6198-104">This topic walks through several examples that explain the programming model.</span></span>  
  
## <a name="enumeration-basics"></a><span data-ttu-id="a6198-105">열거형 기본 사항</span><span class="sxs-lookup"><span data-stu-id="a6198-105">Enumeration Basics</span></span>  
 <span data-ttu-id="a6198-106">데이터 계약 모델에 열거형 형식을 사용하는 방법 중 하나는 형식에 <xref:System.Runtime.Serialization.DataContractAttribute> 특성을 적용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a6198-106">One way to use enumeration types in the data contract model is to apply the <xref:System.Runtime.Serialization.DataContractAttribute> attribute to the type.</span></span> <span data-ttu-id="a6198-107">그런 다음 데이터 계약에 포함할 각 멤버에 대해 <xref:System.Runtime.Serialization.EnumMemberAttribute> 특성을 적용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6198-107">You must then apply the <xref:System.Runtime.Serialization.EnumMemberAttribute> attribute to each member that must be included in the data contract.</span></span>  
  
 <span data-ttu-id="a6198-108">다음 예제에서는 두 개의 클래스가 나옵니다.</span><span class="sxs-lookup"><span data-stu-id="a6198-108">The following example shows two classes.</span></span> <span data-ttu-id="a6198-109">첫 번째 클래스에서는 열거형을 사용하고, 두 번째 클래스에서는 열거형을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="a6198-109">The first uses the enumeration and the second defines the enumeration.</span></span>  
  
 [!code-csharp[c_DataContractEnumerations#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontractenumerations/cs/source.cs#1)]
 [!code-vb[c_DataContractEnumerations#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontractenumerations/vb/source.vb#1)]  
  
 <span data-ttu-id="a6198-110">`Car` 클래스의 인스턴스는 `condition` 필드가 `New`, `Used` 또는 `Rental` 값 중 하나로 설정된 경우에만 보내고 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6198-110">An instance of the `Car` class can be sent or received only if the `condition` field is set to one of the values `New`, `Used`, or `Rental`.</span></span> <span data-ttu-id="a6198-111">`condition`이 `Broken` 또는 `Stolen`이면 <xref:System.Runtime.Serialization.SerializationException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6198-111">If the `condition` is `Broken` or `Stolen`, a <xref:System.Runtime.Serialization.SerializationException> is thrown.</span></span>  
  
 <span data-ttu-id="a6198-112">열거형 데이터 계약에도 보통 때와 같이 <xref:System.Runtime.Serialization.DataContractAttribute> 속성(<xref:System.Runtime.Serialization.DataContractAttribute.Name%2A> 및 <xref:System.Runtime.Serialization.DataContractAttribute.Namespace%2A>)을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6198-112">You can use the <xref:System.Runtime.Serialization.DataContractAttribute> properties (<xref:System.Runtime.Serialization.DataContractAttribute.Name%2A> and <xref:System.Runtime.Serialization.DataContractAttribute.Namespace%2A>) as usual for enumeration data contracts.</span></span>  
  
### <a name="enumeration-member-values"></a><span data-ttu-id="a6198-113">열거형 멤버 값</span><span class="sxs-lookup"><span data-stu-id="a6198-113">Enumeration Member Values</span></span>  
 <span data-ttu-id="a6198-114">일반적으로 데이터 계약에는 숫자 값이 아닌 열거형 멤버 이름이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6198-114">Generally the data contract includes enumeration member names, not numerical values.</span></span> <span data-ttu-id="a6198-115">하지만 데이터 계약 모델을 사용하는 경우 받는 쪽이 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트이면 내보낸 스키마에서 숫자 값을 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="a6198-115">However, when using the data contract model, if the receiving side is a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client, the exported schema preserves the numerical values.</span></span> <span data-ttu-id="a6198-116">이 하지는 경우 사용 하는 경우는 [XmlSerializer 클래스를 사용 하 여](../../../../docs/framework/wcf/feature-details/using-the-xmlserializer-class.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a6198-116">Note that this is not the case when using the [Using the XmlSerializer Class](../../../../docs/framework/wcf/feature-details/using-the-xmlserializer-class.md).</span></span>  
  
 <span data-ttu-id="a6198-117">앞의 예에서 `condition`이 `Used`로 설정되어 있고 데이터가 XML로 serialize된 경우 결과 XML은 `<condition>Used</condition>`이며 `<condition>1</condition>`이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="a6198-117">In the preceding example, if `condition` is set to `Used` and the data is serialized to XML, the resulting XML is `<condition>Used</condition>` and not `<condition>1</condition>`.</span></span> <span data-ttu-id="a6198-118">따라서 다음 데이터 계약은 `CarConditionEnum`의 데이터 계약에 해당됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6198-118">Therefore, the following data contract is equivalent to the data contract of `CarConditionEnum`.</span></span>  
  
 [!code-csharp[c_DataContractEnumerations#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontractenumerations/cs/source.cs#2)]
 [!code-vb[c_DataContractEnumerations#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontractenumerations/vb/source.vb#2)]  
  
 <span data-ttu-id="a6198-119">예를 들어, 보내는 쪽에 `CarConditionEnum`을 사용하고 받는 쪽에 `CarConditionWithNumbers`를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6198-119">For example, you can use `CarConditionEnum` on the sending side and `CarConditionWithNumbers` on the receiving side.</span></span> <span data-ttu-id="a6198-120">보내는 쪽에서는 `Used`에 값 "1"을 사용하고 받는 쪽에서는 값 "20"을 사용하지만 XML 표현은 양쪽 모두 `<condition>Used</condition>`입니다.</span><span class="sxs-lookup"><span data-stu-id="a6198-120">Although the sending side uses the value "1" for `Used` and the receiving side uses the value "20," the XML representation is `<condition>Used</condition>` for both sides.</span></span>  
  
 <span data-ttu-id="a6198-121">데이터 계약에 포함되려면 <xref:System.Runtime.Serialization.EnumMemberAttribute> 특성을 적용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6198-121">To be included in the data contract, you must apply the <xref:System.Runtime.Serialization.EnumMemberAttribute> attribute.</span></span> <span data-ttu-id="a6198-122">[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]에서는 항상 열거형에 모든 열거형의 기본값인 특수 값 0을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6198-122">In the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], you can always apply the special value 0 (zero) to an enumeration, which is also the default value for any enumeration.</span></span> <span data-ttu-id="a6198-123">하지만 이 특수 값 0도 <xref:System.Runtime.Serialization.EnumMemberAttribute> 특성으로 표시하지 않으면 serialize할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a6198-123">However, even this special zero value cannot be serialized unless it is marked with the <xref:System.Runtime.Serialization.EnumMemberAttribute> attribute.</span></span>  
  
 <span data-ttu-id="a6198-124">여기에는 두 가지 예외 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6198-124">There are two exceptions to this:</span></span>  
  
-   <span data-ttu-id="a6198-125">플래그 열거형(이 항목의 뒷부분에서 설명).</span><span class="sxs-lookup"><span data-stu-id="a6198-125">Flag enumerations (discussed later in this topic).</span></span>  
  
-   <span data-ttu-id="a6198-126"><xref:System.Runtime.Serialization.DataMemberAttribute.EmitDefaultValue%2A> 속성이 `false`로 설정된 열거형 데이터 멤버. 이 경우 값이 0인 열거형은 serialize할 데이터에서 생략됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6198-126">Enumeration data members with the <xref:System.Runtime.Serialization.DataMemberAttribute.EmitDefaultValue%2A> property set to `false` (in which case, the enumeration with the value zero is omitted from the serialized data).</span></span>  
  
### <a name="customizing-enumeration-member-values"></a><span data-ttu-id="a6198-127">열거형 멤버 값 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="a6198-127">Customizing Enumeration Member Values</span></span>  
 <span data-ttu-id="a6198-128"><xref:System.Runtime.Serialization.EnumMemberAttribute.Value%2A> 특성의 <xref:System.Runtime.Serialization.EnumMemberAttribute> 속성을 사용하여 데이터 계약의 일부를 구성하는 열거형 멤버 값을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6198-128">You can customize the enumeration member value that forms a part of the data contract by using the <xref:System.Runtime.Serialization.EnumMemberAttribute.Value%2A> property of the <xref:System.Runtime.Serialization.EnumMemberAttribute> attribute.</span></span>  
  
 <span data-ttu-id="a6198-129">예를 들어, 다음 데이터 계약도 `CarConditionEnum`의 데이터 계약에 해당됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6198-129">For example, the following data contract is also equivalent to the data contract of the `CarConditionEnum`.</span></span>  
  
 [!code-csharp[c_DataContractEnumerations#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontractenumerations/cs/source.cs#3)]
 [!code-vb[c_DataContractEnumerations#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontractenumerations/vb/source.vb#3)]  
  
 <span data-ttu-id="a6198-130">serialize된 `PreviouslyOwned` 값의 XML 표현은 `<condition>Used</condition>`입니다.</span><span class="sxs-lookup"><span data-stu-id="a6198-130">When serialized, the value of `PreviouslyOwned` has the XML representation `<condition>Used</condition>`.</span></span>  
  
## <a name="simple-enumerations"></a><span data-ttu-id="a6198-131">단순 열거형</span><span class="sxs-lookup"><span data-stu-id="a6198-131">Simple Enumerations</span></span>  
 <span data-ttu-id="a6198-132"><xref:System.Runtime.Serialization.DataContractAttribute> 특성이 적용되지 않은 열거형 형식을 serialize할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6198-132">You can also serialize enumeration types to which the <xref:System.Runtime.Serialization.DataContractAttribute> attribute has not been applied.</span></span> <span data-ttu-id="a6198-133">그러한 열거형 형식은 위 설명과 완전히 같은 방식으로 취급되지만, <xref:System.NonSerializedAttribute> 특성이 적용되지 않은 모든 멤버가 <xref:System.Runtime.Serialization.EnumMemberAttribute> 특성이 적용된 것처럼 취급된다는 점이 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="a6198-133">Such enumeration types are treated exactly as previously described, except that every member (that does not have the <xref:System.NonSerializedAttribute> attribute applied) is treated as if the <xref:System.Runtime.Serialization.EnumMemberAttribute> attribute has been applied.</span></span> <span data-ttu-id="a6198-134">예를 들어, 다음 열거형에는 위의 `CarConditionEnum` 예제에 해당되는 데이터 계약이 암시적으로 존재합니다.</span><span class="sxs-lookup"><span data-stu-id="a6198-134">For example, the following enumeration implicitly has a data contract equivalent to the preceding `CarConditionEnum` example.</span></span>  
  
 [!code-csharp[c_DataContractEnumerations#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontractenumerations/cs/source.cs#6)]
 [!code-vb[c_DataContractEnumerations#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontractenumerations/vb/source.vb#6)]  
  
 <span data-ttu-id="a6198-135">열거형의 데이터 계약 이름 및 네임스페이스와 열거형 멤버 값을 사용자 지정할 필요가 없는 경우 단순 열거형을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6198-135">You can use simple enumerations when you do not need to customize the enumeration's data contract name and namespace and the enumeration member values.</span></span>  
  
#### <a name="notes-on-simple-enumerations"></a><span data-ttu-id="a6198-136">단순 열거형에 대한 참고 사항</span><span class="sxs-lookup"><span data-stu-id="a6198-136">Notes on Simple Enumerations</span></span>  
 <span data-ttu-id="a6198-137"><xref:System.Runtime.Serialization.EnumMemberAttribute> 특성을 단순 열거형에 적용해도 아무 영향이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a6198-137">Applying the <xref:System.Runtime.Serialization.EnumMemberAttribute> attribute to simple enumerations has no effect.</span></span>  
  
 <span data-ttu-id="a6198-138"><xref:System.SerializableAttribute> 특성이 열거형에 적용되었는지 여부도 관계 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a6198-138">It makes no difference whether or not the <xref:System.SerializableAttribute> attribute is applied to the enumeration.</span></span>  
  
 <span data-ttu-id="a6198-139"><xref:System.Runtime.Serialization.DataContractSerializer> 클래스에서 열거형 멤버에 적용된 <xref:System.NonSerializedAttribute> 특성을 따른다는 점은 <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> 및 <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter>의 동작과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="a6198-139">The fact that the <xref:System.Runtime.Serialization.DataContractSerializer> class honors the <xref:System.NonSerializedAttribute> attribute applied to enumeration members is different from the behavior of the <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> and the <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter>.</span></span> <span data-ttu-id="a6198-140">이 두 가지 serializer는 모두 <xref:System.NonSerializedAttribute> 특성을 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="a6198-140">Both of those serializers ignore the <xref:System.NonSerializedAttribute> attribute.</span></span>  
  
## <a name="flag-enumerations"></a><span data-ttu-id="a6198-141">플래그 열거형</span><span class="sxs-lookup"><span data-stu-id="a6198-141">Flag Enumerations</span></span>  
 <span data-ttu-id="a6198-142"><xref:System.FlagsAttribute> 특성을 열거형에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6198-142">You can apply the <xref:System.FlagsAttribute> attribute to enumerations.</span></span> <span data-ttu-id="a6198-143">이 경우 0개 이상의 열거형 값 목록을 동시에 보내거나 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6198-143">In that case, a list of zero or more enumeration values can be sent or received simultaneously.</span></span>  
  
 <span data-ttu-id="a6198-144">그러려면 플래그 열거형에 <xref:System.Runtime.Serialization.DataContractAttribute> 특성을 적용한 다음 2의 거듭제곱에 해당되는 모든 멤버를 <xref:System.Runtime.Serialization.EnumMemberAttribute> 특성으로 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="a6198-144">To do so, apply the <xref:System.Runtime.Serialization.DataContractAttribute> attribute to the flag enumeration and then mark all the members that are powers of two with the <xref:System.Runtime.Serialization.EnumMemberAttribute> attribute.</span></span> <span data-ttu-id="a6198-145">플래그 열거형을 사용하려면 2의 거듭제곱이 끊어지지 않고 순서대로 진행되어야 합니다(예: 1, 2, 4, 8, 16, 32, 64).</span><span class="sxs-lookup"><span data-stu-id="a6198-145">Note that to use a flag enumeration, the progression must be an uninterrupted sequence of powers of 2 (for example, 1, 2, 4, 8, 16, 32, 64).</span></span>  
  
 <span data-ttu-id="a6198-146">다음 단계는 플래그의 열거형 값을 보내는 경우에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6198-146">The following steps apply to sending a flag's enumeration value:</span></span>  
  
1.  <span data-ttu-id="a6198-147">숫자 값에 매핑되는 열거형 멤버를 찾아 봅니다(<xref:System.Runtime.Serialization.EnumMemberAttribute> 특성 적용).</span><span class="sxs-lookup"><span data-stu-id="a6198-147">Attempt to find an enumeration member (with the <xref:System.Runtime.Serialization.EnumMemberAttribute> attribute applied) that maps to the numeric value.</span></span> <span data-ttu-id="a6198-148">찾은 경우 해당 멤버만 포함하는 목록을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="a6198-148">If found, send a list that contains just that member.</span></span>  
  
2.  <span data-ttu-id="a6198-149">합의 각 부분에 매핑되는 열거형 멤버가 있는(각각 <xref:System.Runtime.Serialization.EnumMemberAttribute> 특성 적용) 숫자 값을 합으로 정리해 봅니다.</span><span class="sxs-lookup"><span data-stu-id="a6198-149">Attempt to break the numeric value into a sum such that there are enumeration members (each with the <xref:System.Runtime.Serialization.EnumMemberAttribute> attribute applied) that map to each part of the sum.</span></span> <span data-ttu-id="a6198-150">해당되는 모든 멤버의 목록을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="a6198-150">Send the list of all these members.</span></span> <span data-ttu-id="a6198-151">*탐욕 알고리즘* 를 사용 하 여 그런 합을 찾이 없기 때문에 그런 합이 존재 하는 경우에 발견 된 다 고 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6198-151">Note that the *greedy algorithm* is used to find such a sum, and thus there is no guarantee that such a sum is found even if it is present.</span></span> <span data-ttu-id="a6198-152">이 문제를 방지하려면 열거형 멤버의 숫자 값이 2의 거듭제곱이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6198-152">To avoid this problem, make sure that the numeric values of the enumeration members are powers of two.</span></span>  
  
3.  <span data-ttu-id="a6198-153">앞의 두 단계가 실패한 경우 숫자 값이 0이 아니면 <xref:System.Runtime.Serialization.SerializationException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6198-153">If the preceding two steps fail, and the numeric value is nonzero, throw a <xref:System.Runtime.Serialization.SerializationException>.</span></span> <span data-ttu-id="a6198-154">숫자 값이 0이면 빈 목록을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="a6198-154">If the numeric value is zero, send the empty list.</span></span>  
  
### <a name="example"></a><span data-ttu-id="a6198-155">예제</span><span class="sxs-lookup"><span data-stu-id="a6198-155">Example</span></span>  
 <span data-ttu-id="a6198-156">다음 열거형 예는 플래그 작업에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6198-156">The following enumeration example can be used in a flag operation.</span></span>  
  
 [!code-csharp[c_DataContractEnumerations#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontractenumerations/cs/source.cs#4)]
 [!code-vb[c_DataContractEnumerations#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontractenumerations/vb/source.vb#4)]  
  
 <span data-ttu-id="a6198-157">다음 예제의 값은 표시된 대로 serialize됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6198-157">The following example values are serialized as indicated.</span></span>  
  
 [!code-csharp[c_DataContractEnumerations#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontractenumerations/cs/source.cs#5)]
 [!code-vb[c_DataContractEnumerations#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontractenumerations/vb/source.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="a6198-158">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a6198-158">See Also</span></span>  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
 [<span data-ttu-id="a6198-159">데이터 계약 사용</span><span class="sxs-lookup"><span data-stu-id="a6198-159">Using Data Contracts</span></span>](../../../../docs/framework/wcf/feature-details/using-data-contracts.md)  
 [<span data-ttu-id="a6198-160">Specifying Data Transfer in Service Contracts</span><span class="sxs-lookup"><span data-stu-id="a6198-160">Specifying Data Transfer in Service Contracts</span></span>](../../../../docs/framework/wcf/feature-details/specifying-data-transfer-in-service-contracts.md)
