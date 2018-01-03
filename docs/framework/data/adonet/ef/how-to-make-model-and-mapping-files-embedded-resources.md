---
title: "방법: 모델 및 매핑 파일을 포함 리소스로 만들기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 20dfae4d-e95a-4264-9540-f5ad23b462d3
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 6b8439e81c9a77f15556c21c5e96add86265c4ad
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-make-model-and-mapping-files-embedded-resources"></a><span data-ttu-id="122cc-102">방법: 모델 및 매핑 파일을 포함 리소스로 만들기</span><span class="sxs-lookup"><span data-stu-id="122cc-102">How to: Make Model and Mapping Files Embedded Resources</span></span>
<span data-ttu-id="122cc-103">[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] 모델 및 매핑 파일을 응용 프로그램의 포함 리소스로 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="122cc-103">The [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] enables you to deploy model and mapping files as embedded resources of an application.</span></span> <span data-ttu-id="122cc-104">포함된 모델 및 매핑 파일이 있는 어셈블리는 엔터티 연결과 동일한 응용 프로그램 도메인에 로드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="122cc-104">The assembly with the embedded model and mapping files must be loaded in the same application domain as the entity connection.</span></span> <span data-ttu-id="122cc-105">자세한 내용은 [연결 문자열](../../../../../docs/framework/data/adonet/ef/connection-strings.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="122cc-105">For more information, see [Connection Strings](../../../../../docs/framework/data/adonet/ef/connection-strings.md).</span></span> <span data-ttu-id="122cc-106">기본적으로 [!INCLUDE[adonet_edm](../../../../../includes/adonet-edm-md.md)] 도구는 모델과 매핑 파일을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="122cc-106">By default, the [!INCLUDE[adonet_edm](../../../../../includes/adonet-edm-md.md)] tools embed the model and mapping files.</span></span> <span data-ttu-id="122cc-107">모델 및 매핑 파일을 수동으로 정의하는 경우 이 절차를 사용하여 파일을 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] 응용 프로그램과 함께 포함 리소스로 배포해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="122cc-107">When you manually define the model and mapping files, use this procedure to ensure that the files are deployed as embedded resources together with an [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="122cc-108">포함 리소스를 유지하려면 모델 및 매핑 파일이 수정될 때마다 이 절차를 반복해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="122cc-108">To maintain embedded resources, you must repeat this procedure whenever the model and mapping files are modified.</span></span>  
  
### <a name="to-embed-model-and-mapping-files"></a><span data-ttu-id="122cc-109">모델 및 매핑 파일을 포함하려면</span><span class="sxs-lookup"><span data-stu-id="122cc-109">To embed model and mapping files</span></span>  
  
1.  <span data-ttu-id="122cc-110">**솔루션 탐색기**, 개념적 (.csdl) 파일을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="122cc-110">In **Solution Explorer**, select the conceptual (.csdl) file.</span></span>  
  
2.  <span data-ttu-id="122cc-111">에 **속성** 창 설정 **빌드 작업** 를 **포함 리소스**합니다.</span><span class="sxs-lookup"><span data-stu-id="122cc-111">In the **Properties** pane, set **Build Action** to **Embedded Resource**.</span></span>  
  
3.  <span data-ttu-id="122cc-112">저장소 파일(.ssdl) 및 매핑 파일(.msl)에 대해 1단계와 2단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="122cc-112">Repeat steps 1 and 2 for the storage (.ssdl) file and the mapping (.msl) file.</span></span>  
  
4.  <span data-ttu-id="122cc-113">**솔루션 탐색기**, App.config 파일을 두 번 클릭 한 다음 수정 된 `Metadata` 에서 매개 변수는 `connectionString` 다음 형식 중 하나를 기반으로 특성:</span><span class="sxs-lookup"><span data-stu-id="122cc-113">In **Solution Explorer**, double-click the App.config file and then modify the `Metadata` parameter in the `connectionString` attribute based on one of the following formats:</span></span>  
  
    -   <span data-ttu-id="122cc-114">`Metadata=` `res://<assemblyFullName>/<resourceName>;`</span><span class="sxs-lookup"><span data-stu-id="122cc-114">`Metadata=` `res://<assemblyFullName>/<resourceName>;`</span></span>  
  
    -   <span data-ttu-id="122cc-115">`Metadata=` `res://*/<resourceName>;`</span><span class="sxs-lookup"><span data-stu-id="122cc-115">`Metadata=` `res://*/<resourceName>;`</span></span>  
  
    -   `Metadata=res://*;`  
  
     <span data-ttu-id="122cc-116">자세한 내용은 [연결 문자열](../../../../../docs/framework/data/adonet/ef/connection-strings.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="122cc-116">For more information, see [Connection Strings](../../../../../docs/framework/data/adonet/ef/connection-strings.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="122cc-117">예</span><span class="sxs-lookup"><span data-stu-id="122cc-117">Example</span></span>  
 <span data-ttu-id="122cc-118">다음 연결 문자열에 포함 된 모델 및 매핑 파일에 대 한 참조는 [AdventureWorks Sales 모델](http://msdn.microsoft.com/en-us/f16cd988-673f-4376-b034-129ca93c7832)합니다.</span><span class="sxs-lookup"><span data-stu-id="122cc-118">The following connection string references embedded model and mapping files for the [AdventureWorks Sales Model](http://msdn.microsoft.com/en-us/f16cd988-673f-4376-b034-129ca93c7832).</span></span> <span data-ttu-id="122cc-119">이 연결 문자열은 프로젝트의 App.config 파일에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="122cc-119">This connection string is stored in the project's App.config file.</span></span>  
  
  
  
## <a name="see-also"></a><span data-ttu-id="122cc-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="122cc-120">See Also</span></span>  
 [<span data-ttu-id="122cc-121">모델링 및 매핑</span><span class="sxs-lookup"><span data-stu-id="122cc-121">Modeling and Mapping</span></span>](../../../../../docs/framework/data/adonet/ef/modeling-and-mapping.md)  
 [<span data-ttu-id="122cc-122">방법: 연결 문자열 정의</span><span class="sxs-lookup"><span data-stu-id="122cc-122">How to: Define the Connection String</span></span>](../../../../../docs/framework/data/adonet/ef/how-to-define-the-connection-string.md)  
 [<span data-ttu-id="122cc-123">방법: EntityConnection 연결 문자열 작성</span><span class="sxs-lookup"><span data-stu-id="122cc-123">How to: Build an EntityConnection Connection String</span></span>](../../../../../docs/framework/data/adonet/ef/how-to-build-an-entityconnection-connection-string.md)  
 [<span data-ttu-id="122cc-124">ADO.NET 엔터티 데이터 모델 도구</span><span class="sxs-lookup"><span data-stu-id="122cc-124">ADO.NET Entity Data Model  Tools</span></span>](http://msdn.microsoft.com/en-us/91076853-0881-421b-837a-f582f36be527)
