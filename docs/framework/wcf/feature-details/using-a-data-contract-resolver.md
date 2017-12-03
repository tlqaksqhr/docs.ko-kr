---
title: "데이터 계약 확인자 사용"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2e68a16c-36f0-4df4-b763-32021bff2b89
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 46a532b45024321a6885fa3e45d172c054d18c1c
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="using-a-data-contract-resolver"></a><span data-ttu-id="0b013-102">데이터 계약 확인자 사용</span><span class="sxs-lookup"><span data-stu-id="0b013-102">Using a Data Contract Resolver</span></span>
<span data-ttu-id="0b013-103">데이터 계약 확인자를 사용하면 알려진 형식을 동적으로 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b013-103">A data contract resolver allows you to configure known types dynamically.</span></span> <span data-ttu-id="0b013-104">알려진 형식은 데이터 계약에 필요하지 않은 형식을 serialize하거나 deserialize할 때 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="0b013-104">Known types are required when serializing or deserializing a type not expected by a data contract.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="0b013-105"> 는 [Data Contract Known Types](../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)서비스에서 메타데이터를 내보낼 때 CLR 형식을 XSD에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="0b013-105"> known types, see [Data Contract Known Types](../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span></span> <span data-ttu-id="0b013-106">알려진 형식은 일반적으로 정적으로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b013-106">Known types are normally specified statically.</span></span> <span data-ttu-id="0b013-107">즉, 작업을 구현하는 동안 작업이 받을 수 있는 가능한 형식을 모두 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b013-107">This means you would have to know all the possible types an operation may receive while implementing the operation.</span></span> <span data-ttu-id="0b013-108">이에 해당하지 않고 알려진 형식을 동적으로 지정하는 기능이 중요한 시나리오도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b013-108">There are scenarios in which this is not true and being able to specify known types dynamically is important.</span></span>  
  
## <a name="creating-a-data-contract-resolver"></a><span data-ttu-id="0b013-109">데이터 계약 확인자 만들기</span><span class="sxs-lookup"><span data-stu-id="0b013-109">Creating a Data Contract Resolver</span></span>  
 <span data-ttu-id="0b013-110">데이터 계약 확인자를 만드는 작업에는 <xref:System.Runtime.Serialization.DataContractResolver.TryResolveType%2A> 및 <xref:System.Runtime.Serialization.DataContractResolver.ResolveName%2A> 메서드를 구현하는 작업이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b013-110">Creating a data contract resolver involves implementing two methods, <xref:System.Runtime.Serialization.DataContractResolver.TryResolveType%2A> and <xref:System.Runtime.Serialization.DataContractResolver.ResolveName%2A>.</span></span> <span data-ttu-id="0b013-111">이러한 두 메서드는 serialization 및 deserialization 중에 사용되는 콜백을 각각 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="0b013-111">These two methods implement callbacks that are used during serialization and deserialization, respectively.</span></span> <span data-ttu-id="0b013-112"><xref:System.Runtime.Serialization.DataContractResolver.TryResolveType%2A> 메서드는 serialization 중에 호출되며 데이터 계약 형식을 받아서 `xsi:type` 이름 및 네임스페이스에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="0b013-112">The <xref:System.Runtime.Serialization.DataContractResolver.TryResolveType%2A> method is invoked during serialization and takes a data contract type and maps it to an `xsi:type` name and namespace.</span></span> <span data-ttu-id="0b013-113"><xref:System.Runtime.Serialization.DataContractResolver.ResolveName%2A> 메서드는 deserialization 중에 호출되며 `xsi:type` 이름 및 네임스페이스를 받아서 데이터 계약 형식으로 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0b013-113">The <xref:System.Runtime.Serialization.DataContractResolver.ResolveName%2A> method is invoked during deserialization and takes an `xsi:type` name and namespace and resolves it to a data contract type.</span></span> <span data-ttu-id="0b013-114">이러한 두 메서드에는 구현에서 기본 알려진 형식 확인자를 사용하기 위해 사용할 수 있는 `knownTypeResolver` 매개 변수가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b013-114">Both of these methods have a `knownTypeResolver` parameter that can be used to use the default known type resolver in your implementation.</span></span>  
  
 <span data-ttu-id="0b013-115">다음 예제에서는 <xref:System.Runtime.Serialization.DataContractResolver>를 구현하여 `Customer` 데이터 계약 형식에서 파생된 `Person`라는 데이터 계약 형식에 매핑하거나 이 데이터 계약 형식에서 매핑하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0b013-115">The following example shows how to implement a <xref:System.Runtime.Serialization.DataContractResolver> to map to and from a data contract type named `Customer` derived from a data contract type `Person`.</span></span>  
  
