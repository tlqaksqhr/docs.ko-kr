---
title: '방법: Svcutil.exe를 사용하여 컴파일된 서비스 코드에서 메타데이터 내보내기'
ms.date: 03/30/2017
ms.assetid: 95d0aed3-16a2-4398-89bb-39418eeb7355
ms.openlocfilehash: 68d651a396aa748d53f9121e9861260bdbf2dffa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33492751"
---
# <a name="how-to-use-svcutilexe-to-export-metadata-from-compiled-service-code"></a><span data-ttu-id="6d7dc-102">방법: Svcutil.exe를 사용하여 컴파일된 서비스 코드에서 메타데이터 내보내기</span><span class="sxs-lookup"><span data-stu-id="6d7dc-102">How to: Use Svcutil.exe to Export Metadata from Compiled Service Code</span></span>
<span data-ttu-id="6d7dc-103">Svcutil.exe에서는 다음과 같이 컴파일된 어셈블리에 있는 서비스, 계약 및 데이터 형식에 대한 메타데이터를 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d7dc-103">Svcutil.exe can export metadata for services, contracts, and data types in compiled assemblies, as follows:</span></span>  
  
-   <span data-ttu-id="6d7dc-104">Svcutil.exe를 사용하는 어셈블리 집합의 컴파일된 모든 서비스 계약에 대한 메타데이터를 내보내려면 어셈블리를 입력 매개 변수로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6d7dc-104">To export metadata for all compiled service contracts for a set of assemblies using Svcutil.exe, specify the assemblies as input parameters.</span></span> <span data-ttu-id="6d7dc-105">이것은 기본적인 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="6d7dc-105">This is the default behavior.</span></span>  
  
-   <span data-ttu-id="6d7dc-106">Svcutil.exe를 사용하는 컴파일된 서비스에 대한 메타데이터를 내보내려면 서비스 어셈블리 또는 어셈블리를 입력 매개 변수로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6d7dc-106">To export metadata for a compiled service using Svcutil.exe, specify the service assembly or assemblies as input parameters.</span></span> <span data-ttu-id="6d7dc-107">내보낼 서비스의 구성 이름을 나타내려면 `/serviceName` 옵션을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d7dc-107">You must use the `/serviceName` option to indicate the configuration name of the service you want to export.</span></span> <span data-ttu-id="6d7dc-108">Svcutil.exe에서는 지정된 실행 가능한 어셈블리에 대한 구성 파일을 자동으로 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="6d7dc-108">Svcutil.exe automatically loads the configuration file for the specified executable assembly.</span></span>  
  
-   <span data-ttu-id="6d7dc-109">어셈블리 집합 내의 모든 데이터 계약 형식을 내보내려면 `/dataContractOnly` 옵션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6d7dc-109">To export all data contract types within a set of assemblies, use the `/dataContractOnly` option.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6d7dc-110">종속 어셈블리의 파일 경로를 지정하려면 `/reference` 옵션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6d7dc-110">Use the `/reference` option to specify the file paths to any dependent assemblies.</span></span>  
  
### <a name="to-export-metadata-for-compiled-service-contracts"></a><span data-ttu-id="6d7dc-111">컴파일된 서비스 계약에 대한 메타데이터를 내보내려면</span><span class="sxs-lookup"><span data-stu-id="6d7dc-111">To export metadata for compiled service contracts</span></span>  
  
1.  <span data-ttu-id="6d7dc-112">서비스 계약 구현을 하나 이상의 클래스 라이브러리로 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="6d7dc-112">Compile your service contract implementations into one or more class libraries.1</span></span>  
  
2.  <span data-ttu-id="6d7dc-113">Svcutil.exe를 컴파일된 어셈블리에서 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6d7dc-113">Run Svcutil.exe on the compiled assemblies.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6d7dc-114">종속 어셈블리의 파일 경로를 지정하려면 `/reference` 스위치를 사용해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d7dc-114">You might need to use the `/reference` switch to specify the file path to any dependent assemblies.</span></span>  
  
    ```  
    svcutil.exe Contracts.dll  
    ```  
  
### <a name="to-export-metadata-for-a-compiled-service"></a><span data-ttu-id="6d7dc-115">컴파일된 서비스에 대한 메타데이터를 내보내려면</span><span class="sxs-lookup"><span data-stu-id="6d7dc-115">To export metadata for a compiled service</span></span>  
  
1.  <span data-ttu-id="6d7dc-116">서비스 구현을 실행 가능한 어셈블리로 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="6d7dc-116">Compile your service implementation into an executable assembly.</span></span>  
  
