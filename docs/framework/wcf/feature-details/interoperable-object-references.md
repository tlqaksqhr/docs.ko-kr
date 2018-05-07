---
title: 상호 운영 가능한 개체 참조
ms.date: 03/30/2017
ms.assetid: cb8da4c8-08ca-4220-a16b-e04c8f527f1b
ms.openlocfilehash: eeedd39ec14a6758395aee1f4c3b8ab26a0c2ffd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="interoperable-object-references"></a>상호 운영 가능한 개체 참조
기본적으로 <xref:System.Runtime.Serialization.DataContractSerializer>는 개체를 값으로 serialize합니다. <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> 속성을 사용하여 데이터 계약 Serializer에 해당 형식의 개체를 serialize할 때 개체 참조를 유지하도록 지시할 수 있습니다.  
  
## <a name="generated-xml"></a>생성된 XML  
 예를 들어 다음과 같은 개체를 살펴보세요.  
  
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
  
 <xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A>를 `false`(기본값)로 설정하면 다음 XML이 생성됩니다.  
  
```xml  
<X>  
   <A>contents of someInstance</A>  
   <B>contents of someInstance</B>  
</X>  
```  
  
 <xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A>를 `true`로 설정하면 다음 XML이 생성됩니다.  
  
```xml  
<X>  
   <A id="1">contents of someInstance</A>  
   <B ref="1" />  
</X>  
```  
  
 그러나 <xref:System.Runtime.Serialization.XsdDataContractExporter> 속성이 `id`로 설정되어 있어도 `ref`는 자체의 스키마에서 `preserveObjectReferences` 및 `true` 특성을 설명하지 못합니다.  
  
## <a name="using-isreference"></a>IsReference 사용  
 설명하는 스키마에 따라 올바른 개체 참조 정보를 생성하려면 형식에 <xref:System.Runtime.Serialization.DataContractAttribute> 특성을 적용하고 <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> 플래그를 `true`로 설정합니다. 위의 예제 클래스 `IsReference`에서 다음과 같이 `X`를 사용합니다.  
  
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
  
 생성되는 XML은 다음과 같습니다.  
  
 `<X>`  
  
 `<A id="1">`  
  
 `<Value>contents of A</Value>`  
  
 `</A>`  
  
 `<B ref="1">`  
  
 `</B>`  
  
 `</X>`  
  
 `IsReference`를 사용하면 메시지 라운드트립이 준수됩니다. 사용하지 않으면 스키마에서 형식이 생성될 때 해당 형식에 대해 XML로 다시 보내지는 스키마가 원래 가정된 스키마와 호환되지 않아도 됩니다. 즉, `id` 및 `ref` 특성이 serialize되었더라도 원래 스키마 때문에 이러한 특성 또는 모든 특성이 XML에서 발생하지 않았을 수 있습니다. 데이터 멤버에 `IsReference`가 적용되면 해당 멤버는 왕복될 때 계속해서 "참조 가능한" 것으로 인식됩니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Runtime.Serialization.DataContractAttribute>  
 <xref:System.Runtime.Serialization.CollectionDataContractAttribute>  
 <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A>  
 <xref:System.Runtime.Serialization.CollectionDataContractAttribute.IsReference%2A>
