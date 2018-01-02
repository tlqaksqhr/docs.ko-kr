---
title: "시작 설정 스키마"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- startup settings schema
- schema startup settings
- configuration schema [.NET Framework], startup settings
ms.assetid: 03de6972-442a-4648-9f3e-efa654e3b949
caps.latest.revision: "10"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 0536197d4cb8b30d99f514d8066e94bf84bffdf3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="startup-settings-schema"></a><span data-ttu-id="4ceb3-102">시작 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="4ceb3-102">Startup Settings Schema</span></span>
<span data-ttu-id="4ceb3-103">시작 설정은 응용 프로그램을 실행해야 하는 공용 언어 런타임의 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4ceb3-103">Startup settings specify the version of the common language runtime that should run the application.</span></span>  
  
|<span data-ttu-id="4ceb3-104">요소</span><span class="sxs-lookup"><span data-stu-id="4ceb3-104">Element</span></span>|<span data-ttu-id="4ceb3-105">설명</span><span class="sxs-lookup"><span data-stu-id="4ceb3-105">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4ceb3-106">\<requiredRuntime></span><span class="sxs-lookup"><span data-stu-id="4ceb3-106">\<requiredRuntime></span></span>](../../../../../docs/framework/configure-apps/file-schema/startup/requiredruntime-element.md)|<span data-ttu-id="4ceb3-107">응용 프로그램에서 1.0 버전의 공용 언어 런타임만 지원하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4ceb3-107">Specifies that the application supports only version 1.0 of the common language runtime.</span></span> <span data-ttu-id="4ceb3-108">런타임 버전 1.1로 빌드된 응용 프로그램은 **\<supportedRuntime>** 요소를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ceb3-108">Applications built with runtime version 1.1 should use the **\<supportedRuntime>** element.</span></span>|  
|[<span data-ttu-id="4ceb3-109">\<supportedRuntime></span><span class="sxs-lookup"><span data-stu-id="4ceb3-109">\<supportedRuntime></span></span>](../../../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md)|<span data-ttu-id="4ceb3-110">응용 프로그램이 지원하는 공용 언어 런타임 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4ceb3-110">Specifies which versions of the common language runtime the application supports.</span></span>|  
|[<span data-ttu-id="4ceb3-111">\<startup></span><span class="sxs-lookup"><span data-stu-id="4ceb3-111">\<startup></span></span>](../../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)|<span data-ttu-id="4ceb3-112">**\<requiredRuntime>** 및 **\<supportedRuntime>** 요소가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ceb3-112">Contains the **\<requiredRuntime>** and **\<supportedRuntime>** elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4ceb3-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4ceb3-113">See Also</span></span>  
 [<span data-ttu-id="4ceb3-114">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="4ceb3-114">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="4ceb3-115">\<PaveOver> 사용할 런타임 버전 지정</span><span class="sxs-lookup"><span data-stu-id="4ceb3-115">\<PaveOver> Specifying Which Runtime Version to Use</span></span>](http://msdn.microsoft.com/en-us/c376208d-980d-42b4-865b-fbe0d9cc97c2)
