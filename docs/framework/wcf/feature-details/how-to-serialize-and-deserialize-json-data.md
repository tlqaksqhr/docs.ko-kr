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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 14029250f3bc26ff8598e0b8d4ccce8e9fcca331
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-serialize-and-deserialize-json-data"></a><span data-ttu-id="061d4-102">방법: JSON 데이터 Serialize 및 Deserialize</span><span class="sxs-lookup"><span data-stu-id="061d4-102">How to: Serialize and Deserialize JSON Data</span></span>
<span data-ttu-id="061d4-103">JSON(JavaScript Object Notation)은 클라이언트 브라우저 및 AJAX 사용 웹 서비스 간에 소량의 데이터를 신속하게 교환할 수 있는 효율적인 데이터 인코딩 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="061d4-103">JSON (JavaScript Object Notation) is an efficient data encoding format that enables fast exchanges of small amounts of data between client browsers and AJAX-enabled Web services.</span></span>  
  
 <span data-ttu-id="061d4-104">이 항목에서는 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>를 사용하여 .NET 형식 개체를 JSON 인코딩된 데이터로 serialize한 다음 JSON 형식의 데이터를 다시 .NET 형식의 인스턴스로 deserialize하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="061d4-104">This topic demonstrates how to serialize .NET type objects into JSON-encoded data and then deserialize data in the JSON format back into instances of .NET types using the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span></span> <span data-ttu-id="061d4-105">이 예제에서는 데이터 계약을 사용하여 사용자 정의 `Person` 형식의 serialization 및 deserialization을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="061d4-105">This example uses a data contract to demonstrate serialization and deserialization of a user-defined `Person` type.</span></span>  
  
 <span data-ttu-id="061d4-106">일반적으로 JSON serialization 및 deserialization은 AJAX 사용 끝점을 통해 노출되는 서비스 작업에서 데이터 계약 형식을 사용하는 경우 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]에 의해 자동으로 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="061d4-106">Normally, JSON serialization and deserialization is handled automatically by [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] when you use data contract types in service operations that are exposed over AJAX-enabled endpoints.</span></span> <span data-ttu-id="061d4-107">그러나 일부 경우에서는 JSON 데이터로 직접 작업해야 할 수도 있습니다. 이 항목에서는 그러한 경우를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="061d4-107">However, in some cases you may need to work with JSON data directly - this is the scenario that this topic demonstrates.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="061d4-108">서버에서 보내는 회신의 serialization 동안 오류가 발생하거나 일부 다른 이유로 인해 회신 작업에서 예외를 throw하는 경우 클라이언트를 오류로 반환하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="061d4-108">If an error occurs during serialization of an outgoing reply on the server or the reply operation throws an exception for some other reason, it may not get returned to the client as a fault.</span></span>  
  
 <span data-ttu-id="061d4-109">이 항목에 따라는 [JSON Serialization](../../../../docs/framework/wcf/samples/json-serialization.md) 샘플.</span><span class="sxs-lookup"><span data-stu-id="061d4-109">This topic is based on the [JSON Serialization](../../../../docs/framework/wcf/samples/json-serialization.md) sample.</span></span>  
  
### <a name="to-define-the-data-contract-for-a-person"></a><span data-ttu-id="061d4-110">사용자에 대한 데이터 계약을 정의하려면</span><span class="sxs-lookup"><span data-stu-id="061d4-110">To define the data contract for a Person</span></span>  
  
