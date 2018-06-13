---
title: DataContract 서로게이트
ms.date: 03/30/2017
ms.assetid: b0188f3c-00a9-4cf0-a887-a2284c8fb014
ms.openlocfilehash: 3fd2bf028ccb2f75210d5e3fc039bdad7e1e065a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33507865"
---
# <a name="datacontract-surrogate"></a>DataContract 서로게이트
이 샘플에서는 데이터 계약 서로게이트 클래스를 사용하여 serialization, deserialization, 스키마 내보내기 및 스키마 가져오기와 같은 프로세스를 사용자 지정할 수 있는 방법에 대해 설명합니다. 이 샘플에서는 데이터 serialize 되 고 Windows Communication Foundation (WCF) 클라이언트와 서비스 간에 전송 되는 클라이언트 및 서버 시나리오에서 서로게이트를 사용 하는 방법을 보여 줍니다.  
  
> [!NOTE]
>  이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.  
  
 이 샘플에는 다음 서비스 계약이 사용됩니다.  
  
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
  
 `AddEmployee` 작업을 통해 사용자는 새 직원에 대한 데이터를 추가할 수 있으며 `GetEmployee` 작업은 이름을 기준으로 한 직원 검색을 지원합니다.  
  
 이러한 작업에는 다음 데이터 형식이 사용됩니다.  
  
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
  
 `Employee` 형식에서는 다음 샘플 코드의 `Person` 클래스가 유효한 데이터 계약 클래스가 아니므로 <xref:System.Runtime.Serialization.DataContractSerializer>에 의해 serialize될 수 없습니다.  
  
