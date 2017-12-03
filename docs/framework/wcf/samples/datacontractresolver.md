---
title: DataContractResolver
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6c200c02-bc14-4b8d-bbab-9da31185b805
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: aefe0bc0e0be17c2585499e4c943b43672907dfc
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="datacontractresolver"></a><span data-ttu-id="3c982-102">DataContractResolver</span><span class="sxs-lookup"><span data-stu-id="3c982-102">DataContractResolver</span></span>
<span data-ttu-id="3c982-103">이 샘플에서는 <xref:System.Runtime.Serialization.DataContractResolver> 클래스를 사용하여 serialization 및 deserialization 프로세스를 사용자 지정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3c982-103">This sample demonstrates how the serialization and deserialization processes can be customized by using the <xref:System.Runtime.Serialization.DataContractResolver> class.</span></span> <span data-ttu-id="3c982-104">이 샘플에서는 DataContractResolver를 사용하여 serialization 및 deserialization 중에 xsi:type 표현에 대한 CLR 형식의 매핑 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3c982-104">This sample shows how to use a DataContractResolver to map CLR types to and from an xsi:type representation during serialization and deserialization.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="3c982-105">샘플 세부 정보</span><span class="sxs-lookup"><span data-stu-id="3c982-105">Sample Details</span></span>  
 <span data-ttu-id="3c982-106">이 샘플에서는 다음 CLR 형식을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="3c982-106">The sample defines the following CLR types.</span></span>  
  
```csharp  
using System;  
using System.Runtime.Serialization;  
  
namespace Types  
{  
    [DataContract]  
    public class Customer  
    {  
        [DataMember]  
        public string Name { get; set; }  
    }  
  
    [DataContract]  
    public class VIPCustomer : Customer  
    {  
        [DataMember]  
        public string VipInfo { get; set; }  
    }  
  
    [DataContract]  
    public class RegularCustomer : Customer  
    {  
    }  
  
    [DataContract]  
    public class PreferredVIPCustomer : VIPCustomer  
    {  
    }  
}  
```  
  
 <span data-ttu-id="3c982-107">이 샘플에서는 어셈블리를 로드하고 어셈블리의 각 형식을 추출한 다음 serialize 및 deserialize합니다.</span><span class="sxs-lookup"><span data-stu-id="3c982-107">The sample loads the assembly, extracts each of these types, and then serializes and deserializes them.</span></span> <span data-ttu-id="3c982-108"><xref:System.Runtime.Serialization.DataContractResolver>는 다음 예제와 같이 <xref:System.Runtime.Serialization.DataContractResolver> 파생 클래스의 인스턴스를 <xref:System.Runtime.Serialization.DataContractSerializer> 생성자에 전달하여 serialization 프로세스에 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c982-108">The <xref:System.Runtime.Serialization.DataContractResolver> is plugged into the serialization process by passing an instance of the <xref:System.Runtime.Serialization.DataContractResolver>-derived class to the <xref:System.Runtime.Serialization.DataContractSerializer> constructor, as shown in the following example.</span></span>  
  
```csharp  
this.serializer = new DataContractSerializer(typeof(Object), null, int.MaxValue, false, true, null, new MyDataContractResolver(assembly));  
```  
  
 <span data-ttu-id="3c982-109">그런 다음 아래의 코드 예제와 같이 CLR 형식을 serialize합니다.</span><span class="sxs-lookup"><span data-stu-id="3c982-109">The sample then serializes the CLR types as shown in the following code example.</span></span>  
  
```csharp  
Assembly assembly = Assembly.Load(new AssemblyName("Types"));  
  
public void serialize(Type type)  
{  
    Object instance = Activator.CreateInstance(type);  
  
    Console.WriteLine("----------------------------------------");  
    Console.WriteLine();  
    Console.WriteLine("Serializing type: {0}", type.Name);  
    Console.WriteLine();  
    this.buffer = new StringBuilder();  
    using (XmlWriter xmlWriter = XmlWriter.Create(this.buffer))  
    {  
        try  
        {  
            this.serializer.WriteObject(xmlWriter, instance);  
        }  
        catch (SerializationException error)  
        {  
            Console.WriteLine(error.ToString());  
        }  
    }  
    Console.WriteLine(this.buffer.ToString());  
}  
```  
  
 <span data-ttu-id="3c982-110">그런 다음 아래의 코드 예제와 같이 xsi:type을 deserialize합니다.</span><span class="sxs-lookup"><span data-stu-id="3c982-110">The sample then deserializes the xsi:types as shown in the following code example.</span></span>  
  
