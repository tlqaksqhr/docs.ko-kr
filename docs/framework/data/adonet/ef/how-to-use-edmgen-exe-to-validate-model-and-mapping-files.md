---
title: "방법: EdmGen.exe를 사용하여 모델 유효성 검사 및 파일 매핑"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2641906a-971a-4d0b-8aee-13fabc02a1cc
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 502646236d08198663b072a4adbbefb7376a6486
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-edmgenexe-to-validate-model-and-mapping-files"></a><span data-ttu-id="a11b6-102">방법: EdmGen.exe를 사용하여 모델 유효성 검사 및 파일 매핑</span><span class="sxs-lookup"><span data-stu-id="a11b6-102">How to: Use EdmGen.exe to Validate Model and Mapping Files</span></span>
<span data-ttu-id="a11b6-103">이 항목에서는 사용 하는 [EDM 생성기 (EdmGen.exe)](../../../../../docs/framework/data/adonet/ef/edm-generator-edmgen-exe.md) 모델 및 매핑 파일 유효성을 검사 하는 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="a11b6-103">This topic shows how to use the [EDM Generator (EdmGen.exe)](../../../../../docs/framework/data/adonet/ef/edm-generator-edmgen-exe.md) tool to validate the model and mapping files.</span></span> <span data-ttu-id="a11b6-104">자세한 내용은 참조 [엔터티 데이터 모델](../../../../../docs/framework/data/adonet/entity-data-model.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a11b6-104">For more information, see [Entity Data Model](../../../../../docs/framework/data/adonet/entity-data-model.md).</span></span>  
  
### <a name="to-validate-the-school-model-using-edmgenexe"></a><span data-ttu-id="a11b6-105">EdmGen.exe를 사용하여 School 모델의 유효성을 검사하려면</span><span class="sxs-lookup"><span data-stu-id="a11b6-105">To validate the School model using EdmGen.exe</span></span>  
  
1.  <span data-ttu-id="a11b6-106">School 데이터베이스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a11b6-106">Create the School database.</span></span> <span data-ttu-id="a11b6-107">자세한 내용은 참조 [School 샘플 데이터베이스 만들기](http://msdn.microsoft.com/en-us/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0)합니다.</span><span class="sxs-lookup"><span data-stu-id="a11b6-107">For more information, see [Creating the School Sample Database](http://msdn.microsoft.com/en-us/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0).</span></span>  
  
2.  <span data-ttu-id="a11b6-108">School 모델을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="a11b6-108">Generate the School model.</span></span> <span data-ttu-id="a11b6-109">자세한 내용은 참조 [하는 방법: 모델 및 매핑 파일 생성을 사용 하 여 EdmGen.exe](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a11b6-109">For more information, see [How to: Use EdmGen.exe to Generate the Model and Mapping Files](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span></span>  
  
3.  <span data-ttu-id="a11b6-110">명령 프롬프트에서 줄 바꿈 없이 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a11b6-110">At the command prompt, execute the following command without line breaks:</span></span>  
  
    ```console
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:ValidateArtifacts /inssdl:.\School.ssdl /inmsl:.\School.msl /incsdl:.\School.csdl  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="a11b6-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a11b6-111">See Also</span></span>  
 [<span data-ttu-id="a11b6-112">방법: 수동으로 Entity Framework 프로젝트 구성</span><span class="sxs-lookup"><span data-stu-id="a11b6-112">How to: Manually Configure an Entity Framework Project</span></span>](http://msdn.microsoft.com/en-us/73f6ae1d-b3b2-4577-aebd-ad5a75954e9e)  
 [<span data-ttu-id="a11b6-113">ADO.NET 엔터티 데이터 모델 도구</span><span class="sxs-lookup"><span data-stu-id="a11b6-113">ADO.NET Entity Data Model  Tools</span></span>](http://msdn.microsoft.com/en-us/91076853-0881-421b-837a-f582f36be527)  
 [<span data-ttu-id="a11b6-114">방법: 쿼리 성능을 개선 하는 뷰를 미리 생성</span><span class="sxs-lookup"><span data-stu-id="a11b6-114">How to: Pre-Generate Views to Improve Query Performance</span></span>](http://msdn.microsoft.com/en-us/b18a9d16-e10b-4043-ba91-b632f85a2579)  
 [<span data-ttu-id="a11b6-115">방법: EdmGen.exe를 사용 하 여 개체 계층 코드를 생성 하려면</span><span class="sxs-lookup"><span data-stu-id="a11b6-115">How to: Use EdmGen.exe to Generate Object-Layer Code</span></span>](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-object-layer-code.md)
