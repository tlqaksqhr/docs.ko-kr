---
title: "NetDataContractSerializer의 기능을 공급하기 위해 DataContractSerializer 및 DataContractResolver를 사용"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1376658f-f695-45f7-a7e0-94664e9619ff
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d189b68cc8321dace0418a3c1e4b1b3c21cfd3ae
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="using-datacontractserializer-and-datacontractresolver-to-provide-the-functionality-of-netdatacontractserializer"></a><span data-ttu-id="7aecb-102">NetDataContractSerializer의 기능을 공급하기 위해 DataContractSerializer 및 DataContractResolver를 사용</span><span class="sxs-lookup"><span data-stu-id="7aecb-102">Using DataContractSerializer and DataContractResolver to Provide the Functionality of NetDataContractSerializer</span></span>
<span data-ttu-id="7aecb-103">이 샘플에서는 <xref:System.Runtime.Serialization.DataContractSerializer>와 적절한 <xref:System.Runtime.Serialization.DataContractResolver>를 함께 사용하여 <xref:System.Runtime.Serialization.NetDataContractSerializer>와 동일한 기능을 제공하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7aecb-103">This sample demonstrates how the use of <xref:System.Runtime.Serialization.DataContractSerializer> with an appropriate <xref:System.Runtime.Serialization.DataContractResolver> provides the same functionality as <xref:System.Runtime.Serialization.NetDataContractSerializer>.</span></span> <span data-ttu-id="7aecb-104">이를 위해 적절한 <xref:System.Runtime.Serialization.DataContractResolver>를 만드는 방법과 이를 <xref:System.Runtime.Serialization.DataContractSerializer>에 추가하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7aecb-104">This sample shows how to create the appropriate <xref:System.Runtime.Serialization.DataContractResolver> and how to add it to the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="7aecb-105">샘플 세부 정보</span><span class="sxs-lookup"><span data-stu-id="7aecb-105">Sample details</span></span>  
 <span data-ttu-id="7aecb-106"><xref:System.Runtime.Serialization.NetDataContractSerializer>는 serialize된 XML에 CLR 형식 정보를 포함하지만 <xref:System.Runtime.Serialization.DataContractSerializer>는 그렇지 않으며 이는 <xref:System.Runtime.Serialization.NetDataContractSerializer>와 <xref:System.Runtime.Serialization.DataContractSerializer>의 중요한 차이점 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="7aecb-106"><xref:System.Runtime.Serialization.NetDataContractSerializer> differs from <xref:System.Runtime.Serialization.DataContractSerializer> in one important way: <xref:System.Runtime.Serialization.NetDataContractSerializer> includes CLR type information in the serialized XML, whereas <xref:System.Runtime.Serialization.DataContractSerializer> does not.</span></span> <span data-ttu-id="7aecb-107">따라서 serialize하는 쪽과 deserialize하는 쪽이 모두 동일한 CLR 형식을 공유하는 경우에만 <xref:System.Runtime.Serialization.NetDataContractSerializer>를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7aecb-107">Therefore, <xref:System.Runtime.Serialization.NetDataContractSerializer> can be used only if both the serializing and deserializing ends share the same CLR types.</span></span> <span data-ttu-id="7aecb-108">그러나 <xref:System.Runtime.Serialization.DataContractSerializer>는 <xref:System.Runtime.Serialization.NetDataContractSerializer>보다 성능이 우수하므로 이를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="7aecb-108">However, it is recommended to use <xref:System.Runtime.Serialization.DataContractSerializer> because its performance is better than <xref:System.Runtime.Serialization.NetDataContractSerializer>.</span></span> <span data-ttu-id="7aecb-109"><xref:System.Runtime.Serialization.DataContractSerializer>에서는 <xref:System.Runtime.Serialization.DataContractResolver>를 추가하여 serialize되는 정보를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7aecb-109">You can change the information that is serialized in <xref:System.Runtime.Serialization.DataContractSerializer> by adding a <xref:System.Runtime.Serialization.DataContractResolver> to it.</span></span>  
  
 <span data-ttu-id="7aecb-110">이 샘플은 두 프로젝트로 구성되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7aecb-110">This sample consists of two projects.</span></span> <span data-ttu-id="7aecb-111">첫 번째 프로젝트에서는 <xref:System.Runtime.Serialization.NetDataContractSerializer>를 사용하여 개체를 serialize합니다.</span><span class="sxs-lookup"><span data-stu-id="7aecb-111">The first project uses <xref:System.Runtime.Serialization.NetDataContractSerializer> to serialize an object.</span></span> <span data-ttu-id="7aecb-112">두 번째 프로젝트에서는 <xref:System.Runtime.Serialization.DataContractSerializer>와 <xref:System.Runtime.Serialization.DataContractResolver>를 함께 사용하여 첫 번째 프로젝트와 동일한 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7aecb-112">The second project uses <xref:System.Runtime.Serialization.DataContractSerializer> with a <xref:System.Runtime.Serialization.DataContractResolver> to provide the same functionality as the first project.</span></span>  
  
 <span data-ttu-id="7aecb-113">다음 코드 예제에서는 DCSwithDCR 프로젝트의 <xref:System.Runtime.Serialization.DataContractResolver>에 추가된 `MyDataContractResolver`라는 사용자 지정 <xref:System.Runtime.Serialization.DataContractSerializer>의 구현을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7aecb-113">The following code example shows the implementation of a custom <xref:System.Runtime.Serialization.DataContractResolver> named `MyDataContractResolver` that is added to the <xref:System.Runtime.Serialization.DataContractSerializer> in the DCSwithDCR project.</span></span>  
  