```  
public class Person  
{  
    public string firstName;  
  
    public string lastName;  
  
    public int age;  
  
    public Person() { }  
}  
```  
  
 `DataContract` 특성을 `Person` 클래스에 적용할 수 있지만 항상 가능한 것은 아닙니다. 예를 들어, `Person` 클래스는 제어할 수 없는 별개의 어셈블리에 정의할 수 있습니다.  
  
 이 제한 사항이 있을 경우 `Person` 클래스를 serialize하는 한 가지 방법은 `DataContractAttribute`로 표시된 다른 클래스로 대체하고 필요한 데이터를 새 클래스에 복사하는 것입니다. 이렇게 하는 것은 `Person` 클래스를 <xref:System.Runtime.Serialization.DataContractSerializer>에 대해 DataContract로 표시하기 위해서입니다. 이것은 데이터 계약 클래스가 아닌 클래스를 serialize하는 한 방법이라는 것에 주의하십시오.  
  
 이 샘플에서는 `Person` 클래스를 `PersonSurrogated`라는 다른 클래스로 논리적으로 대체합니다.  
  
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
  
 데이터 계약 서로게이트는 이 대체를 수행하는 데 사용됩니다. 데이터 계약 서로게이트는 <xref:System.Runtime.Serialization.IDataContractSurrogate>를 구현하는 클래스입니다. 이 샘플에서는 `AllowNonSerializableTypesSurrogate` 클래스가 이 인터페이스를 구현합니다.  
  
 인터페이스 구현에서 첫 번째 작업은 `Person`에서 `PersonSurrogated`로의 형식 매핑을 설정하는 것입니다. 이 매핑은 serialization이 발생할 때 뿐만 아니라 스키마 내보내기를 수행할 때 사용됩니다. 이 매핑은 <xref:System.Runtime.Serialization.IDataContractSurrogate.GetDataContractType%28System.Type%29> 메서드를 구현하여 수행할 수 있습니다.  
  
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
  
 다음 샘플 코드와 같이 <xref:System.Runtime.Serialization.IDataContractSurrogate.GetObjectToSerialize%28System.Object%2CSystem.Type%29> 메서드는 serialization 도중에 `Person` 인스턴스를 `PersonSurrogated` 인스턴스에 매핑합니다.  
  
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
  
 다음 샘플 코드와 같이 <xref:System.Runtime.Serialization.IDataContractSurrogate.GetDeserializedObject%28System.Object%2CSystem.Type%29> 메서드는 deserialization을 위한 역방향 매핑을 제공합니다.  
  
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
  
 스키마 가져오기 도중에 `PersonSurrogated` 데이터 계약을 기존 `Person` 클래스에 매핑하기 위해 이 샘플에서는 다음 샘플 코드와 같이 <xref:System.Runtime.Serialization.IDataContractSurrogate.GetReferencedTypeOnImport%28System.String%2CSystem.String%2CSystem.Object%29> 메서드를 구현합니다.  
  
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
  
 다음 샘플 코드에서는 <xref:System.Runtime.Serialization.IDataContractSurrogate> 인터페이스의 구현을 완료합니다.  
  
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
  
 이 샘플에서는 `AllowNonSerializableTypesAttribute`라는 특성에 의해 ServiceModel에서 서로게이트가 사용하도록 설정됩니다. 개발자는 위의 `IPersonnelDataService` 서비스 계약과 같이 해당 서비스 계약에서 이 특성을 적용해야 합니다. 이 특성은 `IContractBehavior`를 구현하고 해당 `ApplyClientBehavior` 및 `ApplyDispatchBehavior` 메서드의 작업에서 서로게이트를 설정합니다.  
  
 이 경우에 이 특성이 필요하지 않지만 이 샘플에서는 이해를 돕기 위해 사용되었습니다. 사용자는 코드나 구성을 사용해 비슷한 `IContractBehavior` `IEndpointBehavior` 또는 `IOperationBehavior`를 추가하여 수동으로 서로게이트를 사용하도록 설정할 수도 있습니다.  
  
 `IContractBehavior` 구현은 등록된 `DataContractSerializerOperationBehavior`가 있는지 확인하여 DataContract를 사용하는 작업을 찾습니다. 작업에 이 동작이 있는 경우 해당 동작에서 `DataContractSurrogate` 속성이 설정됩니다. 다음 샘플 코드에서는 이를 수행하는 방법을 보여 줍니다. 이 작업 동작에서 서로게이트를 설정하면 serialization 및 deserialization에 대해 사용할 수 있도록 설정됩니다.  
  
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
  
 메타데이터 생성 도중 사용할 서로게이트를 플러그 인하기 위해 추가 단계를 수행해야 합니다. 이를 수행하는 한 가지 메커니즘은 이 샘플에서 보여 주는 `IWsdlExportExtension`을 제공하는 것입니다. 또 다른 방법은 `WsdlExporter`를 직접 수정하는 것입니다.  
  
 `AllowNonSerializableTypesAttribute` 구현 특성 `IWsdlExportExtension` 및 `IContractBehavior`합니다. 확장 일 수 있습니다는 `IContractBehavior` 또는 `IEndpointBehavior` 이 경우. 해당 `IWsdlExportExtension.ExportContract` 메서드 구현은 DataContract에 대한 스키마 생성 도중 사용되는 `XsdDataContractExporter`에 추가하여 서로게이트를 사용하도록 설정합니다. 다음 코드 조각에서는 이를 수행하는 방법을 보여 줍니다.  
  
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
  
 샘플을 실행하려면 클라이언트는 AddEmployee를 호출한 다음 GetEmployee를 호출하여 첫 번째 호출이 성공했는지 확인합니다. GetEmployee 작업 요청의 결과는 클라이언트 콘솔 창에 표시됩니다. GetEmployee 작업 직원을 찾는 데 성공 해야 하며 "찾을 수" 인쇄 합니다.  
  
> [!NOTE]
>  이 샘플에서는 serialize, deserialize 및 메타데이터 생성을 위해 서로게이트를 플러그 인하는 방법을 보여 줍니다. 메타데이터에서의 코드 생성을 위해 서로게이트를 플러그 인하는 방법을 제공되지 않습니다. 클라이언트 코드 생성에 연결 하는 서로게이트를 사용할 수 있는 방법을의 예제를 보려면를 참조 하십시오.는 [사용자 지정 WSDL 게시](../../../../docs/framework/wcf/samples/custom-wsdl-publication.md) 샘플.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>샘플을 설치, 빌드 및 실행하려면  
  
1.  수행 했는지 확인 하십시오.는 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.  
  
2.  지침에 따라 솔루션의 C# 버전을 빌드하려면 [Windows Communication Foundation 샘플 빌드](../../../../docs/framework/wcf/samples/building-the-samples.md)합니다.  
  
3.  지침에 따라 단일 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4에 대 한 Windows WF (Workflow Foundation) 샘플](http://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\DataContract`  
  
## <a name="see-also"></a>참고 항목
