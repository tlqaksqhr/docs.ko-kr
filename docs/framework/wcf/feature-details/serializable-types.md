---
title: "serialize할 수 있는 형식"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f1c8539a-6a79-4413-b294-896f0957b2cd
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 6f053edc688080293b6fae927049bf6776551b7c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="serializable-types"></a><span data-ttu-id="f7750-102">serialize할 수 있는 형식</span><span class="sxs-lookup"><span data-stu-id="f7750-102">Serializable Types</span></span>
<span data-ttu-id="f7750-103">기본적으로 <xref:System.Runtime.Serialization.DataContractSerializer>는 모든 공개 형식을 serialize합니다.</span><span class="sxs-lookup"><span data-stu-id="f7750-103">By default, the <xref:System.Runtime.Serialization.DataContractSerializer> serializes all publicly visible types.</span></span> <span data-ttu-id="f7750-104">이 경우 형식의 모든 공개 읽기/쓰기 속성과 필드가 serialize됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7750-104">All public read/write properties and fields of the type are serialized.</span></span>  
  
 <span data-ttu-id="f7750-105"><xref:System.Runtime.Serialization.DataContractAttribute> 및 <xref:System.Runtime.Serialization.DataMemberAttribute> 특성을 형식 및 멤버에 적용하여 기본 동작을 변경할 수 있습니다. 이 기능은 제어할 수 없거나 특성을 추가하도록 수정할 수 없는 형식이 있는 경우 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7750-105">You can change the default behavior by applying the <xref:System.Runtime.Serialization.DataContractAttribute> and <xref:System.Runtime.Serialization.DataMemberAttribute> attributes to the types and members This feature can be useful in situations in which you have types that are not under your control and cannot be modified to add attributes.</span></span> <span data-ttu-id="f7750-106"><xref:System.Runtime.Serialization.DataContractSerializer>는 이러한 "표시되지 않은" 형식을 인식합니다.</span><span class="sxs-lookup"><span data-stu-id="f7750-106">The <xref:System.Runtime.Serialization.DataContractSerializer> recognizes such "unmarked" types.</span></span>  
  
## <a name="serialization-defaults"></a><span data-ttu-id="f7750-107">Serialization 기본값</span><span class="sxs-lookup"><span data-stu-id="f7750-107">Serialization Defaults</span></span>  
 <span data-ttu-id="f7750-108"><xref:System.Runtime.Serialization.DataContractAttribute> 및 <xref:System.Runtime.Serialization.DataMemberAttribute> 특성을 적용하여 형식 및 멤버의 serialization을 명시적으로 제어하거나 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7750-108">You can apply the <xref:System.Runtime.Serialization.DataContractAttribute> and <xref:System.Runtime.Serialization.DataMemberAttribute> attributes to explicitly control or customize the serialization of types and members.</span></span> <span data-ttu-id="f7750-109">또한 이러한 특성을 전용 필드에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7750-109">In addition, you can apply these attributes to private fields.</span></span> <span data-ttu-id="f7750-110">그러나 이러한 특성으로 표시되지 않은 형식도 serialize 및 deserialize할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7750-110">However, even types that are not marked with these attributes are serialized and deserialized.</span></span> <span data-ttu-id="f7750-111">다음과 같은 규칙 및 예외가 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7750-111">The following rules and exceptions apply:</span></span>  
  
-   <span data-ttu-id="f7750-112"><xref:System.Runtime.Serialization.DataContractSerializer>는 새로 만든 형식의 기본 속성을 사용하여 특성 없이 형식에서 데이터 계약을 유추합니다.</span><span class="sxs-lookup"><span data-stu-id="f7750-112">The <xref:System.Runtime.Serialization.DataContractSerializer> infers a data contract from types without attributes using the default properties of the newly created types.</span></span>  
  
-   <span data-ttu-id="f7750-113">`get` 특성을 멤버에 적용하지 않으면 모든 공용 필드 및 공용 `set` 및 <xref:System.Runtime.Serialization.IgnoreDataMemberAttribute>메서드가 있는 속성이 serialize됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7750-113">All public fields, and properties with public `get` and `set` methods are serialized, unless you apply the <xref:System.Runtime.Serialization.IgnoreDataMemberAttribute> attribute to that member.</span></span>  
  
-   <span data-ttu-id="f7750-114">serialization 의미 체계는 <xref:System.Xml.Serialization.XmlSerializer>의 의미 체계와 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="f7750-114">The serialization semantics are similar to those of the <xref:System.Xml.Serialization.XmlSerializer>.</span></span>  
  
-   <span data-ttu-id="f7750-115">표시되지 않은 형식에서는 매개 변수를 사용하지 않는 생성자가 있는 공용 형식만 serialize됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7750-115">In unmarked types, only public types with constructors that do not have parameters are serialized.</span></span> <span data-ttu-id="f7750-116">이 규칙의 예외는 <xref:System.Runtime.Serialization.ExtensionDataObject> 인터페이스와 함께 사용되는 <xref:System.Runtime.Serialization.IExtensibleDataObject>입니다.</span><span class="sxs-lookup"><span data-stu-id="f7750-116">The exception to this rule is <xref:System.Runtime.Serialization.ExtensionDataObject> used with the <xref:System.Runtime.Serialization.IExtensibleDataObject> interface.</span></span>  
  