2.  <span data-ttu-id="6d7dc-117">서비스 실행 파일의 구성 파일을 만들고 서비스 구성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6d7dc-117">Create a configuration file for your service executable and add a service configuration.</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <configuration>  
      <system.serviceModel>  
        <services>  
          <service name="MyService" >  
            <endpoint address="finder" contract="IPeopleFinder" binding="wsHttpBinding" />  
          </service>  
        </services>  
      </system.serviceModel>  
    </configuration>  
    ```  
  
3.  <span data-ttu-id="6d7dc-118">서비스의 구성 이름을 지정하려면 `/serviceName` 스위치를 사용하여 Svcutil.exe를 컴파일된 서비스 실행 파일에서 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6d7dc-118">Run Svcutil.exe on the compiled service executable using the `/serviceName` switch to specify the configuration name of the service.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6d7dc-119">종속 어셈블리의 파일 경로를 지정하려면 `/reference` 스위치를 사용해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d7dc-119">You might need to use the `/reference` switch to specify the file path to any dependent assemblies.</span></span>  
  
    ```  
    svcutil.exe /serviceName:MyService Service.exe /reference:path/Contracts.dll  
    ```  
  
### <a name="to-export-metadata-for-compiled-data-contracts"></a><span data-ttu-id="6d7dc-120">컴파일된 데이터 계약에 대한 메타데이터를 내보내려면</span><span class="sxs-lookup"><span data-stu-id="6d7dc-120">To export metadata for compiled data contracts</span></span>  
  
1.  <span data-ttu-id="6d7dc-121">데이터 계약 구현을 하나 이상의 클래스 라이브러리로 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="6d7dc-121">Compile your data contract implementations into one or more class libraries.</span></span>  
  
2.  <span data-ttu-id="6d7dc-122">데이터 계약의 메타데이터만 생성되어야 함을 지정하려면 `/dataContract` 스위치를 사용하여 Svcutil.exe를 컴파일된 어셈블리에서 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6d7dc-122">Run Svcutil.exe on the compiled assemblies using the `/dataContract` switch to specify that only metadata for data contracts should be generated.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6d7dc-123">종속 어셈블리의 파일 경로를 지정하려면 `/reference` 스위치를 사용해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d7dc-123">You might need to use the `/reference` switch to specify the file path to any dependent assemblies.</span></span>  
  
    ```  
    svcutil.exe /dataContractOnly Contracts.dll  
    ```  
  
## <a name="example"></a><span data-ttu-id="6d7dc-124">예제</span><span class="sxs-lookup"><span data-stu-id="6d7dc-124">Example</span></span>  
 <span data-ttu-id="6d7dc-125">다음 예제에서는 단순 서비스 구현 및 구성에 대한 메타데이터를 생성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6d7dc-125">The following example demonstrates how to generate metadata for a simple service implementation and configuration.</span></span>  
  
 <span data-ttu-id="6d7dc-126">서비스 계약에 대한 메타데이터를 내보내려면</span><span class="sxs-lookup"><span data-stu-id="6d7dc-126">To export metadata for the service contract.</span></span>  
  
```  
svcutil.exe Contracts.dll  
```  
  
 <span data-ttu-id="6d7dc-127">데이터 계약에 대한 메타데이터를 내보내려면</span><span class="sxs-lookup"><span data-stu-id="6d7dc-127">To export metadata for the data contracts.</span></span>  
  
```  
svcutil.exe /dataContractOnly Contracts.dll  
```  
  
 <span data-ttu-id="6d7dc-128">서비스 구현에 대한 메타데이터를 내보내려면</span><span class="sxs-lookup"><span data-stu-id="6d7dc-128">To export metadata for the service implementation.</span></span>  
  
```  
svcutil.exe /serviceName:MyService Service.exe /reference:<path>/Contracts.dll  
```  
  
 <span data-ttu-id="6d7dc-129">`<path>`는 Contracts.dll의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="6d7dc-129">The `<path>` is the path to Contracts.dll.</span></span>  
  
```  
// The following service contract and data contracts are compiled into   
// Contracts.dll.  
[ServiceContract(ConfigurationName="IPeopleFinder")]  
public interface IPersonFinder  
{  
    [OperationContract]  
    Address GetAddress(Person s);  
}  
  
[DataContract]  
public class Person  
{  
    [DataMember]  
    public string firstName;  
    [DataMember]  
    public string lastName;  
    [DataMember]  
    public int age;  
}  
  
[DataContract]  
public class Address  
{  
    [DataMember]  
    public string city;  
    [DataMember]  
    public string state;  
    [DataMember]  
    public string street;  
    [DataMember]  
    public int zipCode;  
    [DataMember]  
    public Person person;  
}  
  
// The following service implementation is compiled into Service.exe.     
// This service uses the contracts specified in Contracts.dll.  
[ServiceBehavior(ConfigurationName = "MyService")]  
public class MyService : IPersonFinder  
{  
    public Address GetAddress(Person person)  
    {  
        Address address = new Address();  
        address.person = person;  
        return address;  
    }  
}  
  
<!-- The following is the configuration file for Service.exe. -->  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
  <system.serviceModel>  
    <services>  
      <service name="MyService">  
         <endpoint  address="finder"  
                    binding="basicHttpBinding"  
                    contract="IPeopleFinder"/>  
      </service>  
    </services>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="6d7dc-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6d7dc-130">See Also</span></span>  
 [<span data-ttu-id="6d7dc-131">ServiceModel Metadata 유틸리티 도구(Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="6d7dc-131">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)  
 [<span data-ttu-id="6d7dc-132">메타데이터 내보내기 및 가져오기</span><span class="sxs-lookup"><span data-stu-id="6d7dc-132">Exporting and Importing Metadata</span></span>](../../../../docs/framework/wcf/feature-details/exporting-and-importing-metadata.md)
