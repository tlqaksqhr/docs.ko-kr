---
title: "방법: JSON 데이터 Serialize 및 Deserialize"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 88abc1fb-8196-4ee3-a23b-c6934144d1dd
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 994ccb677d1376eff5b889a0a4ddfe072557bdea
ms.sourcegitcommit: 2142a4732bb4ff519b9817db4c24a237b9810d4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/05/2018
---
# <a name="how-to-serialize-and-deserialize-json-data"></a>방법: JSON 데이터 Serialize 및 Deserialize
JSON(JavaScript Object Notation)은 클라이언트 브라우저 및 AJAX 사용 웹 서비스 간에 소량의 데이터를 신속하게 교환할 수 있는 효율적인 데이터 인코딩 형식입니다.  
  
 이 항목에서는 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>를 사용하여 .NET 형식 개체를 JSON 인코딩된 데이터로 serialize한 다음 JSON 형식의 데이터를 다시 .NET 형식의 인스턴스로 deserialize하는 방법을 보여 줍니다. 이 예제에서는 데이터 계약을 사용하여 사용자 정의 `Person` 형식의 serialization 및 deserialization을 보여 줍니다.  
  
 일반적으로 JSON serialization 및 deserialization은 AJAX 사용 끝점을 통해 노출되는 서비스 작업에서 데이터 계약 형식을 사용하는 경우 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]에 의해 자동으로 처리됩니다. 그러나 일부 경우에서는 JSON 데이터로 직접 작업해야 할 수도 있습니다. 이 항목에서는 그러한 경우를 보여 줍니다.  
  
> [!NOTE]
>  서버에서 보내는 회신의 serialization 동안 오류가 발생하거나 일부 다른 이유로 인해 회신 작업에서 예외를 throw하는 경우 클라이언트를 오류로 반환하지 않을 수 있습니다.  
  
 이 항목에 따라는 [JSON Serialization](../../../../docs/framework/wcf/samples/json-serialization.md) 샘플.  
  
### <a name="to-define-the-data-contract-for-a-person"></a>사용자에 대한 데이터 계약을 정의하려면  
  
1.  `Person`를 클래스에 연결하고 <xref:System.Runtime.Serialization.DataContractAttribute> 특성을 serialize할 멤버에 연결하여 <xref:System.Runtime.Serialization.DataMemberAttribute>에 대한 데이터 계약을 정의합니다. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]데이터 계약 참조 [서비스 계약 디자인](../../../../docs/framework/wcf/designing-service-contracts.md)합니다.  
  
    ```csharp  
    [DataContract]  
    internal class Person  
    {  
        [DataMember]  
        internal string name;  
  
        [DataMember]  
        internal int age;  
    }  
    ```  
  
### <a name="to-serialize-an-instance-of-type-person-to-json"></a>형식 Person의 인스턴스를 JSON으로 serialize하려면  
  
1.  `Person` 형식의 인스턴스를 만듭니다.  
  
    ```csharp  
    Person p = new Person();  
    p.name = "John";  
    p.age = 42;  
    ```  
  
2.  `Person`를 사용하여 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> 개체를 메모리 스트림으로 serialize합니다.  
  
    ```csharp  
    MemoryStream stream1 = new MemoryStream();  
    DataContractJsonSerializer ser = new DataContractJsonSerializer(typeof(Person));  
    ```  
  
3.  <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject%2A> 메서드를 사용하여 JSON 데이터를 스트림에 씁니다.  
  
    ```csharp  
    ser.WriteObject(stream1, p);  
    ```  
  
4.  JSON 출력을 표시합니다.  
  
    ```csharp  
    stream1.Position = 0;  
    StreamReader sr = new StreamReader(stream1);  
    Console.Write("JSON form of Person object: ");  
    Console.WriteLine(sr.ReadToEnd());  
    ```  
  
### <a name="to-deserialize-an-instance-of-type-person-from-json"></a>JSON에서 형식 Person의 인스턴스를 deserialize하려면  
  
1.  `Person`의 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject%2A> 메서드를 사용하여 JSON 인코딩된 데이터를 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>의 새 인스턴스로 deserialize합니다.  
  
    ```csharp  
    stream1.Position = 0;  
    Person p2 = (Person)ser.ReadObject(stream1);  
    ```  
  
2.  결과를 표시합니다.  
  
    ```csharp  
    Console.WriteLine($"Deserialized back, got name={p2.name}, age={p2.age}");  
    ```  
  
## <a name="example"></a>예  
  
```csharp  
// Create a User object and serialize it to a JSON stream.  
public static string WriteFromObject()  
{  
    //Create User object.  
    User user = new User("Bob", 42);  
  
    //Create a stream to serialize the object to.  
    MemoryStream ms = new MemoryStream();  
  
    // Serializer the User object to the stream.  
    DataContractJsonSerializer ser = new DataContractJsonSerializer(typeof(User));  
    ser.WriteObject(ms, user);  
    byte[] json = ms.ToArray();  
    ms.Close();  
    return Encoding.UTF8.GetString(json, 0, json.Length);  
}  
  
// Deserialize a JSON stream to a User object.  
public static User ReadToObject(string json)  
{  
    User deserializedUser = new User();  
    MemoryStream ms = new MemoryStream(Encoding.UTF8.GetBytes(json));  
    DataContractJsonSerializer ser = new DataContractJsonSerializer(deserializedUser.GetType());  
    deserializedUser = ser.ReadObject(ms) as User;  
    ms.Close();  
    return deserializedUser;  
}  
```  
  
> [!NOTE]
>  JSON serializer는 다음 샘플 코드에서처럼 동일한 이름의 여러 멤버를 가진 데이터 계약에 대한 serialization 예외를 throw합니다.  
  
```csharp  
[DataContract]  
public class TestDuplicateDataBase  
{  
    [DataMember]  
    public int field1 = 123;  
}

[DataContract]  
public class TestDuplicateDataDerived : TestDuplicateDataBase  
{  
    [DataMember]  
    public new int field1 = 999;  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [독립 실행형 JSON Serialization](../../../../docs/framework/wcf/feature-details/stand-alone-json-serialization.md)  
 [JSON 및 기타 데이터 전송 형식에 대한 지원](../../../../docs/framework/wcf/feature-details/support-for-json-and-other-data-transfer-formats.md)