```  
class MyDataContractResolver : DataContractResolver  
{  
    private XmlDictionary dictionary = new XmlDictionary();  
  
    public MyDataContractResolver()  
    {  
    }  
  
    // Used at deserialization  
    // Allows users to map xsi:type name to any Type   
    public override Type ResolveName(string typeName, string typeNamespace, DataContractResolver knownTypeResolver)  
    {  
        Type type = knownTypeResolver.ResolveName(typeName, typeNamespace, null);  
        if (type == null)  
        {  
            type = Type.GetType(typeName + ", " + typeNamespace);  
        }  
        return type;  
    }  
  
    // Used at serialization  
    // Maps any Type to a new xsi:type representation  
    public override void ResolveType(Type dataContractType, DataContractResolver knownTypeResolver, out XmlDictionaryString typeName, out XmlDictionaryString typeNamespace)  
    {  
        knownTypeResolver.ResolveType(dataContractType, null, out typeName, out typeNamespace);  
        if (typeName == null || typeNamespace == null)  
        {  
            XmlDictionary dictionary = new XmlDictionary();  
            typeName = dictionary.Add(dataContractType.FullName);  
            typeNamespace = dictionary.Add(dataContractType.Assembly.FullName);  
        }  
    }  
}  
```  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="7aecb-114">이 샘플을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="7aecb-114">To use this sample</span></span>  
  
1.  <span data-ttu-id="7aecb-115">[!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]에서 DCRSample.sln 솔루션 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="7aecb-115">Using [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], open the DCRSample.sln solution file.</span></span>  
  
2.  <span data-ttu-id="7aecb-116">솔루션 파일을 마우스 오른쪽 단추로 클릭 하 고 선택 **속성**합니다.</span><span class="sxs-lookup"><span data-stu-id="7aecb-116">Right-click the solution file and choose **Properties**.</span></span>  
  
3.  <span data-ttu-id="7aecb-117">에 **솔루션 속성 페이지** 대화 아래 **공용 속성**, **시작 프로젝트**선택, **여러 개의 시작 프로젝트:**합니다.</span><span class="sxs-lookup"><span data-stu-id="7aecb-117">In the **Solution Property Pages** dialog, under **Common Properties**, **Startup Project**, select **Multiple startup projects:**.</span></span>  
  
4.  <span data-ttu-id="7aecb-118">옆에 **DCSwithDCR** 프로젝트를 **시작** 에서 **동작** 드롭다운입니다.</span><span class="sxs-lookup"><span data-stu-id="7aecb-118">Next to the **DCSwithDCR** project, select **Start** from the **Action** dropdown.</span></span>  
  
5.  <span data-ttu-id="7aecb-119">옆에 **NetDCS** 프로젝트를 **시작** 에서 **동작** 드롭다운입니다.</span><span class="sxs-lookup"><span data-stu-id="7aecb-119">Next to the **NetDCS** project, select **Start** from the **Action** dropdown.</span></span>  
  
6.  <span data-ttu-id="7aecb-120">클릭 **확인** 는 대화 상자를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="7aecb-120">Click **OK** to close the dialog.</span></span>  
  
7.  <span data-ttu-id="7aecb-121">Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="7aecb-121">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
8.  <span data-ttu-id="7aecb-122">Ctrl+F5를 눌러 솔루션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="7aecb-122">To run the solution, press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="7aecb-123">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7aecb-123">The samples may already be installed on your machine.</span></span> <span data-ttu-id="7aecb-124">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="7aecb-124">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="7aecb-125">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="7aecb-125">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="7aecb-126">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7aecb-126">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Data\NetDcSasDcSwithDCR`  
  
## <a name="see-also"></a><span data-ttu-id="7aecb-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7aecb-127">See Also</span></span>
