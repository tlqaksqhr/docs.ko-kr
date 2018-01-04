---
title: "DataContract 서로게이트"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b0188f3c-00a9-4cf0-a887-a2284c8fb014
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f14b69cba50839f3c4105b286af4de0523385b38
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="datacontract-surrogate"></a><span data-ttu-id="19cb4-102">DataContract 서로게이트</span><span class="sxs-lookup"><span data-stu-id="19cb4-102">DataContract Surrogate</span></span>
<span data-ttu-id="19cb4-103">이 샘플에서는 데이터 계약 서로게이트 클래스를 사용하여 serialization, deserialization, 스키마 내보내기 및 스키마 가져오기와 같은 프로세스를 사용자 지정할 수 있는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="19cb4-103">This sample demonstrates how processes like serialization, deserialization, schema export, and schema import can be customized using a data contract surrogate class.</span></span> <span data-ttu-id="19cb4-104">이 샘플에서는 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 클라이언트와 서비스 사이에서 데이터를 serialize하여 전송하는 클라이언트 및 서버 시나리오에서 서로게이트를 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="19cb4-104">This sample shows how to use a surrogate in a client and server scenario where data is serialized and transmitted between a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] client and service.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="19cb4-105">이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19cb4-105">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="19cb4-106">이 샘플에는 다음 서비스 계약이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="19cb4-106">The sample uses the following service contract:</span></span>  
  
```  
[ServiceContract(Namespace = "http://Microsoft.ServiceModel.Samples")]  
[AllowNonSerializableTypes]  
public interface IPersonnelDataService  
{  
    [OperationContract]  
    void AddEmployee(Employee employee);  
  
    [OperationContract]  
    Employee GetEmployee(string name);  
}  
```  
  
 <span data-ttu-id="19cb4-107">`AddEmployee` 작업을 통해 사용자는 새 직원에 대한 데이터를 추가할 수 있으며 `GetEmployee` 작업은 이름을 기준으로 한 직원 검색을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="19cb4-107">The `AddEmployee` operation allows users to add data about new employees and the `GetEmployee` operation supports search for employees based on name.</span></span>  
  
 <span data-ttu-id="19cb4-108">이러한 작업에는 다음 데이터 형식이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="19cb4-108">These operations use the following data type:</span></span>  
  
```  
[DataContract(Namespace = "http://Microsoft.ServiceModel.Samples")]  
class Employee  
{  
    [DataMember]  
    public DateTime dateHired;  
  
    [DataMember]  
    public Decimal salary;  
  
    [DataMember]  
    public Person person;  
}  
```  
  
 <span data-ttu-id="19cb4-109">`Employee` 형식에서는 다음 샘플 코드의 `Person` 클래스가 유효한 데이터 계약 클래스가 아니므로 <xref:System.Runtime.Serialization.DataContractSerializer>에 의해 serialize될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="19cb4-109">In the `Employee` type, the `Person` class (shown in the following sample code) cannot be serialized by the <xref:System.Runtime.Serialization.DataContractSerializer> because it is not a valid data contract class.</span></span>  
  
```  
public class Person  
{  
    public string firstName;  
  
    public string lastName;  
  
    public int age;  
  
    public Person() { }  
}  
```  
  
 <span data-ttu-id="19cb4-110">`DataContract` 특성을 `Person` 클래스에 적용할 수 있지만 항상 가능한 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="19cb4-110">You can apply the `DataContract` attribute to the `Person` class, but this is not always possible.</span></span> <span data-ttu-id="19cb4-111">예를 들어, `Person` 클래스는 제어할 수 없는 별개의 어셈블리에 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19cb4-111">For example, the `Person` class can be defined in a separate assembly over which you have no control.</span></span>  
  
 <span data-ttu-id="19cb4-112">이 제한 사항이 있을 경우 `Person` 클래스를 serialize하는 한 가지 방법은 `DataContractAttribute`로 표시된 다른 클래스로 대체하고 필요한 데이터를 새 클래스에 복사하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="19cb4-112">Given this restriction, one way to serialize the `Person` class is to substitute it with another class that is marked with `DataContractAttribute` and copy over necessary data to the new class.</span></span> <span data-ttu-id="19cb4-113">이렇게 하는 것은 `Person` 클래스를 <xref:System.Runtime.Serialization.DataContractSerializer>에 대해 DataContract로 표시하기 위해서입니다.</span><span class="sxs-lookup"><span data-stu-id="19cb4-113">The objective is to make the `Person` class appear as a DataContract to the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span> <span data-ttu-id="19cb4-114">이것은 데이터 계약 클래스가 아닌 클래스를 serialize하는 한 방법이라는 것에 주의하십시오.</span><span class="sxs-lookup"><span data-stu-id="19cb4-114">Note that this is one way to serialize non-data contract classes.</span></span>  
  
 <span data-ttu-id="19cb4-115">이 샘플에서는 `Person` 클래스를 `PersonSurrogated`라는 다른 클래스로 논리적으로 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="19cb4-115">The sample logically replaces the `Person` class with a different class named `PersonSurrogated`.</span></span>  
  
