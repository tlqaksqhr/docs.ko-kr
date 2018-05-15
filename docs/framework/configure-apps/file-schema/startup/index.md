---
title: 시작 설정 스키마
ms.date: 03/30/2017
helpviewer_keywords:
- startup settings schema
- schema startup settings
- configuration schema [.NET Framework], startup settings
ms.assetid: 03de6972-442a-4648-9f3e-efa654e3b949
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 59f0441b79244eb529be338495c32af886a5f2b3
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="startup-settings-schema"></a><span data-ttu-id="38744-102">시작 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="38744-102">Startup Settings Schema</span></span>
<span data-ttu-id="38744-103">시작 설정은 응용 프로그램을 실행해야 하는 공용 언어 런타임의 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="38744-103">Startup settings specify the version of the common language runtime that should run the application.</span></span>  
  
|<span data-ttu-id="38744-104">요소</span><span class="sxs-lookup"><span data-stu-id="38744-104">Element</span></span>|<span data-ttu-id="38744-105">설명</span><span class="sxs-lookup"><span data-stu-id="38744-105">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="38744-106">\<requiredRuntime></span><span class="sxs-lookup"><span data-stu-id="38744-106">\<requiredRuntime></span></span>](../../../../../docs/framework/configure-apps/file-schema/startup/requiredruntime-element.md)|<span data-ttu-id="38744-107">응용 프로그램에서 1.0 버전의 공용 언어 런타임만 지원하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="38744-107">Specifies that the application supports only version 1.0 of the common language runtime.</span></span> <span data-ttu-id="38744-108">런타임 버전 1.1로 빌드된 응용 프로그램은 **\<supportedRuntime>** 요소를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38744-108">Applications built with runtime version 1.1 should use the **\<supportedRuntime>** element.</span></span>|  
|[<span data-ttu-id="38744-109">\<supportedRuntime></span><span class="sxs-lookup"><span data-stu-id="38744-109">\<supportedRuntime></span></span>](../../../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md)|<span data-ttu-id="38744-110">응용 프로그램이 지원하는 공용 언어 런타임 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="38744-110">Specifies which versions of the common language runtime the application supports.</span></span>|  
|[<span data-ttu-id="38744-111">\<startup></span><span class="sxs-lookup"><span data-stu-id="38744-111">\<startup></span></span>](../../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)|<span data-ttu-id="38744-112">**\<requiredRuntime>** 및 **\<supportedRuntime>** 요소가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38744-112">Contains the **\<requiredRuntime>** and **\<supportedRuntime>** elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="38744-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="38744-113">See Also</span></span>  
 [<span data-ttu-id="38744-114">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="38744-114">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="38744-115">\<PaveOver> 사용할 런타임 버전 지정</span><span class="sxs-lookup"><span data-stu-id="38744-115">\<PaveOver> Specifying Which Runtime Version to Use</span></span>](http://msdn.microsoft.com/library/c376208d-980d-42b4-865b-fbe0d9cc97c2)
