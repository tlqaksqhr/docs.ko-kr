---
title: "Serialization 지침"
ms.date: 03/30/2017
ms.prod: .net
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- serialization, guidelines
- binary serialization, guidelines
ms.assetid: ebbeddff-179d-443f-bf08-9c373199a73a
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a695e10ae9b074f0f9dc913d2f687c82e00475dd
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="serialization-guidelines"></a><span data-ttu-id="8a875-102">Serialization 지침</span><span class="sxs-lookup"><span data-stu-id="8a875-102">Serialization guidelines</span></span>
<span data-ttu-id="8a875-103">이 문서에서는 serialize될 API를 디자인할 때 고려해야 할 지침을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8a875-103">This document lists the guidelines to consider when designing an API to be serialized.</span></span>  

[!INCLUDE [binary-serialization-warning](../../../includes/binary-serialization-warning.md)]
  
 <span data-ttu-id="8a875-104">.NET에서는 다양한 serialization 시나리오에 적합한 세 가지의 기본 serialization 기술을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8a875-104">.NET offers three main serialization technologies that are optimized for various serialization scenarios.</span></span> <span data-ttu-id="8a875-105">다음 표에서는 이러한 기술 및 해당 기술과 관련된 기본 .NET 형식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8a875-105">The following table lists these technologies and the main .NET types related to these technologies.</span></span>  
  
|<span data-ttu-id="8a875-106">기술</span><span class="sxs-lookup"><span data-stu-id="8a875-106">Technology</span></span>|<span data-ttu-id="8a875-107">관련 클래스</span><span class="sxs-lookup"><span data-stu-id="8a875-107">Relevant Classes</span></span>|<span data-ttu-id="8a875-108">참고</span><span class="sxs-lookup"><span data-stu-id="8a875-108">Notes</span></span>|  
|----------------|----------------------|-----------|  
|<span data-ttu-id="8a875-109">데이터 계약 Serialization</span><span class="sxs-lookup"><span data-stu-id="8a875-109">Data Contract Serialization</span></span>|<xref:System.Runtime.Serialization.DataContractAttribute><br /><br /> <xref:System.Runtime.Serialization.DataMemberAttribute><br /><br /> <xref:System.Runtime.Serialization.DataContractSerializer><br /><br /> <xref:System.Runtime.Serialization.NetDataContractSerializer><br /><br /> <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer><br /><br /> <xref:System.Runtime.Serialization.ISerializable>|<span data-ttu-id="8a875-110">일반 지속성</span><span class="sxs-lookup"><span data-stu-id="8a875-110">General persistence</span></span><br /><br /> <span data-ttu-id="8a875-111">웹 서비스</span><span class="sxs-lookup"><span data-stu-id="8a875-111">Web Services</span></span><br /><br /> <span data-ttu-id="8a875-112">JSON</span><span class="sxs-lookup"><span data-stu-id="8a875-112">JSON</span></span>|  
|<span data-ttu-id="8a875-113">XML Serialization</span><span class="sxs-lookup"><span data-stu-id="8a875-113">XML Serialization</span></span>|<xref:System.Xml.Serialization.XmlSerializer>|<span data-ttu-id="8a875-114">XML 형식</span><span class="sxs-lookup"><span data-stu-id="8a875-114">XML format</span></span> <br /><span data-ttu-id="8a875-115">모든 권한 포함</span><span class="sxs-lookup"><span data-stu-id="8a875-115">with full control</span></span>|  
|<span data-ttu-id="8a875-116">런타임 -Serialization(이진 및 SOAP)</span><span class="sxs-lookup"><span data-stu-id="8a875-116">Runtime -Serialization (Binary and SOAP)</span></span>|<xref:System.SerializableAttribute><br /><br /> <xref:System.Runtime.Serialization.ISerializable><br /><br /> <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter><br /><br /> <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter>|<span data-ttu-id="8a875-117">.NET Remoting</span><span class="sxs-lookup"><span data-stu-id="8a875-117">.NET Remoting</span></span>|  
  
 <span data-ttu-id="8a875-118">새로운 형식을 디자인할 때 이러한 기술 중 해당 형식(있는 경우)이 지원해야 하는 기술을 결정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a875-118">When you design new types, you should decide which, if any, of these technologies those types need to support.</span></span> <span data-ttu-id="8a875-119">다음 지침은 이러한 기술을 선택하는 방법과 해당 지원을 제공하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8a875-119">The following guidelines describe how to make that choice and how to provide such support.</span></span> <span data-ttu-id="8a875-120">이 지침은 응용 프로그램 또는 라이브러리를 구현하는 데 사용해야 하는 serialization 기술을 선택하는 데 도움을 주기 위해 만든 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="8a875-120">These guidelines are not meant to help you choose which serialization technology you should use in the implementation of your application or library.</span></span> <span data-ttu-id="8a875-121">이 지침은 API 디자인과 직접 관련되어 있지 않으므로 이 항목의 범위 내에 포함되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8a875-121">Such guidelines are not directly related to API design and thus are not within the scope of this topic.</span></span>  
  