```  
[DataContract(Name="Person", Namespace = "http://Microsoft.ServiceModel.Samples")]  
public class PersonSurrogated  
{  
    [DataMember]  
    public string FirstName;  
  
    [DataMember]  
    public string LastName;  
  
    [DataMember]  
    public int Age;  
}  
```  
  
 <span data-ttu-id="19cb4-116">데이터 계약 서로게이트는 이 대체를 수행하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="19cb4-116">The data contract surrogate is used to achieve this replacement.</span></span> <span data-ttu-id="19cb4-117">데이터 계약 서로게이트는 <xref:System.Runtime.Serialization.IDataContractSurrogate>를 구현하는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="19cb4-117">A data contract surrogate is a class that implements <xref:System.Runtime.Serialization.IDataContractSurrogate>.</span></span> <span data-ttu-id="19cb4-118">이 샘플에서는 `AllowNonSerializableTypesSurrogate` 클래스가 이 인터페이스를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="19cb4-118">In this sample, the `AllowNonSerializableTypesSurrogate` class implements this interface.</span></span>  
  
 <span data-ttu-id="19cb4-119">인터페이스 구현에서 첫 번째 작업은 `Person`에서 `PersonSurrogated`로의 형식 매핑을 설정하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="19cb4-119">In the interface implementation, the first task is to establish a type mapping from `Person` to `PersonSurrogated`.</span></span> <span data-ttu-id="19cb4-120">이 매핑은 serialization이 발생할 때 뿐만 아니라 스키마 내보내기를 수행할 때 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="19cb4-120">This is used both at serialization time as well as at schema export time.</span></span> <span data-ttu-id="19cb4-121">이 매핑은 <xref:System.Runtime.Serialization.IDataContractSurrogate.GetDataContractType%28System.Type%29> 메서드를 구현하여 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19cb4-121">This mapping is achieved by implementing the <xref:System.Runtime.Serialization.IDataContractSurrogate.GetDataContractType%28System.Type%29> method.</span></span>  
  
```  
public Type GetDataContractType(Type type)  
{  
    if (typeof(Person).IsAssignableFrom(type))  
    {  
        return typeof(PersonSurrogated);  
    }  
    return type;  
}  
```  
  
 <span data-ttu-id="19cb4-122">다음 샘플 코드와 같이 <xref:System.Runtime.Serialization.IDataContractSurrogate.GetObjectToSerialize%28System.Object%2CSystem.Type%29> 메서드는 serialization 도중에 `Person` 인스턴스를 `PersonSurrogated` 인스턴스에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="19cb4-122">The <xref:System.Runtime.Serialization.IDataContractSurrogate.GetObjectToSerialize%28System.Object%2CSystem.Type%29> method maps a `Person` instance to a `PersonSurrogated` instance during serialization, as shown in the following sample code.</span></span>  
  
```  
public object GetObjectToSerialize(object obj, Type targetType)  
{  
    if (obj is Person)  
    {  
        Person person = (Person)obj;  
        PersonSurrogated personSurrogated = new PersonSurrogated();  
        personSurrogated.FirstName = person.firstName;  
        personSurrogated.LastName = person.lastName;  
        personSurrogated.Age = person.age;  
        return personSurrogated;  
    }  
    return obj;  
}  
```  
  
 <span data-ttu-id="19cb4-123">다음 샘플 코드와 같이 <xref:System.Runtime.Serialization.IDataContractSurrogate.GetDeserializedObject%28System.Object%2CSystem.Type%29> 메서드는 deserialization을 위한 역방향 매핑을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="19cb4-123">The <xref:System.Runtime.Serialization.IDataContractSurrogate.GetDeserializedObject%28System.Object%2CSystem.Type%29> method provides the reverse mapping for deserialization, as shown in the following sample code.</span></span>  
  
