---
title: 상호 운영 가능한 개체 참조
ms.date: 03/30/2017
ms.assetid: cb8da4c8-08ca-4220-a16b-e04c8f527f1b
ms.openlocfilehash: eeedd39ec14a6758395aee1f4c3b8ab26a0c2ffd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33493575"
---
# <a name="interoperable-object-references"></a><span data-ttu-id="c9072-102">상호 운영 가능한 개체 참조</span><span class="sxs-lookup"><span data-stu-id="c9072-102">Interoperable Object References</span></span>
<span data-ttu-id="c9072-103">기본적으로 <xref:System.Runtime.Serialization.DataContractSerializer>는 개체를 값으로 serialize합니다.</span><span class="sxs-lookup"><span data-stu-id="c9072-103">By default the <xref:System.Runtime.Serialization.DataContractSerializer> serializes objects by value.</span></span> <span data-ttu-id="c9072-104"><xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> 속성을 사용하여 데이터 계약 Serializer에 해당 형식의 개체를 serialize할 때 개체 참조를 유지하도록 지시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9072-104">You can use the <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> property to instruct the Data Contract Serializer to preserve object references when serializing objects of the type.</span></span>  
  
## <a name="generated-xml"></a><span data-ttu-id="c9072-105">생성된 XML</span><span class="sxs-lookup"><span data-stu-id="c9072-105">Generated XML</span></span>  
 <span data-ttu-id="c9072-106">예를 들어 다음과 같은 개체를 살펴보세요.</span><span class="sxs-lookup"><span data-stu-id="c9072-106">As an example, consider the following object:</span></span>  
  
```  
[DataContract]  
public class X  
{  
    SomeClass someInstance = new SomeClass();  
    [DataMember]  
    public SomeClass A = someInstance;  
    [DataMember]  
    public SomeClass B = someInstance;  
}  
  
public class SomeClass   
{  
}  
```  
  
 <span data-ttu-id="c9072-107"><xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A>를 `false`(기본값)로 설정하면 다음 XML이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9072-107">With <xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A> set to `false` (the default), the following XML is generated:</span></span>  
  
```xml  
<X>  
   <A>contents of someInstance</A>  
   <B>contents of someInstance</B>  
</X>  
```  
  
 <span data-ttu-id="c9072-108"><xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A>를 `true`로 설정하면 다음 XML이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9072-108">With <xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A> set to `true`, the following XML is generated:</span></span>  
  
```xml  
<X>  
   <A id="1">contents of someInstance</A>  
   <B ref="1" />  
</X>  
```  
  
 <span data-ttu-id="c9072-109">그러나 <xref:System.Runtime.Serialization.XsdDataContractExporter> 속성이 `id`로 설정되어 있어도 `ref`는 자체의 스키마에서 `preserveObjectReferences` 및 `true` 특성을 설명하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="c9072-109">However, <xref:System.Runtime.Serialization.XsdDataContractExporter> does not describe the `id` and `ref` attributes in its schema, even when the `preserveObjectReferences` property is set to `true`.</span></span>  
  
## <a name="using-isreference"></a><span data-ttu-id="c9072-110">IsReference 사용</span><span class="sxs-lookup"><span data-stu-id="c9072-110">Using IsReference</span></span>  
 <span data-ttu-id="c9072-111">설명하는 스키마에 따라 올바른 개체 참조 정보를 생성하려면 형식에 <xref:System.Runtime.Serialization.DataContractAttribute> 특성을 적용하고 <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> 플래그를 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c9072-111">To generate object reference information that is valid according to the schema that describes it, apply the <xref:System.Runtime.Serialization.DataContractAttribute> attribute to a type, and set the <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> flag to `true`.</span></span> <span data-ttu-id="c9072-112">위의 예제 클래스 `IsReference`에서 다음과 같이 `X`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c9072-112">Using `IsReference` in the previous example class `X`:</span></span>  
  
 `[DataContract(IsReference=true)] public class X`  
  
 `{`  
  
 `SomeClass someInstance = new SomeClass();`  
  
 `[DataMember]`  
  
 `public SomeClass A = someInstance;`  
  
 `[DataMember]`  
  
 `public SomeClass B = someInstance;`  
  
 `}`  
  
 `public class SomeClass`  
  
 `{`  
  
 `}`  
  
 <span data-ttu-id="c9072-113">생성되는 XML은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c9072-113">The generated XML is as follows:</span></span>  
  
 `<X>`  
  
 `<A id="1">`  
  
 `<Value>contents of A</Value>`  
  
 `</A>`  
  
 `<B ref="1">`  
  
 `</B>`  
  
 `</X>`  
  
 <span data-ttu-id="c9072-114">`IsReference`를 사용하면 메시지 라운드트립이 준수됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9072-114">Using `IsReference` ensures compliance on message round-tripping.</span></span> <span data-ttu-id="c9072-115">사용하지 않으면 스키마에서 형식이 생성될 때 해당 형식에 대해 XML로 다시 보내지는 스키마가 원래 가정된 스키마와 호환되지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9072-115">Without it, when a type is generated from schema, what is sent back as XML for that type is not necessarily compatible with the schema originally assumed.</span></span> <span data-ttu-id="c9072-116">즉, `id` 및 `ref` 특성이 serialize되었더라도 원래 스키마 때문에 이러한 특성 또는 모든 특성이 XML에서 발생하지 않았을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9072-116">In other words, although the `id` and `ref` attributes were serialized, the original schema could have barred these attributes (or all attributes) from occurring in the XML.</span></span> <span data-ttu-id="c9072-117">데이터 멤버에 `IsReference`가 적용되면 해당 멤버는 왕복될 때 계속해서 "참조 가능한" 것으로 인식됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9072-117">With `IsReference` applied to a data member, the member continues to be recognized as "referenceable" when roundtripped.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9072-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c9072-118">See Also</span></span>  
 <xref:System.Runtime.Serialization.DataContractAttribute>  
 <xref:System.Runtime.Serialization.CollectionDataContractAttribute>  
 <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A>  
 <xref:System.Runtime.Serialization.CollectionDataContractAttribute.IsReference%2A>