## <a name="guidelines"></a><span data-ttu-id="8a875-122">지침</span><span class="sxs-lookup"><span data-stu-id="8a875-122">Guidelines</span></span>  
  
-   <span data-ttu-id="8a875-123">새로운 형식을 디자인할 때는 serialization을 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a875-123">DO think about serialization when you design new types.</span></span>  
  
     <span data-ttu-id="8a875-124">프로그램에서 형식의 인스턴스를 유지하거나 전송해야 할 수 있으므로 serialization은 형식에 대해 중요한 디자인 고려 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="8a875-124">Serialization is an important design consideration for any type, because programs might need to persist or transmit instances of the type.</span></span>  
  
### <a name="choosing-the-right-serialization-technology-to-support"></a><span data-ttu-id="8a875-125">지원할 올바른 Serialization 기술 선택</span><span class="sxs-lookup"><span data-stu-id="8a875-125">Choosing the right serialization technology to support</span></span>  
 <span data-ttu-id="8a875-126">지정된 형식은 하나 이상의 serialization 기술을 지원하거나 serialization 기술을 전혀 지원하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a875-126">Any given type can support none, one, or more of the serialization technologies.</span></span>  
  
-   <span data-ttu-id="8a875-127">형식의 인스턴스가 웹 서비스에서 유지되거나 사용되어야 하는 경우 *데이터 계약 serialization*을 지원하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8a875-127">CONSIDER supporting *data contract serialization* if instances of your type might need to be persisted or used in Web Services.</span></span>  
  
-   <span data-ttu-id="8a875-128">형식이 직렬화될 때 생성되는 XML 형식을 더 구체적으로 제어해야 하는 경우 데이터 계약 serialization 대신 또는 데이터 계약 serialization과 함께 *XML serialization*을 지원하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8a875-128">CONSIDER supporting the *XML serialization* instead of or in addition to data contract serialization if you need more control over the XML format that is produced when the type is serialized.</span></span>  
  
     <span data-ttu-id="8a875-129">이러한 지원은 XML 특성을 생성하는 등의 목적으로 데이터 계약 serialization에서 지원하지 않는 XML 구문을 사용해야 하는 일부 상호 운용성 시나리오에 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a875-129">This may be necessary in some interoperability scenarios where you need to use an XML construct that is not supported by data contract serialization, for example, to produce XML attributes.</span></span>  
  
-   <span data-ttu-id="8a875-130">형식의 인스턴스에서 .NET Remoting 경계 간에 이동해야 하는 경우 *런타임 serialization*을 지원하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8a875-130">CONSIDER supporting *runtime serialization* if instances of your type need to travel across .NET Remoting boundaries.</span></span>  
  