```  
public object GetDeserializedObject(object obj,   
Type targetType)  
{  
    if (obj is PersonSurrogated)  
    {  
        PersonSurrogated personSurrogated = (PersonSurrogated)obj;  
        Person person = new Person();  
        person.firstName = personSurrogated.FirstName;  
        person.lastName = personSurrogated.LastName;  
        person.age = personSurrogated.Age;  
        return person;  
    }  
    return obj;  
}  
```  
  
 <span data-ttu-id="19cb4-124">스키마 가져오기 도중에 `PersonSurrogated` 데이터 계약을 기존 `Person` 클래스에 매핑하기 위해 이 샘플에서는 다음 샘플 코드와 같이 <xref:System.Runtime.Serialization.IDataContractSurrogate.GetReferencedTypeOnImport%28System.String%2CSystem.String%2CSystem.Object%29> 메서드를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="19cb4-124">To map the `PersonSurrogated` data contract to the existing `Person` class during schema import, the sample implements the <xref:System.Runtime.Serialization.IDataContractSurrogate.GetReferencedTypeOnImport%28System.String%2CSystem.String%2CSystem.Object%29> method, as shown in the following sample code.</span></span>  
  
```  
public Type GetReferencedTypeOnImport(string typeName,   
               string typeNamespace, object customData)  
{  
if (  
typeNamespace.Equals("http://schemas.datacontract.org/2004/07/DCSurrogateSample")  
)  
    {  
         if (typeName.Equals("PersonSurrogated"))  
        {  
             return typeof(Person);  
        }  
     }  
     return null;  
}  
```  
  
 <span data-ttu-id="19cb4-125">다음 샘플 코드에서는 <xref:System.Runtime.Serialization.IDataContractSurrogate> 인터페이스의 구현을 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="19cb4-125">The following sample code completes the implementation of the <xref:System.Runtime.Serialization.IDataContractSurrogate> interface.</span></span>  
  
```  
public System.CodeDom.CodeTypeDeclaration ProcessImportedType(  
          System.CodeDom.CodeTypeDeclaration typeDeclaration,   
          System.CodeDom.CodeCompileUnit compileUnit)  
{  
    return typeDeclaration;  
}  
public object GetCustomDataToExport(Type clrType,   
                               Type dataContractType)  
{  
    return null;  
}  
  
public object GetCustomDataToExport(  
System.Reflection.MemberInfo memberInfo, Type dataContractType)  
{  
    return null;  
}  
public void GetKnownCustomDataTypes(  
        KnownTypeCollection customDataTypes)  
{  
    // It does not matter what we do here.  
    throw new NotImplementedException();  
}  
```  
  
 <span data-ttu-id="19cb4-126">이 샘플에서는 `AllowNonSerializableTypesAttribute`라는 특성에 의해 ServiceModel에서 서로게이트가 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="19cb4-126">In this sample, the surrogate is enabled in ServiceModel by an attribute called `AllowNonSerializableTypesAttribute`.</span></span> <span data-ttu-id="19cb4-127">개발자는 위의 `IPersonnelDataService` 서비스 계약과 같이 해당 서비스 계약에서 이 특성을 적용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="19cb4-127">Developers would need to apply this attribute on their service contract as shown on the `IPersonnelDataService` service contract above.</span></span> <span data-ttu-id="19cb4-128">이 특성은 `IContractBehavior`를 구현하고 해당 `ApplyClientBehavior` 및 `ApplyDispatchBehavior` 메서드의 작업에서 서로게이트를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="19cb4-128">This attribute implements `IContractBehavior` and sets up the surrogate on operations in its `ApplyClientBehavior` and `ApplyDispatchBehavior` methods.</span></span>  
  
 <span data-ttu-id="19cb4-129">이 경우에 이 특성이 필요하지 않지만 이 샘플에서는 이해를 돕기 위해 사용되었습니다.</span><span class="sxs-lookup"><span data-stu-id="19cb4-129">The attribute is not necessary in this case - it is used for demonstration purposes in this sample.</span></span> <span data-ttu-id="19cb4-130">사용자는 코드나 구성을 사용해 비슷한 `IContractBehavior` `IEndpointBehavior` 또는 `IOperationBehavior`를 추가하여 수동으로 서로게이트를 사용하도록 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19cb4-130">Users can alternatively enable a surrogate by manually adding a similar `IContractBehavior`, `IEndpointBehavior` or `IOperationBehavior` using code or using configuration.</span></span>  
  
 <span data-ttu-id="19cb4-131">`IContractBehavior` 구현은 등록된 `DataContractSerializerOperationBehavior`가 있는지 확인하여 DataContract를 사용하는 작업을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="19cb4-131">The `IContractBehavior` implementation looks for operations that use DataContract by checking if they have a `DataContractSerializerOperationBehavior` registered.</span></span> <span data-ttu-id="19cb4-132">작업에 이 동작이 있는 경우 해당 동작에서 `DataContractSurrogate` 속성이 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="19cb4-132">If they do, it sets the `DataContractSurrogate` property on that behavior.</span></span> <span data-ttu-id="19cb4-133">다음 샘플 코드에서는 이를 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="19cb4-133">The following sample code shows how this is done.</span></span> <span data-ttu-id="19cb4-134">이 작업 동작에서 서로게이트를 설정하면 serialization 및 deserialization에 대해 사용할 수 있도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="19cb4-134">Setting the surrogate on this operation behavior enables it for serialization and deserialization.</span></span>  
  