1.  <span data-ttu-id="061d4-111">`Person`를 클래스에 연결하고 <xref:System.Runtime.Serialization.DataContractAttribute> 특성을 serialize할 멤버에 연결하여 <xref:System.Runtime.Serialization.DataMemberAttribute>에 대한 데이터 계약을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="061d4-111">Define the data contract for `Person` by attaching the <xref:System.Runtime.Serialization.DataContractAttribute> to the class and <xref:System.Runtime.Serialization.DataMemberAttribute> attribute to the members you want to serialize.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="061d4-112">데이터 계약 참조 [서비스 계약 디자인](../../../../docs/framework/wcf/designing-service-contracts.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="061d4-112"> data contracts, see [Designing Service Contracts](../../../../docs/framework/wcf/designing-service-contracts.md).</span></span>  
  
    ```  
    [DataContract]  
        internal class Person  
        {  
            [DataMember]  
            internal string name;  
  
            [DataMember]  
            internal int age;  
        }  
    ```  
  
### <a name="to-serialize-an-instance-of-type-person-to-json"></a><span data-ttu-id="061d4-113">형식 Person의 인스턴스를 JSON으로 serialize하려면</span><span class="sxs-lookup"><span data-stu-id="061d4-113">To serialize an instance of type Person to JSON</span></span>  
  
1.  <span data-ttu-id="061d4-114">`Person` 형식의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="061d4-114">Create an instance of the `Person` type.</span></span>  
  
    ```  
    Person p = new Person();  
    p.name = "John";  
    p.age = 42;  
    ```  
  
2.  <span data-ttu-id="061d4-115">`Person`를 사용하여 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> 개체를 메모리 스트림으로 serialize합니다.</span><span class="sxs-lookup"><span data-stu-id="061d4-115">Serialize the `Person` object to a memory stream using the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span></span>  
  
    ```  
    MemoryStream stream1 = new MemoryStream();  
    DataContractJsonSerializer ser = new DataContractJsonSerializer(typeof(Person));  
    ```  
  
3.  <span data-ttu-id="061d4-116"><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject%2A> 메서드를 사용하여 JSON 데이터를 스트림에 씁니다.</span><span class="sxs-lookup"><span data-stu-id="061d4-116">Use the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject%2A> method to write JSON data to the stream.</span></span>  
  
    ```  
    ser.WriteObject(stream1, p);  
    ```  
  
4.  <span data-ttu-id="061d4-117">JSON 출력을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="061d4-117">Show the JSON output.</span></span>  
  
    ```  
    stream1.Position = 0;  
    StreamReader sr = new StreamReader(stream1);  
    Console.Write("JSON form of Person object: ");  
    Console.WriteLine(sr.ReadToEnd());  
    ```  
  
### <a name="to-deserialize-an-instance-of-type-person-from-json"></a><span data-ttu-id="061d4-118">JSON에서 형식 Person의 인스턴스를 deserialize하려면</span><span class="sxs-lookup"><span data-stu-id="061d4-118">To deserialize an instance of type Person from JSON</span></span>  
  
1.  <span data-ttu-id="061d4-119">`Person`의 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject%2A> 메서드를 사용하여 JSON 인코딩된 데이터를 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>의 새 인스턴스로 deserialize합니다.</span><span class="sxs-lookup"><span data-stu-id="061d4-119">Deserialize the JSON-encoded data into a new instance of `Person` by using the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject%2A> method of the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span></span>  
  
    ```  
    stream1.Position = 0;  
    Person p2 = (Person)ser.ReadObject(stream1);  
    ```  
  
2.  <span data-ttu-id="061d4-120">결과를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="061d4-120">Show the results.</span></span>  
  
    ```  
    Console.Write("Deserialized back, got name=");  
    Console.Write(p2.name);  
    Console.Write(", age=");  
    Console.WriteLine(p2.age);  
    ```  
  
## <a name="example"></a><span data-ttu-id="061d4-121">예제</span><span class="sxs-lookup"><span data-stu-id="061d4-121">Example</span></span>  
  
```  
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
>  <span data-ttu-id="061d4-122">JSON serializer는 다음 샘플 코드에서처럼 동일한 이름의 여러 멤버를 가진 데이터 계약에 대한 serialization 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="061d4-122">The JSON serializer throws a serialization exception for data contracts that have multiple members with the same name, as shown in the following sample code.</span></span>  
  
```  
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
  
## <a name="see-also"></a><span data-ttu-id="061d4-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="061d4-123">See Also</span></span>  
 [<span data-ttu-id="061d4-124">독립 실행형 JSON Serialization</span><span class="sxs-lookup"><span data-stu-id="061d4-124">Stand-Alone JSON Serialization</span></span>](../../../../docs/framework/wcf/feature-details/stand-alone-json-serialization.md)  
 [<span data-ttu-id="061d4-125">전송 형식 JSON 및 기타 데이터에 대 한 지원</span><span class="sxs-lookup"><span data-stu-id="061d4-125">Support for JSON and Other Data Transfer Formats</span></span>](../../../../docs/framework/wcf/feature-details/support-for-json-and-other-data-transfer-formats.md)