```csharp  
public void deserialize(Type type)  
{  
    Console.WriteLine();  
    Console.WriteLine("Deserializing type: {0}", type.Name);  
    Console.WriteLine();  
    using (XmlReader xmlReader = XmlReader.Create(new StringReader(this.buffer.ToString())))  
    {  
        Object obj = this.serializer.ReadObject(xmlReader);  
    }  
}  
```  
  
 <span data-ttu-id="3c982-111">사용자 지정 <xref:System.Runtime.Serialization.DataContractResolver>가 <xref:System.Runtime.Serialization.DataContractSerializer> 생성자에 전달되므로 <xref:System.Runtime.Serialization.DataContractResolver.TryResolveType%2A>은 serialization 중에 CLR 형식을 해당하는 `xsi:type`에 매핑하기 위해 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c982-111">Since the custom <xref:System.Runtime.Serialization.DataContractResolver> is passed in to the <xref:System.Runtime.Serialization.DataContractSerializer> constructor, the <xref:System.Runtime.Serialization.DataContractResolver.TryResolveType%2A> is called during serialization to map a CLR type to an equivalent `xsi:type`.</span></span> <span data-ttu-id="3c982-112">이와 마찬가지로 <xref:System.Runtime.Serialization.DataContractResolver.ResolveName%2A>은 deserialization 중에 `xsi:type`을 해당하는 CLR 형식에 매핑하기 위해 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c982-112">Similarly the <xref:System.Runtime.Serialization.DataContractResolver.ResolveName%2A> is called during deserialization to map the `xsi:type` to an equivalent CLR type.</span></span> <span data-ttu-id="3c982-113">이 샘플에서 <xref:System.Runtime.Serialization.DataContractResolver>는 다음 예제와 같이 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c982-113">In this sample, the <xref:System.Runtime.Serialization.DataContractResolver> is defined as shown in the following example.</span></span>  
  
 <span data-ttu-id="3c982-114">다음 코드 예제는 <xref:System.Runtime.Serialization.DataContractResolver>에서 파생되는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="3c982-114">The following code example is a class deriving from <xref:System.Runtime.Serialization.DataContractResolver>.</span></span>  
  
```  
class MyDataContractResolver : DataContractResolver  
{  
    private Dictionary<string, XmlDictionaryString> dictionary = new Dictionary<string, XmlDictionaryString>();  
    Assembly assembly;  
  
    public MyDataContractResolver(Assembly assembly)  
    {  
        this.assembly = assembly;  
    }  
  
    // Used at deserialization  
    // Allows users to map xsi:type name to any Type   
    public override Type ResolveName(string typeName, string typeNamespace, DataContractResolver knownTypeResolver)  
    {  
        XmlDictionaryString tName;  
        XmlDictionaryString tNamespace;  
        if (dictionary.TryGetValue(typeName, out tName) && dictionary.TryGetValue(typeNamespace, out tNamespace))  
        {  
            return this.assembly.GetType(tNamespace.Value + "." + tName.Value);  
        }  
        else  
        {  
            return null;  
        }  
    }  
  
    // Used at serialization  
    // Maps any Type to a new xsi:type representation  
    public override void ResolveType(Type dataContractType, DataContractResolver knownTypeResolver, out XmlDictionaryString typeName, out XmlDictionaryString typeNamespace)  
    {  
        string name = dataContractType.Name;  
        string namesp = dataContractType.Namespace;  
        typeName = new XmlDictionaryString(XmlDictionary.Empty, name, 0);   
        typeNamespace = new XmlDictionaryString(XmlDictionary.Empty, namesp, 0);  
        if (!dictionary.ContainsKey(dataContractType.Name))  
        {  
            dictionary.Add(name, typeName);  
        }  
        if (!dictionary.ContainsKey(dataContractType.Namespace))  
        {  
            dictionary.Add(namesp, typeNamespace);  
        }  
    }  
}  
```  
  
 <span data-ttu-id="3c982-115">샘플에 포함된 Types 프로젝트에서는 이 샘플에 사용되는 모든 형식을 포함하는 어셈블리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="3c982-115">As part of the sample, the Types project generates the assembly with all the types that are used in this sample.</span></span> <span data-ttu-id="3c982-116">이 프로젝트를 사용하여 serialize할 형식을 추가, 제거 또는 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="3c982-116">Use this project to add, remove or modify the types that will be serialized.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="3c982-117">이 샘플을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="3c982-117">To use this sample</span></span>  
  
1.  <span data-ttu-id="3c982-118">[!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]에서 DCRSample.sln 솔루션 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="3c982-118">Using [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], open the DCRSample.sln solution file.</span></span>  
  
2.  <span data-ttu-id="3c982-119">F5 키를 눌러 솔루션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3c982-119">To run the solution, press F5</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="3c982-120">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c982-120">The samples may already be installed on your machine.</span></span> <span data-ttu-id="3c982-121">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="3c982-121">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="3c982-122">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="3c982-122">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="3c982-123">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c982-123">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Data\DataContractResolver`  
  
## <a name="see-also"></a><span data-ttu-id="3c982-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3c982-124">See Also</span></span>  
 [<span data-ttu-id="3c982-125">데이터 계약 확인자를 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="3c982-125">Using a Data Contract Resolver</span></span>](../../../../docs/framework/wcf/feature-details/using-a-data-contract-resolver.md)