-   <span data-ttu-id="8a875-131">일반적인 지속성 이유만으로는 런타임 serialization 또는 XML serialization을 지원하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="8a875-131">AVOID supporting runtime serialization or XML serialization just for general persistence reasons.</span></span> <span data-ttu-id="8a875-132">대신 데이터 계약 serialization을 사용하십시오.</span><span class="sxs-lookup"><span data-stu-id="8a875-132">Prefer data contract serialization instead</span></span>  
  
#### <a name="supporting-data-contract-serialization"></a><span data-ttu-id="8a875-133">데이터 계약 Serialization 지원</span><span class="sxs-lookup"><span data-stu-id="8a875-133">Supporting data contract serialization</span></span>  
 <span data-ttu-id="8a875-134">형식은 형식에 <xref:System.Runtime.Serialization.DataContractAttribute>를 적용하고 형식의 멤버(필드 및 속성)에 <xref:System.Runtime.Serialization.DataMemberAttribute>를 적용하여 데이터 계약 serialization을 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a875-134">Types can support data contract serialization by applying the <xref:System.Runtime.Serialization.DataContractAttribute> to the type and the <xref:System.Runtime.Serialization.DataMemberAttribute> to the members (fields and properties) of the type.</span></span>  
  
 [!code-csharp[SerializationGuidelines#1](../../../samples/snippets/csharp/VS_Snippets_CFX/serializationguidelines/cs/source.cs#1)]
 [!code-vb[SerializationGuidelines#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/serializationguidelines/vb/source.vb#1)]  
  
1.  <span data-ttu-id="8a875-135">부분 신뢰에서 사용할 수 있는 형식의 경우 형식의 데이터 멤버를 public으로 표시하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8a875-135">CONSIDER marking data members of your type public if the type can be used in partial trust.</span></span> <span data-ttu-id="8a875-136">완전 신뢰에서는 데이터 계약 serializer가 public이 아닌 형식 및 멤버를 serialize 및 deserialize할 수 있지만 부분 신뢰에서는 public 형식만 serialize 및 deserialize할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a875-136">In full trust, data contract serializers can serialize and deserialize nonpublic types and members, but only public members can be serialized and deserialized in partial trust.</span></span>  
  
2.  <span data-ttu-id="8a875-137">Data-MemberAttribute가 있는 모든 속성에 대해 getter 및 setter를 구현하십시오.</span><span class="sxs-lookup"><span data-stu-id="8a875-137">DO implement a getter and setter on all properties that have Data-MemberAttribute.</span></span> <span data-ttu-id="8a875-138">serialize 가능한 형식으로 간주되게 하려면 데이터 계약 serializer에 getter와 setter가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="8a875-138">Data contract serializers require both the getter and the setter for the type to be considered serializable.</span></span> <span data-ttu-id="8a875-139">부분 신뢰에서 사용하지 않을 형식의 경우에는 두 속성 접근자 중 하나 또는 둘 다 public이 아닐 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a875-139">If the type won’t be used in partial trust, one or both of the property accessors can be nonpublic.</span></span>  
  
     [!code-csharp[SerializationGuidelines#2](../../../samples/snippets/csharp/VS_Snippets_CFX/serializationguidelines/cs/source.cs#2)]
     [!code-vb[SerializationGuidelines#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/serializationguidelines/vb/source.vb#2)]  
  
3.  <span data-ttu-id="8a875-140">deserialize된 인스턴스의 초기화에 serialization 콜백을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8a875-140">CONSIDER using the serialization callbacks for initialization of deserialized instances.</span></span>  
  
     <span data-ttu-id="8a875-141">개체가 deserialize될 때는 생성자가 호출되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8a875-141">Constructors are not called when objects are deserialized.</span></span> <span data-ttu-id="8a875-142">따라서 정상적인 생성이 수행되는 동안 실행되는 논리는 모두 *serialization 콜백* 중 하나로 구현되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a875-142">Therefore, any logic that executes during normal construction needs to be implemented as one of the *serialization callbacks*.</span></span>  
  
     [!code-csharp[SerializationGuidelines#3](../../../samples/snippets/csharp/VS_Snippets_CFX/serializationguidelines/cs/source.cs#3)]
     [!code-vb[SerializationGuidelines#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/serializationguidelines/vb/source.vb#3)]  
  
     <span data-ttu-id="8a875-143"><xref:System.Runtime.Serialization.OnDeserializedAttribute> 특성은 가장 일반적으로 사용되는 콜백 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="8a875-143">The <xref:System.Runtime.Serialization.OnDeserializedAttribute> attribute is the most commonly used callback attribute.</span></span> <span data-ttu-id="8a875-144">패밀리의 다른 특성은 다음과 같습니다. <xref:System.Runtime.Serialization.OnDeserializingAttribute>,</span><span class="sxs-lookup"><span data-stu-id="8a875-144">The other attributes in the family are <xref:System.Runtime.Serialization.OnDeserializingAttribute>,</span></span>    
    <span data-ttu-id="8a875-145"><xref:System.Runtime.Serialization.OnSerializingAttribute> 및 <xref:System.Runtime.Serialization.OnSerializedAttribute></span><span class="sxs-lookup"><span data-stu-id="8a875-145"><xref:System.Runtime.Serialization.OnSerializingAttribute>, and <xref:System.Runtime.Serialization.OnSerializedAttribute>.</span></span> <span data-ttu-id="8a875-146">이 특성은 deserialization하기 전, serialization하기 전 및 마지막으로 serialization한 후에 각각 실행되는 콜백을 표시하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a875-146">They can be used to mark callbacks that get executed before deserialization, before serialization, and finally, after serialization, respectively.</span></span>  
  
4.  <span data-ttu-id="8a875-147"><xref:System.Runtime.Serialization.KnownTypeAttribute>를 사용하여 복합 개체 그래프를 deserialize할 때 사용되어야 하는 추상 형식을 나타내는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8a875-147">CONSIDER using the <xref:System.Runtime.Serialization.KnownTypeAttribute> to indicate concrete types that should be used when deserializing a complex object graph.</span></span>  
  
     <span data-ttu-id="8a875-148">예를 들어 deserialize된 데이터 멤버의 형식이 추상 클래스로 표현되는 경우 직렬 변환기가 인스턴스화할 추상 형식을 결정하고 멤버에 할당하려면 *알려진 형식* 정보가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="8a875-148">For example, if a type of a deserialized data member is represented by an abstract class, the serializer will need the *known type* information to decide what concrete type to instantiate and assign to the member.</span></span> <span data-ttu-id="8a875-149">특성을 사용하여 알려진 형식을 지정하지 않으면 알려진 형식을 serializer 생성자에 전달하여 명시적으로 serializer에 전달하거나 구성 파일에 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a875-149">If the known type is not specified using the attribute, it will need to be passed to the serializer explicitly (you can do it by passing known types to the serializer constructor) or it will need to be specified in the configuration file.</span></span>  
  
     [!code-csharp[SerializationGuidelines#4](../../../samples/snippets/csharp/VS_Snippets_CFX/serializationguidelines/cs/source.cs#4)]
     [!code-vb[SerializationGuidelines#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/serializationguidelines/vb/source.vb#4)]  
  
     <span data-ttu-id="8a875-150">**Person** 클래스를 컴파일할 때 알려진 형식 목록을 정적으로 알 수 없는 경우 **KnownTypeAttribute**가 런타임에 알려진 형식 목록을 반환하는 메서드를 가리킬 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a875-150">In cases where the list of known types is not known statically (when the **Person** class is compiled), the **KnownTypeAttribute** can also point to a method that returns a list of known types at runtime.</span></span>  
  
5.  <span data-ttu-id="8a875-151">serialize 가능한 형식을 만들거나 변경할 때 이전 버전과의 호환성과 이후 버전과의 호환성을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8a875-151">DO consider backward and forward compatibility when creating or changing serializable types.</span></span>  
  
     <span data-ttu-id="8a875-152">이후 버전의 형식에 대한 serialize된 스트림을 현재 버전의 형식으로 deserialize할 수 있고, 그 반대로 deserialize할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a875-152">Keep in mind that serialized streams of future versions of your type can be deserialized into the current version of the type, and vice versa.</span></span> <span data-ttu-id="8a875-153">데이터 계약 특성에 명시적 매개 변수를 사용하여 계약을 유지할 목적으로 특별히 주의하는 경우를 제외하면 private 멤버이거나 내부 멤버인 경우를 포함하여 데이터 멤버는 이후 버전의 형식에서 해당 멤버의 이름, 형식 또는 순서를 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8a875-153">Make sure you understand that data members, even private and internal, cannot change their names, types, or even their order in future versions of the type unless special care is taken to preserve the contract using explicit parameters to the data contract attributes.Test compatibility of serialization when making changes to serializable types.</span></span> <span data-ttu-id="8a875-154">이 경우에는 새 버전을 이전 버전으로 deserialize하거나 이전 버전을 새 버전으로 deserialize하십시오.</span><span class="sxs-lookup"><span data-stu-id="8a875-154">Try deserializing the new version into an old version, and vice versa.</span></span>  
  
6.  <span data-ttu-id="8a875-155">서로 다른 버전의 형식 간에 라운드트립이 가능하도록 <xref:System.Runtime.Serialization.IExtensibleDataObject> 인터페이스를 구현하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8a875-155">CONSIDER implementing <xref:System.Runtime.Serialization.IExtensibleDataObject> interface to allow round-tripping between different versions of the type.</span></span>  
  
     <span data-ttu-id="8a875-156">이 인터페이스를 사용하면 serializer에서 라운드트립하는 동안 데이터가 손실되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8a875-156">The interface allows the serializer to ensure that no data is lost during round-tripping.</span></span> <span data-ttu-id="8a875-157"><xref:System.Runtime.Serialization.IExtensibleDataObject.ExtensionData%2A> 속성은 현재 버전에서는 알 수 없는 이후 버전 형식의 모든 데이터를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="8a875-157">The <xref:System.Runtime.Serialization.IExtensibleDataObject.ExtensionData%2A> property stores any data from the future version of the type that is unknown to the current version.</span></span> <span data-ttu-id="8a875-158">이후에 현재 버전을 이후 버전으로 직렬화하거나 deserialize하면 **ExtensionData** 속성 값을 통해 직렬화된 스트림에서 추가 데이터를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a875-158">When the current version is subsequently serialized and deserialized into a future version, the additional data will be available in the serialized stream through the **ExtensionData** property value.</span></span>  
  
     [!code-csharp[SerializationGuidelines#5](../../../samples/snippets/csharp/VS_Snippets_CFX/serializationguidelines/cs/source.cs#5)]
     [!code-vb[SerializationGuidelines#5](../../../samples/snippets/visualbasic/VS_Snippets_CFX/serializationguidelines/vb/source.vb#5)]  
  
     <span data-ttu-id="8a875-159">자세한 내용은 [호환 가능한 데이터 계약](../../../docs/framework/wcf/feature-details/forward-compatible-data-contracts.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8a875-159">For more information, see [Forward-Compatible Data Contracts](../../../docs/framework/wcf/feature-details/forward-compatible-data-contracts.md).</span></span>  
  
#### <a name="supporting-xml-serialization"></a><span data-ttu-id="8a875-160">XML Serialization 지원</span><span class="sxs-lookup"><span data-stu-id="8a875-160">Supporting XML serialization</span></span>  
 <span data-ttu-id="8a875-161">데이터 계약 serialization은 .NET Framework의 기본 serialization 기술이지만 데이터 계약 serialization에서 지원하지 않는 serialization 시나리오가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a875-161">Data contract serialization is the main (default) serialization technology in the .NET Framework, but there are serialization scenarios that data contract serialization does not support.</span></span> <span data-ttu-id="8a875-162">예를 들어 serializer에서 생성하거나 사용하는 XML의 모양을 완전히 제어할 수 있는 권한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8a875-162">For example, it does not give you full control over the shape of XML produced or consumed by the serializer.</span></span> <span data-ttu-id="8a875-163">이러한 충분한 제어 권한이 필요한 경우 *XML serialization*을 사용해야 하며 이 serialization 기술을 지원하기 위한 형식을 디자인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a875-163">If such fine control is required, *XML serialization* has to be used, and you need to design your types to support this serialization technology.</span></span>  
  
1.  <span data-ttu-id="8a875-164">생성된 XML의 모양을 제어해야 하는 확실한 이유가 있지 않으면 XML Serialization에 맞게 형식을 디자인하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="8a875-164">AVOID designing your types specifically for XML Serialization, unless you have a very strong reason to control the shape of the XML produced.</span></span> <span data-ttu-id="8a875-165">이 serialization 기술은 앞의 섹션에서 설명한 데이터 계약 Serialization으로 대체되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8a875-165">This serialization technology has been superseded by the Data Contract Serialization discussed in the previous section.</span></span>  
  
     <span data-ttu-id="8a875-166">즉, 형식이 XML Serialization과 함께 사용될 것이라는 사실을 알고 있지 않으면 <xref:System.Runtime.Serialization> 네임스페이스의 특성을 새 형식에 적용하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="8a875-166">In other words, don’t apply attributes from the <xref:System.Runtime.Serialization> namespace to new types, unless you know that the type will be used with XML Serialization.</span></span> <span data-ttu-id="8a875-167">다음 예제에서는 생성된 XML의 모양을 제어하는 데 **System.Xml.Serialization**을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8a875-167">The following example shows how **System.Xml.Serialization** can be used to control the shape of the XML -produced.</span></span>  
  
     [!code-csharp[SerializationGuidelines#6](../../../samples/snippets/csharp/VS_Snippets_CFX/serializationguidelines/cs/source.cs#6)]
     [!code-vb[SerializationGuidelines#6](../../../samples/snippets/visualbasic/VS_Snippets_CFX/serializationguidelines/vb/source.vb#6)]  
  
2.  <span data-ttu-id="8a875-168">XML Serialization 특성을 적용하는 방법보다 serialize된 XML의 모양을 더 구체적으로 제어하려면 <xref:System.Xml.Serialization.IXmlSerializable> 인터페이스를 구현하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8a875-168">CONSIDER implementing the <xref:System.Xml.Serialization.IXmlSerializable> interface if you want even more control over the shape of the serialized XML than what’s offered by applying the XML Serialization attributes.</span></span> <span data-ttu-id="8a875-169">인터페이스의 두 가지 방법 <xref:System.Xml.Serialization.IXmlSerializable.ReadXml%2A> 및 <xref:System.Xml.Serialization.IXmlSerializable.WriteXml%2A>, serialize 된 XML 스트림에 완벽 하 게 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a875-169">Two methods of the interface, <xref:System.Xml.Serialization.IXmlSerializable.ReadXml%2A> and <xref:System.Xml.Serialization.IXmlSerializable.WriteXml%2A>, allow you to fully control the serialized XML stream.</span></span> <span data-ttu-id="8a875-170"><xref:System.Xml.Serialization.XmlSchemaProviderAttribute> 특성을 적용하여 형식에 대해 생성되는 XML 스키마를 제어할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a875-170">You can also control the XML schema that gets generated for the type by applying the <xref:System.Xml.Serialization.XmlSchemaProviderAttribute> attribute.</span></span>  
  
#### <a name="supporting-runtime-serialization"></a><span data-ttu-id="8a875-171">런타임 Serialization 지원</span><span class="sxs-lookup"><span data-stu-id="8a875-171">Supporting runtime serialization</span></span>  
 <span data-ttu-id="8a875-172">*Runtime serialization*은 .NET Remoting에 사용되는 기술입니다.</span><span class="sxs-lookup"><span data-stu-id="8a875-172">*Runtime serialization* is a technology used by .NET Remoting.</span></span> <span data-ttu-id="8a875-173">.NET Remoting을 사용하여 형식이 전송될 것으로 판단되면 해당 형식이 런타임 serialization을 지원하는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a875-173">If you think your types will be transported using .NET Remoting, you need to make sure they support runtime serialization.</span></span>  
  
 <span data-ttu-id="8a875-174"><xref:System.SerializableAttribute> 특성을 적용하여 *런타임 serialization*에 대한 기본 지원을 제공할 수 있으며 고급 시나리오에는 단순한 *런타임 직렬화 가능 패턴*의 구현이 포함됩니다. <xref:System.Runtime.Serialization.ISerializable>을 구현하고 serialization 생성자를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a875-174">The basic support for *runtime serialization* can be provided by applying the <xref:System.SerializableAttribute> attribute, and more advanced scenarios involve implementing a simple *runtime serializable pattern* (implement -<xref:System.Runtime.Serialization.ISerializable> and provide a serialization constructor).</span></span>  
  
1.  <span data-ttu-id="8a875-175">.NET Remoting과 함께 형식을 사용하지 않는 경우 런타임 serialization을 지원하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8a875-175">CONSIDER supporting runtime serialization if your types will be used with .NET Remoting.</span></span> <span data-ttu-id="8a875-176">예를 들어 <xref:System.AddIn> 네임스페이스는 .NET Remoting을 사용하므로 **System.AddIn** 추가 기능 간에 교환된 모든 형식이 런타임 serialization을 지원해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a875-176">For example, the <xref:System.AddIn> namespace uses .NET Remoting, and so all types exchanged between **System.AddIn** add-ins need to support runtime serialization.</span></span>  
  
     [!code-csharp[SerializationGuidelines#7](../../../samples/snippets/csharp/VS_Snippets_CFX/serializationguidelines/cs/source.cs#7)]
     [!code-vb[SerializationGuidelines#7](../../../samples/snippets/visualbasic/VS_Snippets_CFX/serializationguidelines/vb/source.vb#7)]  
  
2.  <span data-ttu-id="8a875-177">serialization 프로세스를 완전하게 제어하려면 *런타임 직렬화 가능 패턴*을 구현하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8a875-177">CONSIDER implementing the *runtime serializable pattern* if you want complete control over the serialization process.</span></span> <span data-ttu-id="8a875-178">데이터가 serialize 또는 deserialize될 때 데이터를 변환하려는 경우를 예로 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a875-178">For example, if you want to transform data as it gets serialized or deserialized.</span></span>  
  
     <span data-ttu-id="8a875-179">이 패턴은 아주 단순합니다.</span><span class="sxs-lookup"><span data-stu-id="8a875-179">The pattern is very simple.</span></span> <span data-ttu-id="8a875-180"><xref:System.Runtime.Serialization.ISerializable> 인터페이스를 구현하고, 개체가 deserialize될 때 사용되는 특별한 생성자를 제공하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a875-180">All you need to do is implement the <xref:System.Runtime.Serialization.ISerializable> interface and provide a special constructor that is used when the object is deserialized.</span></span>  
  
     [!code-csharp[SerializationGuidelines#8](../../../samples/snippets/csharp/VS_Snippets_CFX/serializationguidelines/cs/source.cs#8)]
     [!code-vb[SerializationGuidelines#8](../../../samples/snippets/visualbasic/VS_Snippets_CFX/serializationguidelines/vb/source.vb#8)]  
  
3.  <span data-ttu-id="8a875-181">serialization 생성자를 보호되도록 설정하고 여기에 나와 있는 샘플에 표시된 대로 입력하고 이름을 지정한 두 개의 매개 변수를 제공하십시오.</span><span class="sxs-lookup"><span data-stu-id="8a875-181">DO make the serialization constructor protected and provide two parameters typed and named exactly as shown in the sample here.</span></span>  
  
     [!code-csharp[SerializationGuidelines#9](../../../samples/snippets/csharp/VS_Snippets_CFX/serializationguidelines/cs/source.cs#9)]
     [!code-vb[SerializationGuidelines#9](../../../samples/snippets/visualbasic/VS_Snippets_CFX/serializationguidelines/vb/source.vb#9)]  
  
4.  <span data-ttu-id="8a875-182">ISerializable 멤버를 명시적으로 구현하십시오.</span><span class="sxs-lookup"><span data-stu-id="8a875-182">DO implement the ISerializable members explicitly.</span></span>  
  
     [!code-csharp[SerializationGuidelines#10](../../../samples/snippets/csharp/VS_Snippets_CFX/serializationguidelines/cs/source.cs#10)]
     [!code-vb[SerializationGuidelines#10](../../../samples/snippets/visualbasic/VS_Snippets_CFX/serializationguidelines/vb/source.vb#10)]  
  
5.  <span data-ttu-id="8a875-183">**ISerializable.GetObjectData** 구현에 링크 요구를 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="8a875-183">DO apply a link demand to **ISerializable.GetObjectData** implementation.</span></span> <span data-ttu-id="8a875-184">그러면 완전히 신뢰되는 코어 및 런타임 serializer만 멤버에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a875-184">This ensures that only fully trusted core and the runtime serializer have access to the member.</span></span>  
  
     [!code-csharp[SerializationGuidelines#11](../../../samples/snippets/csharp/VS_Snippets_CFX/serializationguidelines/cs/source.cs#11)]
     [!code-vb[SerializationGuidelines#11](../../../samples/snippets/visualbasic/VS_Snippets_CFX/serializationguidelines/vb/source.vb#11)]  
  
## <a name="see-also"></a><span data-ttu-id="8a875-185">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8a875-185">See also</span></span>  
 [<span data-ttu-id="8a875-186">데이터 계약 사용</span><span class="sxs-lookup"><span data-stu-id="8a875-186">Using Data Contracts</span></span>](../../../docs/framework/wcf/feature-details/using-data-contracts.md)  
 [<span data-ttu-id="8a875-187">데이터 계약 Serializer</span><span class="sxs-lookup"><span data-stu-id="8a875-187">Data Contract Serializer</span></span>](../../../docs/framework/wcf/feature-details/data-contract-serializer.md)  
 [<span data-ttu-id="8a875-188">데이터 계약 Serializer에서 지 원하는 형식</span><span class="sxs-lookup"><span data-stu-id="8a875-188">Types Supported by the Data Contract Serializer</span></span>](../../../docs/framework/wcf/feature-details/types-supported-by-the-data-contract-serializer.md)  
 [<span data-ttu-id="8a875-189">이진 serialization</span><span class="sxs-lookup"><span data-stu-id="8a875-189">Binary Serialization</span></span>](binary-serialization.md)  
 [<span data-ttu-id="8a875-190">원격 개체</span><span class="sxs-lookup"><span data-stu-id="8a875-190">Remote Objects</span></span>](http://msdn.microsoft.com/library/515686e6-0a8d-42f7-8188-73abede57c58)  
 [<span data-ttu-id="8a875-191">XML 및 SOAP serialization</span><span class="sxs-lookup"><span data-stu-id="8a875-191">XML and SOAP Serialization</span></span>](xml-and-soap-serialization.md)  
 [<span data-ttu-id="8a875-192">보안 및 Serialization</span><span class="sxs-lookup"><span data-stu-id="8a875-192">Security and Serialization</span></span>](../../../docs/framework/misc/security-and-serialization.md)