```csharp  
public class MyCustomerResolver : DataContractResolver  
{  
    public override bool TryResolveType(Type dataContractType, Type declaredType, DataContractResolver knownTypeResolver, out XmlDictionaryString typeName, out XmlDictionaryString typeNamespace)  
    {  
        if (dataContractType == typeof(Customer))  
        {  
            XmlDictionary dictionary = new XmlDictionary();  
            typeName = dictionary.Add("SomeCustomer");  
            typeNamespace = dictionary.Add("http://tempuri.com");  
            return true;  
        }  
        else  
        {  
            return knownTypeResolver.TryResolveType(dataContractType, declaredType, null, out typeName, out typeNamespace);  
        }  
    }  
  
    public override Type ResolveName(string typeName, string typeNamespace, DataContractResolver knownTypeResolver)  
    {  
        if (typeName == "SomeCustomer" && typeNamespace == "http://tempuri.com")  
        {  
            return typeof(Customer);  
        }  
        else  
        {  
            return knownTypeResolver.ResolveName(typeName, typeNamespace, null);  
        }  
    }  
}  
```  
  
 <span data-ttu-id="0b013-116"><xref:System.Runtime.Serialization.DataContractResolver>를 정의한 후에는 다음 예제와 같이 이를 <xref:System.Runtime.Serialization.DataContractSerializer> 생성자에 전달하여 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b013-116">Once you have defined a <xref:System.Runtime.Serialization.DataContractResolver> you can use it by passing it to the <xref:System.Runtime.Serialization.DataContractSerializer> constructor as shown in the following example.</span></span>  
  
```  
XmlObjectSerializer serializer = new DataContractSerializer(typeof(Customer), null, Int32.MaxValue, false, false, null, new MyCustomerResolver());  
```  
  
 <span data-ttu-id="0b013-117">다음 예제와 같이 <xref:System.Runtime.Serialization.DataContractSerializer> 또는 <xref:System.Runtime.Serialization.DataContractSerializer.ReadObject%2A> 메서드를 호출할 때 <xref:System.Runtime.Serialization.DataContractSerializer.WriteObject%2A>를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b013-117">You can specify a <xref:System.Runtime.Serialization.DataContractSerializer> in a call to the <xref:System.Runtime.Serialization.DataContractSerializer.ReadObject%2A> or <xref:System.Runtime.Serialization.DataContractSerializer.WriteObject%2A> methods, as shown in the following example.</span></span>  
  
```  
MemoryStream ms = new MemoryStream();  
DataContractSerializer serializer = new DataContractSerializer(typeof(Customer));  
XmlDictionaryWriter writer = XmlDictionaryWriter.CreateDictionaryWriter(XmlWriter.Create(ms));  
serializer.WriteObject(writer, new Customer(), new MyCustomerResolver());  
writer.Flush();  
ms.Position = 0;  
Console.WriteLine(((Customer)serializer.ReadObject(XmlDictionaryReader.CreateDictionaryReader(XmlReader.Create(ms)), false, new MyCustomerResolver()));  
```  
  
 <span data-ttu-id="0b013-118">또는 다음 예제와 같이 이를 <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>에 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b013-118">Or you can set it on the <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior> as shown in the following example.</span></span>  
  
```  
ServiceHost host = new ServiceHost(typeof(MyService));  
  
ContractDescription cd = host.Description.Endpoints[0].Contract;  
OperationDescription myOperationDescription = cd.Operations.Find("Echo");  
  
DataContractSerializerOperationBehavior serializerBehavior = myOperationDescription.Behaviors.Find<DataContractSerializerOperationBehavior>();  
if (serializerBehavior == null)  
{  
    serializerBehavior = new DataContractSerializerOperationBehavior(myOperationDescription);  
    myOperationDescription.Behaviors.Add(serializerBehavior);  
}  
  
SerializerBehavior.DataContractResolver = new MyCustomerResolver();  
```  
  
 <span data-ttu-id="0b013-119">서비스에 적용할 수 있는 특성을 구현하여 데이터 계약 확인자를 선언적으로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b013-119">You can declaratively specify a data contract resolver by implementing an attribute that can be applied to a service.</span></span>  [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="0b013-120">[KnownAssemblyAttribute](../../../../docs/framework/wcf/samples/knownassemblyattribute.md) 샘플.</span><span class="sxs-lookup"><span data-stu-id="0b013-120"> the [KnownAssemblyAttribute](../../../../docs/framework/wcf/samples/knownassemblyattribute.md) sample.</span></span> <span data-ttu-id="0b013-121">"Knownassembly" 특성을 구현 하는이 샘플에서 서비스의 동작을 사용자 지정 데이터 계약 확인자를 추가 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b013-121">This sample implements an attribute called "KnownAssembly" that adds a custom data contract resolver to the service’s behavior.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b013-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0b013-122">See Also</span></span>  
 [<span data-ttu-id="0b013-123">데이터 계약 알려진된 형식</span><span class="sxs-lookup"><span data-stu-id="0b013-123">Data Contract Known Types</span></span>](../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)  
 [<span data-ttu-id="0b013-124">DataContractSerializer 샘플</span><span class="sxs-lookup"><span data-stu-id="0b013-124">DataContractSerializer Sample</span></span>](../../../../docs/framework/wcf/samples/datacontractserializer-sample.md)  
 [<span data-ttu-id="0b013-125">KnownAssemblyAttribute</span><span class="sxs-lookup"><span data-stu-id="0b013-125">KnownAssemblyAttribute</span></span>](../../../../docs/framework/wcf/samples/knownassemblyattribute.md)