```  
public void ApplyClientBehavior(ContractDescription description, ServiceEndpoint endpoint, System.ServiceModel.Dispatcher.ClientRuntime proxy)  
{  
    foreach (OperationDescription opDesc in description.Operations)  
    {  
        ApplyDataContractSurrogate(opDesc);  
    }  
}  
  
public void ApplyDispatchBehavior(ContractDescription description, ServiceEndpoint endpoint, System.ServiceModel.Dispatcher.DispatchRuntime dispatch)  
{  
    foreach (OperationDescription opDesc in description.Operations)  
    {  
        ApplyDataContractSurrogate(opDesc);  
    }  
}  
  
private static void ApplyDataContractSurrogate(OperationDescription description)  
{  
    DataContractSerializerOperationBehavior dcsOperationBehavior = description.Behaviors.Find<DataContractSerializerOperationBehavior>();  
    if (dcsOperationBehavior != null)  
    {  
        if (dcsOperationBehavior.DataContractSurrogate == null)  
            dcsOperationBehavior.DataContractSurrogate = new AllowNonSerializableTypesSurrogate();  
    }  
}  
```  
  
 <span data-ttu-id="19cb4-135">메타데이터 생성 도중 사용할 서로게이트를 플러그 인하기 위해 추가 단계를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="19cb4-135">Additional steps need to be taken to plug in the surrogate for use during metadata generation.</span></span> <span data-ttu-id="19cb4-136">이를 수행하는 한 가지 메커니즘은 이 샘플에서 보여 주는 `IWsdlExportExtension`을 제공하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="19cb4-136">One mechanism to do this is to provide an `IWsdlExportExtension` which is what this sample demonstrates.</span></span> <span data-ttu-id="19cb4-137">또 다른 방법은 `WsdlExporter`를 직접 수정하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="19cb4-137">Another way is to modify the `WsdlExporter` directly.</span></span>  
  
 <span data-ttu-id="19cb4-138">`AllowNonSerializableTypesAttribute` 구현 특성 `IWsdlExportExtension` 및 `IContractBehavior`합니다.</span><span class="sxs-lookup"><span data-stu-id="19cb4-138">The `AllowNonSerializableTypesAttribute` attribute implements `IWsdlExportExtension` and `IContractBehavior`.</span></span> <span data-ttu-id="19cb4-139">확장 일 수 있습니다는 `IContractBehavior` 또는 `IEndpointBehavior` 이 경우.</span><span class="sxs-lookup"><span data-stu-id="19cb4-139">The extension can be either an `IContractBehavior` or `IEndpointBehavior` in this case.</span></span> <span data-ttu-id="19cb4-140">해당 `IWsdlExportExtension.ExportContract` 메서드 구현은 DataContract에 대한 스키마 생성 도중 사용되는 `XsdDataContractExporter`에 추가하여 서로게이트를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="19cb4-140">Its `IWsdlExportExtension.ExportContract` method implementation enables the surrogate by adding it to the `XsdDataContractExporter` used during schema generation for DataContract.</span></span> <span data-ttu-id="19cb4-141">다음 코드 조각에서는 이를 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="19cb4-141">The following code snippet shows how to do this.</span></span>  
  
