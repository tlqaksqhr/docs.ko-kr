---
title: "모델링 및 매핑"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ec8a9515-3708-4cde-a688-4d8e6975f150
caps.latest.revision: "7"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 2004b950f1096f574734259ba02944577dd9adc9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="modeling-and-mapping"></a><span data-ttu-id="4ca98-102">모델링 및 매핑</span><span class="sxs-lookup"><span data-stu-id="4ca98-102">Modeling and Mapping</span></span>
<span data-ttu-id="4ca98-103">[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]에서는 응용 프로그램에 가장 적합한 방식으로 개념적 모델, 저장소 모델 및 두 모델 간의 매핑을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ca98-103">In the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)], you can define the conceptual model, storage model, and the mapping between the two in the way that best suits your application.</span></span> <span data-ttu-id="4ca98-104">엔터티 데이터 모델 도구에서 [!INCLUDE[vsprvs](../../../../../includes/vsprvs-md.md)] 만들 수는 있습니다.[ edmx 파일](http://msdn.microsoft.com/en-us/f4c8e7ce-1db6-417e-9759-15f8b55155d4) 데이터베이스 또는 그래픽 모델과 업데이트 한 다음 데이터베이스나 모델이 변경 될 때 해당 파일에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ca98-104">The Entity Data Model Tools in [!INCLUDE[vsprvs](../../../../../includes/vsprvs-md.md)] allow you to create an .[edmx file](http://msdn.microsoft.com/en-us/f4c8e7ce-1db6-417e-9759-15f8b55155d4) from a database or a graphical model and then update that file when either the database or model changes.</span></span>  
  
 <span data-ttu-id="4ca98-105">Entity Framework 4.1부터는 Code First 개발을 통해 모델을 프로그램 방식으로 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ca98-105">Starting with the Entity Framework 4.1 you can also create a model programmatically using Code First development.</span></span> <span data-ttu-id="4ca98-106">Code First 개발에는 두 가지 다른 시나리오가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ca98-106">There are two different scenarios for Code First development.</span></span> <span data-ttu-id="4ca98-107">두 경우 모두 개발자는 .NET Framewor 클래스 정의를 코딩하여 모델을 정의한 후 데이터 주석 또는 fluent API를 사용하여 추가 매핑 또는 구성을 선택적으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4ca98-107">In both cases, the developer defines a model by coding .NET Framework class definitions, and then optionally specifies additional mapping or configuration by using Data Annotations or the fluent API.</span></span>  
  
 <span data-ttu-id="4ca98-108">자세한 내용은 참조 [만들고 개념적 모델을 매핑하여](http://go.microsoft.com/fwlink/?LinkId=235016)합니다.</span><span class="sxs-lookup"><span data-stu-id="4ca98-108">For more information, see [Creating and Mapping a Conceptual Model](http://go.microsoft.com/fwlink/?LinkId=235016).</span></span>  
  
 <span data-ttu-id="4ca98-109">에 포함 되어 있는 EDM 생성기 또한 사용할 수 있습니다는 [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="4ca98-109">You can also use the EDM Generator, which is included with the [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="4ca98-110">EdmGen.exe 생성기는 기존 데이터 소스에서 .csdl, .ssdl 및 .msl 파일을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="4ca98-110">The EdmGen.exe generates the .csdl, .ssdl, and .msl files from an existing data source.</span></span> <span data-ttu-id="4ca98-111">또한 모델 및 매핑 콘텐츠를 수동으로 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ca98-111">You can also manually create the model and mapping content.</span></span> <span data-ttu-id="4ca98-112">자세한 내용은 참조 [EDM 생성기 (EdmGen.exe)](../../../../../docs/framework/data/adonet/ef/edm-generator-edmgen-exe.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4ca98-112">For more information, see [EDM Generator (EdmGen.exe)](../../../../../docs/framework/data/adonet/ef/edm-generator-edmgen-exe.md).</span></span>
