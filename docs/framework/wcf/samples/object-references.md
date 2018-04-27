---
title: 개체 참조
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7a93d260-91c3-4448-8f7a-a66fb562fc23
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: fcb34efeb7eed28f85774dc5489b3e56aeac4e6c
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="object-references"></a><span data-ttu-id="a7433-102">개체 참조</span><span class="sxs-lookup"><span data-stu-id="a7433-102">Object References</span></span>
<span data-ttu-id="a7433-103">이 샘플에서는 서버와 클라이언트 간에 개체를 참조로 전달하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a7433-103">This sample demonstrates how to pass objects by references between server and client.</span></span> <span data-ttu-id="a7433-104">샘플에서는 시뮬레이션 된 *소셜 네트워크*합니다.</span><span class="sxs-lookup"><span data-stu-id="a7433-104">The sample uses simulated *social networks*.</span></span> <span data-ttu-id="a7433-105">인맥 네트워크는 친구 목록을 포함하는 `Person` 클래스로 구성되며, 이 목록의 친구는 `Person` 클래스의 인스턴스이며 자체적으로도 친구 목록을 가지고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7433-105">A social network consists of a `Person` class that contains a list of friends in which each friend is an instance of the `Person` class, with its own list of friends.</span></span> <span data-ttu-id="a7433-106">이를 기반으로 개체 그래프가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7433-106">This creates a graph of objects.</span></span> <span data-ttu-id="a7433-107">서비스는 이러한 인맥 네트워크에 대한 작업을 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="a7433-107">The service exposes operations on these social networks.</span></span>  
  
 <span data-ttu-id="a7433-108">이 샘플에서 서비스는 IIS(인터넷 정보 서비스)를 통해 호스팅되고 클라이언트는 콘솔 응용 프로그램(.exe)입니다.</span><span class="sxs-lookup"><span data-stu-id="a7433-108">In this sample, the service is hosted by Internet Information Services (IIS) and the client is a console application (.exe).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a7433-109">이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7433-109">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
## <a name="service"></a><span data-ttu-id="a7433-110">서비스</span><span class="sxs-lookup"><span data-stu-id="a7433-110">Service</span></span>  
 <span data-ttu-id="a7433-111">`Person` 클래스에는 <xref:System.Runtime.Serialization.DataContractAttribute> 특성이 적용되어 있으며, 클래스를 참조 형식으로 선언하도록 <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> 필드가 `true`로 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7433-111">The `Person` class has the <xref:System.Runtime.Serialization.DataContractAttribute> attribute applied, with the <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> field set to `true` to declare it as a reference type.</span></span> <span data-ttu-id="a7433-112">모든 속성에는 <xref:System.Runtime.Serialization.DataMemberAttribute> 특성이 적용되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7433-112">All properties have the <xref:System.Runtime.Serialization.DataMemberAttribute> attribute applied.</span></span>  
  
```  
[DataContract(IsReference=true)]  
public class Person  
{  
    string name;  
    string location;  
    string gender;  
    int age;  
    List<Person> friends;  
    [DataMember()]  
    public string Name  
    {  
        get { return name; }  
        set { name = value; }  
    }  
    [DataMember()]  
    public string Location  
    {  
        get { return location; }  
        set { location = value; }  
    }  
    [DataMember()]  
    public string Gender  
    {  
        get { return gender; }  
        set { gender = value; }  
    }  
…  
}  
```  
  
 <span data-ttu-id="a7433-113">`GetPeopleInNetwork` 작업은 `Person` 형식의 매개 변수를 받아 인맥 네트워크의 모든 사람, 즉 `friends` 목록에 있는 모든 사람과 친구의 친구 등을 중복되는 항목 없이 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="a7433-113">The `GetPeopleInNetwork` operation takes a parameter of type `Person` and returns all the people in the network; that is, all the people in the `friends` list, the friend's friends, and so on, without duplicates.</span></span>  
  
```  
public List<Person> GetPeopleInNetwork(Person p)  
{  
    List<Person> people = new List<Person>();  
    ListPeopleInNetwork(p, people);  
    return people;  
  
}  
```  
  
 <span data-ttu-id="a7433-114">`GetMutualFriends` 작업은 `Person` 형식의 매개 변수를 받아 서로의 `friends` 목록에 동시에 존재하는 모든 친구를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="a7433-114">The `GetMutualFriends` operation takes a parameter of type `Person` and returns all the friends in the list who also have this person in their `friends` list.</span></span>  
  
```  
public List<Person> GetMutualFriends(Person p)  
{  
    List<Person> mutual = new List<Person>();  
    foreach (Person friend in p.Friends)  
    {  
        if (friend.Friends.Contains(p))  
            mutual.Add(friend);  
    }  
    return mutual;  
}  
```  
  
 <span data-ttu-id="a7433-115">`GetCommonFriends` 작업은 `Person` 형식의 목록을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a7433-115">The `GetCommonFriends` operation takes a list of type `Person`.</span></span> <span data-ttu-id="a7433-116">이 목록에는 두 개의 `Person` 개체가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7433-116">The list is expected to have two `Person` objects in it.</span></span> <span data-ttu-id="a7433-117">이 작업은 입력 목록에 있는 두 `Person` 개체 모두의 `friends` 목록에 있는 `Person` 개체의 목록을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="a7433-117">The operation returns a list of `Person` objects that are in the `friends` lists of both `Person` objects in the input list.</span></span>  
  
```  
public List<Person> GetCommonFriends(List<Person> people)  
{  
    List<Person> common = new List<Person>();  
    foreach (Person friend in people[0].Friends)  
        if (people[1].Friends.Contains(friend))  
            common.Add(friend);  
    return common;  
}  
```  
  
## <a name="client"></a><span data-ttu-id="a7433-118">클라이언트</span><span class="sxs-lookup"><span data-stu-id="a7433-118">Client</span></span>  
 <span data-ttu-id="a7433-119">클라이언트 프록시를 사용 하 여 만들어집니다는 **서비스 참조 추가** Visual Studio의 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="a7433-119">The client proxy is created using the **Add Service Reference** feature of Visual Studio.</span></span>  
  
 <span data-ttu-id="a7433-120">5개의 `Person` 개체로 구성된 인맥 네트워크가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7433-120">A social network that consists of five `Person` objects is created.</span></span> <span data-ttu-id="a7433-121">클라이언트는 서비스의 메서드 3개를 각각 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="a7433-121">The client calls each of the three methods in the service.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="a7433-122">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="a7433-122">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="a7433-123">수행 했는지 확인 하십시오.는 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a7433-123">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="a7433-124">C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="a7433-124">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="a7433-125">지침에 따라 단일 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a7433-125">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="a7433-126">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7433-126">The samples may already be installed on your machine.</span></span> <span data-ttu-id="a7433-127">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="a7433-127">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="a7433-128">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="a7433-128">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="a7433-129">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7433-129">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Data\ObjectReferences`  
  
## <a name="see-also"></a><span data-ttu-id="a7433-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a7433-130">See Also</span></span>  
 <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A>  
 [<span data-ttu-id="a7433-131">상호 운영 가능한 개체 참조</span><span class="sxs-lookup"><span data-stu-id="a7433-131">Interoperable Object References</span></span>](../../../../docs/framework/wcf/feature-details/interoperable-object-references.md)