```  
public void ExportContract(WsdlExporter exporter, WsdlContractConversionContext context)  
{  
    if (exporter == null)  
        throw new ArgumentNullException("exporter");  
  
    object dataContractExporter;  
    XsdDataContractExporter xsdDCExporter;  
    if (!exporter.State.TryGetValue(typeof(XsdDataContractExporter), out dataContractExporter))  
    {  
        xsdDCExporter = new XsdDataContractExporter(exporter.GeneratedXmlSchemas);  
        exporter.State.Add(typeof(XsdDataContractExporter), xsdDCExporter);  
    }  
    else  
    {  
        xsdDCExporter = (XsdDataContractExporter)dataContractExporter;  
    }  
    if (xsdDCExporter.Options == null)  
        xsdDCExporter.Options = new ExportOptions();  
  
    if (xsdDCExporter.Options.DataContractSurrogate == null)  
        xsdDCExporter.Options.DataContractSurrogate = new AllowNonSerializableTypesSurrogate();  
}  
```  
  
 <span data-ttu-id="19cb4-142">샘플을 실행하려면 클라이언트는 AddEmployee를 호출한 다음 GetEmployee를 호출하여 첫 번째 호출이 성공했는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="19cb4-142">When you run the sample, the client calls AddEmployee followed by a GetEmployee call to check if the first call was successful.</span></span> <span data-ttu-id="19cb4-143">GetEmployee 작업 요청의 결과는 클라이언트 콘솔 창에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="19cb4-143">The result of the GetEmployee operation request is displayed in the client console window.</span></span> <span data-ttu-id="19cb4-144">GetEmployee 작업 직원을 찾는 데 성공 해야 하며 "찾을 수" 인쇄 합니다.</span><span class="sxs-lookup"><span data-stu-id="19cb4-144">The GetEmployee operation must succeed in finding the employee and print "found".</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="19cb4-145">이 샘플에서는 serialize, deserialize 및 메타데이터 생성을 위해 서로게이트를 플러그 인하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="19cb4-145">This sample shows how to plug in a surrogate for serialize, deserialize and metadata generation.</span></span> <span data-ttu-id="19cb4-146">메타데이터에서의 코드 생성을 위해 서로게이트를 플러그 인하는 방법을 제공되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="19cb4-146">It does not show how to plug in a surrogate for code generation from metadata.</span></span> <span data-ttu-id="19cb4-147">클라이언트 코드 생성에 연결 하는 서로게이트를 사용할 수 있는 방법을의 예제를 보려면를 참조 하십시오.는 [사용자 지정 WSDL 게시](../../../../docs/framework/wcf/samples/custom-wsdl-publication.md) 샘플.</span><span class="sxs-lookup"><span data-stu-id="19cb4-147">To see a sample of how a surrogate can be used to plug into client code generation, see the [Custom WSDL Publication](../../../../docs/framework/wcf/samples/custom-wsdl-publication.md) sample.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="19cb4-148">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="19cb4-148">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="19cb4-149">수행 했는지 확인 하십시오.는 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="19cb4-149">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="19cb4-150">지침에 따라 솔루션의 C# 버전을 빌드하려면 [Windows Communication Foundation 샘플 빌드](../../../../docs/framework/wcf/samples/building-the-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="19cb4-150">To build the C# edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="19cb4-151">지침에 따라 단일 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="19cb4-151">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="19cb4-152">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19cb4-152">The samples may already be installed on your machine.</span></span> <span data-ttu-id="19cb4-153">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="19cb4-153">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="19cb4-154">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="19cb4-154">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="19cb4-155">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19cb4-155">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\DataContract`  
  
## <a name="see-also"></a><span data-ttu-id="19cb4-156">참고 항목</span><span class="sxs-lookup"><span data-stu-id="19cb4-156">See Also</span></span>
