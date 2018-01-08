---
title: "완화: 응용 프로그램 도메인 간 개체의 deserialization"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 30c2d66c-04a8-41a5-ad31-646b937f61b5
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fa156c914d2a1bb2ff0601d9e06c9b87d4190754
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="mitigation-deserialization-of-objects-across-app-domains"></a><span data-ttu-id="a50d2-102">완화: 응용 프로그램 도메인 간 개체의 deserialization</span><span class="sxs-lookup"><span data-stu-id="a50d2-102">Mitigation: Deserialization of Objects Across App Domains</span></span>
<span data-ttu-id="a50d2-103">경우에 따라 앱이 다양한 응용 프로그램을 기반으로 하여 두 개 이상의 응용 프로그램 도메인을 사용하면 여러 응용 프로그램 도메인 간에 논리 호출 컨텍스트의 개체를 deserialize하려는 시도로 인해 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="a50d2-103">In some cases, when an app uses two or more app domains with different application bases, the attempt to deserialize objects in the logical call context across app domains throws an exception.</span></span>  
  
## <a name="diagnosing-the-issue"></a><span data-ttu-id="a50d2-104">문제 진단</span><span class="sxs-lookup"><span data-stu-id="a50d2-104">Diagnosing the issue</span></span>  
 <span data-ttu-id="a50d2-105">다음 조건의 순서대로 문제가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="a50d2-105">The issue arises under the following sequence of conditions:</span></span>  
  
1.  <span data-ttu-id="a50d2-106">앱이 다양한 응용 프로그램을 기반으로 하여 두 개 이상의 응용 프로그램 도메인을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a50d2-106">An app uses two or more app domains with different application bases.</span></span>  
  
2.  <span data-ttu-id="a50d2-107">일부 형식은 <xref:System.Runtime.Remoting.Messaging.LogicalCallContext> 또는 <xref:System.Runtime.Remoting.Messaging.LogicalCallContext.SetData%2A?displayProperty=nameWithType>와 같은 메서드를 호출하여 <xref:System.Runtime.Remoting.Messaging.CallContext.LogicalSetData%2A?displayProperty=nameWithType>에 명시적으로 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="a50d2-107">Some types are explicitly added to the <xref:System.Runtime.Remoting.Messaging.LogicalCallContext> by calling a method such as <xref:System.Runtime.Remoting.Messaging.LogicalCallContext.SetData%2A?displayProperty=nameWithType> or <xref:System.Runtime.Remoting.Messaging.CallContext.LogicalSetData%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="a50d2-108">이러한 형식은 serializable로 표시되지 않고 전역 어셈블리 캐시에 저장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a50d2-108">These types are not marked as serializable and are not stored in the global assembly cache.</span></span>  
  
3.  <span data-ttu-id="a50d2-109">나중에 기본이 아닌 응용 프로그램 도메인에서 실행되는 코드가 구성 파일에서 값을 읽거나 XML을 사용하여 개체를 deserialize하려고 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="a50d2-109">Later, code running in the non-default app domain tries to read a value from a configuration file or use XML to deserialize an object.</span></span>  
  
4.  <span data-ttu-id="a50d2-110">구성 파일에서 읽거나 개체를 deserialize하기 위해 <xref:System.Xml.XmlReader> 개체는 구성 시스템에 액세스하려고 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="a50d2-110">In order to read from a configuration file or deserialize the object, an <xref:System.Xml.XmlReader> object tries to access the configuration system.</span></span>  
  
5.  <span data-ttu-id="a50d2-111">구성 시스템이 아직 초기화되지 않은 경우, 초기화를 완료해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a50d2-111">If the configuration system has not already been initialized, it must complete its initialization.</span></span> <span data-ttu-id="a50d2-112">즉, 런타임은 실제로 다음과 같이 구성 시스템에 대한 안정적인 경로를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a50d2-112">This means, among other things, that the runtime has to create a stable path for a configuration system, which it does as follows:</span></span>  
  
    1.  <span data-ttu-id="a50d2-113">기본이 아닌 응용 프로그램 도메인의 증명 정보를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="a50d2-113">It looks for evidence for the non-default app domain.</span></span>  
  
    2.  <span data-ttu-id="a50d2-114">기본 응용 프로그램 도메인을 기반으로 하여 기본이 아닌 응용 프로그램 도메인의 증명 정보를 계산하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="a50d2-114">It tries to calculate the evidence for the non-default app domain based on the default app domain.</span></span>  
  
    3.  <span data-ttu-id="a50d2-115">기본 응용 프로그램 도메인의 증명 정보를 가져오기 위한 호출은 기본이 아닌 응용 프로그램 도메인에서 기본 응용 프로그램 도메인으로 응용 프로그램 간 도메인 호출을 트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="a50d2-115">The call to get evidence for the default app domain triggers a cross-app domain call from the non-default app domain to the default app domain.</span></span>  
  
    4.  <span data-ttu-id="a50d2-116">.NET Framework에서 응용 프로그램 간 도메인 계약의 일부로서 논리 호출 컨텍스트의 내용 또한 응용 프로그램 도메인 경계를 넘어 마샬링해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a50d2-116">As part of the cross-app domain contract in the .NET Framework, the contents of the logical call context also have to be marshaled across app domain boundaries.</span></span>  
  
6.  <span data-ttu-id="a50d2-117">기본 응용 프로그램 도메인에서 논리 호출 컨텍스트에 있는 형식을 확인할 수 없으므로 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="a50d2-117">Because the types that are in the logical call context cannot be resolved in the default app domain, an exception is thrown.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="a50d2-118">완화</span><span class="sxs-lookup"><span data-stu-id="a50d2-118">Mitigation</span></span>  
 <span data-ttu-id="a50d2-119">이 문제를 해결하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="a50d2-119">To work around this issue, do the following</span></span>  
  
1.  <span data-ttu-id="a50d2-120">예외가 throw될 때 호출 스택에서 `get_Evidence`에 대한 호출을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="a50d2-120">Look for the call to `get_Evidence` in the call stack when the exception is thrown.</span></span> <span data-ttu-id="a50d2-121">이 예외는 <xref:System.IO.FileNotFoundException> 및 <xref:System.Runtime.Serialization.SerializationException>을 포함한 예외의 큰 하위 집합 중 하나일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a50d2-121">The exception can be any of a large subset of exceptions, including <xref:System.IO.FileNotFoundException> and <xref:System.Runtime.Serialization.SerializationException>.</span></span>  
  
2.  <span data-ttu-id="a50d2-122">응용 프로그램에서 개체가 논리 호출 컨텍스트에 추가되지 않은 위치를 찾아 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a50d2-122">Identify the place in the app where no objects are added to the logical call context and add the following code:</span></span>  
  
    ```  
    System.Configuration.ConfigurationManager.GetSection("system.xml/xmlReader");  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="a50d2-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a50d2-123">See Also</span></span>  
 [<span data-ttu-id="a50d2-124">런타임 변경 내용</span><span class="sxs-lookup"><span data-stu-id="a50d2-124">Runtime Changes</span></span>](../../../docs/framework/migration-guide/runtime-changes-in-the-net-framework-4-5-1.md)