-   <span data-ttu-id="f7750-117">읽기 전용 필드, `get` 또는 `set` 메서드가 없는 속성, 내부 또는 전용 `set` 또는 `get` 메서드가 있는 속성은 serialize되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f7750-117">Read-only fields, properties without a `get` or `set` method, and properties with internal or private `set` or `get` methods are not serialized.</span></span> <span data-ttu-id="f7750-118">이러한 속성은 무시되고 예외가 throw되지 않습니다. get-only 컬렉션의 경우는 예외입니다.</span><span class="sxs-lookup"><span data-stu-id="f7750-118">Such properties are ignored and no exception is thrown, except in the case of get-only collections.</span></span>  
  
-   <span data-ttu-id="f7750-119"><xref:System.Xml.Serialization.XmlSerializer> 특성(`XmlElement`, `XmlAttribute`, `XmlIgnore`, `XmlInclude` 등)이 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7750-119"><xref:System.Xml.Serialization.XmlSerializer> attributes (such as `XmlElement`, `XmlAttribute`, `XmlIgnore`, `XmlInclude`, and so on) are ignored.</span></span>  
  
-   <span data-ttu-id="f7750-120">지정된 형식에 <xref:System.Runtime.Serialization.DataContractAttribute> 특성을 적용하지 않는 경우 serializer는 <xref:System.Runtime.Serialization.DataMemberAttribute> 특성이 적용되는 형식의 모든 멤버를 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="f7750-120">If you do not apply the <xref:System.Runtime.Serialization.DataContractAttribute> attribute to a given type, the serializer ignores any member in that type to which the <xref:System.Runtime.Serialization.DataMemberAttribute> attribute is applied.</span></span>  
  
-   <span data-ttu-id="f7750-121"><xref:System.Runtime.Serialization.DataContractSerializer.KnownTypes%2A> 속성은 <xref:System.Runtime.Serialization.DataContractAttribute> 특성으로 표시되지 않는 형식으로 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7750-121">The <xref:System.Runtime.Serialization.DataContractSerializer.KnownTypes%2A> property is supported in types not marked with the <xref:System.Runtime.Serialization.DataContractAttribute> attribute.</span></span> <span data-ttu-id="f7750-122">여기에는 표시되지 않은 형식에 대한 <xref:System.Runtime.Serialization.KnownTypeAttribute> 특성 지원이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7750-122">This includes support for the <xref:System.Runtime.Serialization.KnownTypeAttribute> attribute on unmarked types.</span></span>  
  
-   <span data-ttu-id="f7750-123">공용 멤버, 속성 또는 필드에 대한 serialization 프로세스를 "취소"하려면 <xref:System.Runtime.Serialization.IgnoreDataMemberAttribute> 특성을 해당 멤버에 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="f7750-123">To "opt out" of the serialization process for public members, properties, or fields, apply the <xref:System.Runtime.Serialization.IgnoreDataMemberAttribute> attribute to that member.</span></span>  
  
## <a name="inheritance"></a><span data-ttu-id="f7750-124">상속</span><span class="sxs-lookup"><span data-stu-id="f7750-124">Inheritance</span></span>  
 <span data-ttu-id="f7750-125">표시되지 않은 형식(<xref:System.Runtime.Serialization.DataContractAttribute> 특성이 없는 형식)은 이러한 특성을 포함하는 형식에서 상속할 수 있지만 반대의 경우, 즉 특성을 포함하는 형식이 표시되지 않은 형식에서 상속할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f7750-125">Unmarked types (types without the <xref:System.Runtime.Serialization.DataContractAttribute> attribute) can inherit from types that do have this attribute; however, the reverse is not permitted: types with the attribute cannot inherit from unmarked types.</span></span> <span data-ttu-id="f7750-126">이 규칙은 주로 이전 버전의 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]로 작성된 코드와의 이전 버전 호환성을 보장하기 위해 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7750-126">This rule is enforced primarily to ensure backward compatibility with code written in earlier versions of [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7750-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f7750-127">See Also</span></span>  
 <xref:System.Runtime.Serialization.IgnoreDataMemberAttribute>  
 <xref:System.Runtime.Serialization.DataContractAttribute>  
 <xref:System.Runtime.Serialization.DataMemberAttribute>  
 <xref:System.Xml.Serialization.XmlSerializer>  
 [<span data-ttu-id="f7750-128">데이터 계약 Serializer에서 지 원하는 형식</span><span class="sxs-lookup"><span data-stu-id="f7750-128">Types Supported by the Data Contract Serializer</span></span>](../../../../docs/framework/wcf/feature-details/types-supported-by-the-data-contract-serializer.md)
